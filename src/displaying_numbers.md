# Displaying Numbers

## Usage

Write a number to the display.

```python
Atlas.write_num(v, dp=[d])
```

`v` is a integer value to write to the display. This number can range from -99999 to 999999. `d` is an optional integer argument that indicates the location of decimal points. Decimal points are placed based on the binary representation of the integer argument. For example `0b100000` would put a decimal point in the first position. `0b111111` would put a decimal point in every position.

```python
Atlas.increment_num()
```

Increase the current number on the display by 1.

```python
Atlas.increment_num()
```

Decrease the current number on the display by 1.

```python
Atlas.decrement_num()
```

## Examples

```python
from atlas import Atlas

device = Atlas()

device.write_num(123456) # write 123456 to the display
device.increment_num() # increment the number to 123457
device.decrement_num() # decrement the number to 123456
```