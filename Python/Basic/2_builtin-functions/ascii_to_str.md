# Ascii to Str [ref](https://docs.python.org/3/library/functions.html)

* 문자를 읽어들여 아스키코드를 반환하거나 아스키코드를 읽어들여 문자를 반환해야 할 때가 있다.
* 이 때 사용하는 내장함수가 `ord()`와 `chr()`함수다.

### `ord(c)`
* argument type: str
* return ascii value of string

### `chr(i)`
* argument type: int
* return string representing a character whose unicode point is the integer i
* ValueError will be raised if i is outside the ascii code range (0~127)