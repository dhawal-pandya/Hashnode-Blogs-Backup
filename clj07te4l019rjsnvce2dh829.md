---
title: "Golang  and fmt"
datePublished: Sat Jun 17 2023 16:30:39 GMT+0000 (Coordinated Universal Time)
cuid: clj07te4l019rjsnvce2dh829
slug: golang-and-fmt
tags: go, golang, google, print, fmt

---

The "fmt" package in Go is a part of the standard library and provides functionality for formatted input and output operations.

```plaintext
fmt <==> format
```

It is commonly used for printing values, formatting strings, and reading input from standard input.

### Methods

The "fmt" package offers several functions and methods that allow you to perform various formatting operations:

#### Printing Functions:

* fmt.Print: This function prints the arguments to the standard output without any formatting. The arguments are separated by spaces, and no newline character is appended at the end.
    

```go
fmt.Print("Namaste") // Output: Namaste
```

* fmt.Println: Similar to fmt.Print, but it appends a newline character at the end of the output.
    

```go
fmt.Println("Namaste", "World") // Output: Namaste World
```

* fmt.Printf: This function allows you to print formatted text based on a format specifier string. It supports placeholders marked with % that are replaced by corresponding values passed as arguments.
    

```go
name := "Albus" 
age := 25 
fmt.Printf("Name: %s, Age: %d\n", name, age) 
// Output: Name: Albus, Age: 25
```

#### Formatting Functions:

* fmt.Sprintf: This function formats and returns a string without printing it to the standard output. It is useful when you need to store the formatted string in a variable.
    

```go
name := "Albus" 
age := 25 
info := fmt.Sprintf("Name: %s, Age: %d", name, age) 
fmt.Println(info) 
// Output: Name: Albus, Age: 25
```

* fmt.Errorf: This function formats an error message and returns an error value. It is often used to create custom error messages.
    

```go
err := fmt.Errorf("Invalid input: %d", 42) 
fmt.Println(err) 
// Output: Invalid input: 42
```

#### Reading Input Functions:

* fmt.Scan: This function reads space-separated values from standard input and assigns them to the provided variables. It returns the number of items successfully scanned.
    

```go
var name string 
var age int 
fmt.Scan(&name, &age) 
fmt.Printf("Name: %s, Age: %d\n", name, age)
```

* fmt.Scanf: This function reads input from standard input based on a format specifier string. It assigns values to variables based on the format specifier placeholders.
    

```go
var name string 
var age int 
fmt.Scanf("Name: %s, Age: %d", &name, &age) 
fmt.Printf("Name: %s, Age: %d\n", name, age)
```

* fmt.Scanln: This function is similar to fmt.Scan, but it reads until a newline character is encountered. It also returns the number of items successfully scanned.
    

```go
var name string 
var age int 
fmt.Scanln(&name, &age) 
fmt.Printf("Name: %s, Age: %d\n", name, age)
```

#### Additional Formatting Options:

The "fmt" package supports a wide range of formatting options using format specifiers.

Some commonly used format specifiers include:

1. %d for integers
    
2. %s for strings
    
3. %f for floating-point numbers
    
4. %t for booleans
    
5. %v for any value
    
6. %T to display the type of a value
    

The format specifiers can be further modified with flags, width, precision, and alignment options to control the appearance of the formatted output.

#### Custom Type Formatting:

The "fmt" package allows you to define custom formatting for your own types by implementing the fmt.Stringer interface or by defining a String() method for the custom type. This enables you to specify how your custom type should be formatted when printed using the "fmt" functions.

### Conclusion

The "fmt" package in Go provides a comprehensive set of functions and methods for formatted input and output operations. It allows you to print values, format strings, and read input from standard input.

With various formatting options and the ability to define custom type formatting, the "fmt" package provides flexibility and convenience for I/O operations in Go programs.