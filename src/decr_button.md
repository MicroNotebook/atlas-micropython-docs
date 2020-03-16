# Decr Button

`atlas.py`

```python
from machine import Pin, SPI, Timer, RTC
import network
import time

...

_DECR_BUTTON_PIN = 2

...

class Atlas:
    def __init__(self):

        ...

        self.decr_button = Pin(_DECR_BUTTON_PIN, Pin.IN, Pin.PULL_UP)
        self.decr_button.irq(trigger=Pin.IRQ_FALLING, handler=self.incr_button_callback)

    ...

    def decr_button_callback(self, pin):
        if self._debounce(self.incr_button):
            self.decrement_num()

...
```

## Usage

Check the value of the decr button pin.

```python
Atlas.decr_button.value()
```

The `value` function will return the current value of the decr button pin, either a 1 (for on) or a 0 (for off).

### Callback

The `atlas.py` file has a predefined callback as part of the `Atlas` class. For the mode button it is called `decr_button_callback`. As defined in the source code this callback decrements the current number on the displays. Feel free to change this to whatever you want! I only recommend keeping your code within the `if` statement that is checking the `_debounce` function.

```python
def decr_button_callback(self, pin):
    if self._debounce(self.incr_button):
        # your code here
```

## Examples

```python
from atlas import Atlas

device = Atlas()

device.decr_button.value() # read the value of the button pin
```
