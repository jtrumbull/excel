## `=RIGHT( text, num )`
Returns text representing the rightmost `num` characters of `text`

__Example__:
`=RIGHT("ABCDE", 2) = "DE"`

__Example__:
`=RIGHT("ABCDE", 3) = "CDE"`


## `=FIND( needle, haystack )`
Returns an integer representing the starting position of `needle` in `haystack`

__Example__:
`=FIND("C", "ABCDE") = 3`

__Example__:
`=FIND("BC", "ABCDE") = 2`

## `=LEN( text )`
Returns an integer representing the length of `text`

__Example__:
`=LEN("ABCDE") = 5`

## Finding the rightmost characters of `text` after `needle`
This is acheived by subtracting the position of `needle` from the length of `text` 

```
=LEN("ABCDE") = 5
=FIND("B", "ABCDE") = 2
=5 - 2 = 3
=RIGHT("ABCDE", 3) = "CDE"
```
Or more tersely `=RIGHT(text, LEN(text) - FIND(needle, text))`

_* If the length of `needle` is greater than 1, you will also need to subtract it's length - 1. The reason you subtract an additonal 1, is due to excel's lack of the zero-index -meaning that the index returned from FIND() already accounts for the first character in the needle._

```
// If the needle was "BC":
=RIGHT(text, LEN(text) - FIND(needle, text) - 1)

// If the needle was "BCD":
=RIGHT(text, LEN(text) - FIND(needle, text) - 2)
```
Or more universal `=RIGHT(text, LEN(text) - FIND(needle, text) - (LEN(needle) - 1))`
