# Introduction

To use the `Atlas` class, you need to import it from atlas.py into your program. Then, it needs to be initialized and set to a variable. Put the following code at the top of your main program file to do this.

```python
from atlas import Atlas

device = Atlas()
```

Now, you can use the `device` variable to access the various components on the Atlas device. For example, you can turn the red LED on with the following code.

```
device.red_led.value(1)
```

The rest of this book goes over using all of the different components on the Atlas device. You can find information about the specific components in the sections listed below.

- [LEDs](./LEDs.md)
- [Buttons](./buttons.md)
- [Buzzer](./buzzer.md)
- [Displays](./displays.md)