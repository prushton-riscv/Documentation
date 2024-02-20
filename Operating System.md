

# User Interface
There are two things that interface with the user

## Keyboard
The keyboard is given 64 bytes to be fully compatible with [UTF-16](https://www.fileformat.info/info/charset/UTF-16/list.htm). When a character is written to the character register, the operating system will pick up the non-zero character and send it to the character buffer

## Character Buffer
This is where characters are stored to be displayed to the user. They can be requested one at a time and cached and sent to a display.

## Display
idk yet havent gotten there