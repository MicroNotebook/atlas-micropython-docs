# Mode Button

`atlas.py`

```python
from machine import Pin, SPI, Timer, RTC
import network
import time

...

_MODE_BUTTON_PIN = 12

...

class Atlas:
    def __init__(self):

        ...

        self.mode_button = Pin(_MODE_BUTTON_PIN, Pin.IN, Pin.PULL_UP)
        self.mode_button.irq(trigger=Pin.IRQ_FALLING, handler=self.mode_button_callback)

    ...

    def mode_button_callback(self, pin):
        if self._debounce(self.mode_button):
            for led in self.leds:
                self.toggle_pin(led)

...
```

## Usage

Check the value of the mode button pin.

```python
Atlas.mode_button.value()
```

The `value` function will return the current value of the mode button pin, either a 1 (for on) or a 0 (for off).

### Callback

The `atlas.py` file has a predefined callback as part of the `Atlas` class. For the mode button it is called `mode_button_callback`. As defined in the source code this callback toggles all of the LEDs on the device. Feel free to change this to whatever you want! I only recommend keeping your code within the `if` statement that is checking the `_debounce` function.

```python
def mode_button_callback(self, pin):
    if self._debounce(self.mode_button):
        # your code here
```

## Examples

```python
from atlas import Atlas

device = Atlas()

device.mode_button.value() # read the value of the button pin
```
