---
title: "Runes in Golang"
datePublished: Mon Jun 19 2023 04:30:42 GMT+0000 (Coordinated Universal Time)
cuid: clj2cz8ow01vmzmnvfoc685an
slug: runes-in-golang
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/cBkHr5RuooA/upload/30fac6f8bc471e91b5d763e1bf3eda72.jpeg
tags: go, golang, google, char, runes

---

In Go, a rune is a built-in type that represents a Unicode code point.

It is an alias for the int32 type and can store any valid Unicode code point, ranging from 0 to 0x10FFFF.

The concept of runes in Go is essential for working with Unicode characters and strings, allowing developers to handle text in a consistent and comprehensive manner.

### What's up with Runes?

#### Unicode Code Points

Unicode is a character encoding standard that assigns a unique numeric value, known as a code point, to each character in the vast collection of human-written scripts and symbols.

In Go, a rune represents a Unicode code point, allowing developers to work with individual characters from different languages and scripts. Rune literals are denoted using single quotes, such as 'A', '😊', or '世'.

#### Rune Literals and Unicode Escapes

Rune literals can be expressed using their Unicode code point value, either as an integer or as a Unicode escape sequence.

For example, the rune literal 'A' can be represented as 65 (the Unicode code point for the uppercase letter 'A') or as '\\u0041' using the Unicode escape sequence.

Unicode escape sequences enable the representation of code points that cannot be easily typed or displayed directly.

#### Rune Type and Representation

The rune type in Go is an alias for int32 and represents a Unicode code point. Internally, a rune is represented as a 32-bit integer, enabling the storage of code points beyond the 16-bit range supported by the char type in some other programming languages.

The rune type facilitates the handling of characters from the entire Unicode character set, including characters in languages such as Sanskrit, Japanese, and Hindi.

#### String Type and Rune Operations

Go treats strings as a sequence of bytes, but when iterating over strings using a for loop, it implicitly converts each character to a rune, making it convenient to work with individual Unicode characters.

This conversion enables operations on runes, such as indexing, slicing, comparison, and manipulation of individual characters within a string.

The `for range` loop is commonly used to iterate over runes in a string, extracting and processing each character individually.

```go
// Example: Iterating over runes in a string 
str := "Hello, 世界!" // "世界" is "world" in Chinese
for _, r := range str { 
    fmt.Printf("%c ", r) 
} 
// Output: H e l l o , 世 界 !
```

#### Unicode Support and UTF-8 Encoding

Go natively supports Unicode and uses UTF-8 encoding for representing strings. UTF-8 is a variable-length encoding scheme that represents Unicode code points using 1 to 4 bytes.

When a string contains non-ASCII characters, each character may require multiple bytes in memory. The utf8 package in Go provides functions to work with UTF-8 encoded strings, including functions for counting runes, validating encodings, and manipulating Unicode code points.

### Conclusion

Runes in Go are the foundation for working with Unicode characters and strings. They represent Unicode code points and enable consistent handling of text from various languages and scripts.

With rune literals, the rune type, and support for UTF-8 encoding, Go provides a powerful and flexible environment for working with Unicode text.

So basically Go allows you to turn into a proper witch.