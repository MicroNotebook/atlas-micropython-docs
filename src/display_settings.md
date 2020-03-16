# Display Settings

## Usage

Clear all of the displays.

```python
Atlas.display_clear()
```

Change the brightness of the displays.

```python
Atlas.display_brightness(x)
```

`x` is a value between 0 and 15 inclusive. 0 is the least bright setting and 15 is the brightest.

## Examples

```python
from atlas import Atlas

device = Atlas()

device.write_num(1)
device.display_brightness(15) # set the display the brightest setting 
device.display_clear() # turn off all of the LEDs on the displays
```