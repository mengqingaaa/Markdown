# bytes binary data 二进制数据

### `bytes` object
An *immutable* sequence of integers in the range of *0 <= x < 256*(single byte).
`bytes` is aan immutable version of `bytearray`.

The syntax for bytes literals is largely the same as that for string literals, except that a `b` prefix is added:
* Single quotes: `b'still allows embedded "double" quotes'`
* Double quotes: `b"still allows embedded 'single quotes"`
* Triple quotes: `b'''3 single quotes'''`, `b"""3 double quotes"""`

Only ASCII characters are permitted in bytes literals (regardless of the declared source code encoding).
Any binary values over *127* must be entered into bytes literals using the appropriate escape sequence.