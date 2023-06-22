---
title: "Variadic Operator in Golang"
datePublished: Thu Jun 22 2023 04:30:42 GMT+0000 (Coordinated Universal Time)
cuid: clj6nastu06xo0fnv6xjqhqax
slug: variadic-operator-in-golang
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/nhX8QhXMBkM/upload/55283bcd33f252155302c8aa0a3f0dac.png
tags: go, google, functional-programming, golang-developer, variadicfunctions

---

Big words, which basically mean "many arguments"...

The variadic operator (...) allows functions to accept a variable number of arguments of the same type. It provides a flexible and convenient way to work with a varying number of inputs.

### Syntax

The variadic operator is denoted by three dots (...) placed after the type of the parameter in a function signature. It can only be used for the final parameter of a function. The variadic parameter acts as a slice, allowing you to pass any number of values of the specified type.

```go
func aFunction (values ...int) { 
    // Function body 
}
```

#### Variadic Function Call

When calling a variadic function, you can provide any number of arguments of the specified type. The variadic operator allows you to pass multiple values without explicitly creating a slice or specifying the number of arguments.

```go
aFunc(1, 2, 3, 4, 5) // Passing multiple values 
aFunc() // Passing zero values 
aFunc(slice...) // Passing a slice of values
```

#### Accessing Variadic Arguments:

Inside the function, the variadic parameter is treated as a slice, allowing you to access individual values using indexing or iteration.

```go
func printNumbers(numbers ...int) { 
    for _, num := range numbers { 
        fmt.Println(num) 
    } 
}
printNumbers(1, 2, 3, 4, 5)
```

#### Empty Variadic Parameter

It is valid to call a variadic function without providing any arguments. In this case, the variadic parameter will be an empty slice.

```go
func aFunc(values ...string) { 
    // Function body 
}
aFunc() // values will be an empty slice
```

#### Mixing Variadic and Regular Parameters

A function can have both variadic and regular parameters. Variadic parameters should be the last parameter in the function signature.

```go
func greet(prefix string, names ...string) { 
    for _, name := range names { 
        fmt.Println(prefix, name) 
    } 
}
greet("Namaste", "Albus", "Bhavesh", "Ciara")
// Namaste Albus
// Namaste Bhavesh
// Namaste Ciara
```

### Variadic Arguments with a Slice

If you have a slice and want to pass its values as variadic arguments, you can use the ... operator to unpack the slice.

```go
numbers := []int{1, 2, 3, 4, 5} 
aFunc(numbers...) 
// Unpacking the slice and passing as variadic arguments
```

#### Creating a Slice from Variadic Arguments

If you have a function that accepts variadic arguments and you want to convert those arguments into a slice, you can do so using the variadic... syntax.

```go
func createSlice(values ...int) []int { 
    return values 
} 
numbers := createSlice(1, 2, 3, 4, 5) 
// numbers is a slice containing [1, 2, 3, 4, 5]
```

#### Mixing Variadic Arguments and Slices

You can pass variadic arguments along with regular slices as separate arguments to a function.

```go
func aFunc(numbers ...int) { 
    // Function body 
}
func anotherFunc(slice []int, values ...int) { 
    // Function body 
}
numbers := []int{1, 2, 3} 
aFunc(4, 5, 6) // Variadic arguments 
anotherFunc(numbers, 7, 8, 9) // Slice and variadic arguments
```

Using the variadic operator with slices provides a convenient way to work with existing slices as variadic arguments. It eliminates the need to manually unpack the slice and allows for a more concise and expressive code. This feature enhances the flexibility and usability of variadic functions when working with slices in Go.

### Conclusion

The variadic operator in Go allows us more flexibility in function design, enabling functions to accept a variable number of arguments. It simplifies the calling code for us by eliminating the need to manually create a slice or specify the number of arguments.

The most common, but unobvious use case of a variadic function is the `(fmt.Printf)` , we use for consoling. It is a function too, which takes in an indefinite amount of arguments. It blew my mind when I first made that connection. Hope you had that "aha" moment as well...