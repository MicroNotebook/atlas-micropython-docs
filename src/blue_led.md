# Blue LED

`atlas.py`

```python
from machine import Pin, SPI, Timer, RTC
import network
import time

...

_BLUE_LED_PIN = 5

...

class Atlas:
    def __init__(self):

        ...

        self.blue_led = Pin(_BLUE_LED_PIN, Pin.OUT)
        self.blue_led.value(0)

...
```

## Usage

Get or set the value of the blue LED pin.

```python
Atlas.blue_led.value([x])
```

With no parameter the `value` function will return the current value of the LED pin, either a 1 (for on) or a 0 (for off). Putting a 1 or a 0 for argument `x` will set the state of the LED pin to on or off respectively.

## Examples

```python
from atlas import Atlas

device = Atlas()

device.blue_led.value() # read the value of the LED pin
device.blue_led.value(1) # turn the LED on
device.blue_led.value(0) # turn the LED off
```
