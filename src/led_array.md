# LED Array

`atlas.py`

```python
from machine import Pin, SPI, Timer, RTC
import network
import time

...

_RED_LED_PIN = 0
_GREEN_LED_PIN = 4
_BLUE_LED_PIN = 5

...

class Atlas:
    def __init__(self):

        ...

        self.red_led = Pin(_RED_LED_PIN, Pin.OUT)
        self.green_led = Pin(_GREEN_LED_PIN, Pin.OUT)
        self.blue_led = Pin(_BLUE_LED_PIN, Pin.OUT)
        self.leds = [self.red_led, self.green_led, self.blue_led]

...
```

## Usage

Access the red, green, and blue LEDs indexed at 0, 1, and 2 respectively.

```python
Atlas.leds[i]
```

`i` must be an integer value of 0, 1, or 2 to access the items in the array.

## Examples

```python
from atlas import Atlas

device = Atlas()

for led in device.leds: # turn on all of the leds
    led.value(1)

for led in device.leds: # turn off all of the leds
    led.value(0)
```

