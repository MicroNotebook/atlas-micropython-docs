# Red LED

`atlas.py`

```python
from machine import Pin, SPI, Timer, RTC
import network
import time

...

_RED_LED_PIN = 0

...

class Atlas:
    def __init__(self):

        ...

        self.red_led = Pin(_RED_LED_PIN, Pin.OUT)
        self.red_led.value(0)

...
```

## Usage

Get or set the value of the red LED pin.

```python
Atlas.red_led.value([x])
```

With no parameter the `value` function will return the current value of the LED pin, either a 1 (for on) or a 0 (for off). Putting a 1 or a 0 for argument `x` will set the state of the LED pin to on or off respectively.

## Examples

```python
from atlas import Atlas

device = Atlas()

device.red_led.value() # read the value of the LED pin
device.red_led.value(1) # turn the LED on
device.red_led.value(0) # turn the LED off
```
