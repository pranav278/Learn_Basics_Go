# Go intro
Go, also known as Golang, is a programming language developed by Google

## What is Go
- Statically typed, compiled language

- Designed by Robert Griesemer, Rob Pike, and Ken Thompson at Google

- Built-in and semi-easy-to-use concurrency (Goroutines)

- Easy to compile and build executables/packages

## Why Go

- Designed for systems to be faster than C 

- Ended up being a great all-around language for systems, apps, and even automation

- It's like writing C in Python

- Go has it's own garbage collection and is more concise than C

- Strongly typed language


## What Is Written In Go

- Kubernetes

- Terraform

- Docker

- etcd

## Cross Platform

- WINDOWS

- MACOS

- LINUX (ALL FLAVORS)

## Go Is Not Object Oriented

- There aren't objects like in, for example, C#

- Go doesn't have an Object type (structs in Go aren't objects), Classes, or Inheritance (no classes, so no basing objects on other object)

- The closest thing you'll get to Objects in Go is a type/struct

## Go.mod File

- Dependency management. If you're familiar with Python, think of the requirements.txt file

- Helpful commands; `go mod tidy': Ensures the go.mod file matches the source code in the module 

## Go.sum File

- Generated file that you don't have to manage

- go.sum file maintains the checksum so when you run the project again it will not install all packages again.

## what is exactly these files are ?
Absolutely, you've provided a succinct overview of the `go.mod` and `go.sum` files in Go, and their role in dependency management. Let's delve a bit deeper into these aspects:

### go.mod File:

1. **Dependency Management:**
   - The `go.mod` file serves as the module definition for a Go project. It includes metadata about the project, such as the module name, Go version compatibility, and most importantly, the dependencies required by the project.

2. **Similar to requirements.txt in Python:**
   - Much like `requirements.txt` in Python or `package.json` in Node.js, the `go.mod` file lists the dependencies and their versions that are needed for the project. This ensures reproducibility across different development environments.

3. **go mod tidy:**
   - The `go mod tidy` command is used to clean up the `go.mod` file. It ensures that the `go.mod` file accurately reflects the dependencies used in the code. Unused dependencies are removed, and missing ones are added.

### go.sum File:

1. **Checksum Management:**
   - The `go.sum` file is a generated file that contains checksums for specific module versions. It ensures the integrity and security of the dependencies. The checksums are cryptographic hashes generated from the content of the module's source code.

2. **Prevents Redundant Downloads:**
   - When you build your project or run it again, Go checks the `go.sum` file to verify that the downloaded dependencies match the expected checksums. If they match, Go doesn't need to download the dependencies again, which helps in saving bandwidth and time.

3. **Automatic Maintenance:**
   - Developers typically don't need to manually manage the `go.sum` file. It's automatically updated by the Go toolchain when you add or update dependencies using commands like `go get` or `go mod tidy`.

In summary, the `go.mod` file is the central file for defining dependencies and metadata for a Go project, while the `go.sum` file ensures the security and integrity of the dependencies by maintaining checksums. Together, they provide an effective and automated way to manage dependencies in Go projects.


## Some common data types in programming
specifically in the context of Go (Golang). Let's expand a bit on each of these, and then I'll touch on more advanced types based on the link you shared.

### Basic Data Types:

1. **String:**
   - Represents a sequence of characters. In Go, strings are immutable, meaning their values cannot be changed after they are created.

   ```go
   var myString string = "This is a string"
   ```

2. **Bool:**
   - Represents a boolean value, which can be either `true` or `false`.

   ```go
   var isTrue bool = true
   ```

3. **Int:**
   - Represents integer numbers. It can be either signed (positive or negative) or unsigned (only positive).

   ```go
   var myInt int = 42
   ```

4. **Floats:**
   - Represents floating-point numbers, which have decimal points.

   ```go
   var myFloat float64 = 1.2
   ```

### More Advanced Types:

The link you provided discusses more advanced types in Go. Here are some of them:

1. **Structs:**
   - Allow you to create complex data types by grouping together variables of different types under a single name.

   ```go
   type Person struct {
       Name string
       Age  int
   }
   ```

2. **Arrays and Slices:**
   - Arrays are fixed-size sequences of elements, while slices are more flexible and can dynamically resize.

   ```go
   var myArray [3]int
   mySlice := []int{1, 2, 3}
   ```

3. **Maps:**
   - Represents an unordered collection of key-value pairs.

   ```go
   myMap := map[string]int{"a": 1, "b": 2}
   ```

4. **Pointers:**
   - Hold the memory address of a variable. They are used to indirectly access the value of a variable.

   ```go
   var x int = 42
   var pointerToX *int = &x
   ```

5. **Interfaces:**
   - Defines a set of methods that a type must implement. It allows you to write more flexible and reusable code.

   ```go
   type Shape interface {
       Area() float64
   }
   ```

6. **Channels:**
   - Used for communication between goroutines in concurrent programming.

   ```go
   myChannel := make(chan int)
   ```

These advanced types in Go provide a powerful set of tools for structuring and organizing data in your programs, as well as for handling more complex programming scenarios.

# Go Structure

In Go, the structure of a project is determined by its directory layout and the use of certain files. While Go does not enforce a strict project structure, there are conventions that many developers follow for consistency and organization. Below is a typical directory structure for a Go project:

```
myproject/
|-- cmd/
|   |-- myapp/
|       |-- main.go
|
|-- internal/
|   |-- pkg1/
|       |-- pkg1.go
|   |-- pkg2/
|       |-- pkg2.go
|
|-- pkg/
|   |-- sharedpkg/
|       |-- sharedpkg.go
|
|-- api/
|   |-- openapi.yaml
|
|-- web/
|   |-- static/
|   |-- templates/
|
|-- config/
|   |-- config.yaml
|
|-- scripts/
|   |-- build.sh
|   |-- deploy.sh
|
|-- go.mod
|-- go.sum
|-- README.md
```

Explanation of the directories and files:

- **`cmd/`**: This directory typically contains the main applications or executable entry points for your project. Each subdirectory under `cmd/` represents a different application.

- **`internal/`**: This directory is reserved for packages that are only used by your project and not intended for use by other projects. The contents of `internal/` are not exposed to external dependencies.

- **`pkg/`**: The `pkg/` directory is used for libraries or packages that are intended for use by other projects. It contains shared code that can be imported by external packages.

- **`api/`**: This directory may contain API specifications, such as OpenAPI or Swagger files, describing your project's API.

- **`web/`**: This directory is often used for web-related assets, such as static files and templates.

- **`config/`**: Configuration files for your project, such as YAML or JSON files, can be placed in this directory.

- **`scripts/`**: Shell scripts or other automation scripts used for building, testing, or deploying your project.

- **`go.mod`**: The `go.mod` file is used to define and manage the project's dependencies and modules.

- **`go.sum`**: The `go.sum` file, as mentioned earlier, maintains cryptographic checksums for the dependencies specified in `go.mod`.

- **`README.md`**: A README file providing documentation and information about the project.

This structure is just an example, and the actual layout may vary based on the project's nature and requirements. Additionally, some projects may not have all these directories or may have additional directories based on specific needs. It's essential to follow the conventions that make sense for your project and team while considering factors like maintainability, readability, and scalability.


## Function Structure

Certainly! Let's break down the structure of a function in Go in a simple way:

```go
func addNumbers(a int, b int) int {
    sum := a + b
    return sum
}

func main() {
    result := addNumbers(3, 5)
    fmt.Println(result)
}
```

1. **Function Declaration (`func`):** The `func` keyword is used to declare a function.

2. **Function Name (`addNumbers`):** This is the name of the function. In this case, it's `addNumbers`.

3. **Parameters (`a int, b int`):** Inside the parentheses, you declare the parameters that the function takes. Each parameter has a name (`a` and `b` in this example) and a type (`int` for integer in this case).

4. **Return Type (`int`):** After the parameter list, you specify the type of value that the function will return. In this case, the function returns an integer (`int`).

5. **Function Body (`{ ... }`):** The body of the function contains the code that gets executed when the function is called. In this example, it calculates the sum of the two input numbers (`a` and `b`).

6. **Return Statement (`return sum`):** The `return` keyword is used to send a value back from the function. Here, it returns the calculated sum.

7. **Function Call (`addNumbers(3, 5)`):** In the `main` function, we call `addNumbers` with arguments `3` and `5`. This means `a` becomes `3` and `b` becomes `5` inside the `addNumbers` function.

8. **Printing Result (`fmt.Println(result)`):** Finally, we print the result of the function (the sum) using `fmt.Println`.

In summary, a Go function is like a little block of code that you define with a name, input parameters, a specific task (the code inside the function), and, if needed, a result that it gives back. Functions help organize and reuse code in a program.


## Variables

In Go (Golang), variables are used to store and manage data. Here's an overview of how variables work in Go, covering full variable declarations, global variables, and short variable declarations:

### Full Variable Declarations:

1. **Syntax:**
   ```go
   var variableName dataType
   ```

2. **Example:**
   ```go
   var age int
   age = 25
   ```

   In this example, we declare a variable named `age` of type `int` and assign the value `25` to it.

### Global Variables:

1. **Declaration Outside Functions:**
   ```go
   var globalVariable int = 10
   ```

2. **Example:**
   ```go
   package main

   import "fmt"

   var globalVariable int = 10

   func main() {
       fmt.Println(globalVariable)
   }
   ```

   The `globalVariable` is declared outside any function and is accessible throughout the package.

### Short Variable Declarations:

1. **Syntax:**
   ```go
   variableName := value
   ```

2. **Example:**
   ```go
   func main() {
       name := "John"
       age := 30
       fmt.Println(name, age)
   }
   ```

   In this example, variables `name` and `age` are declared and initialized using the short variable declaration syntax.

### Multiple Short Variable Declarations:

1. **Syntax:**
   ```go
   variable1, variable2 := value1, value2
   ```

2. **Example:**
   ```go
   func main() {
       city, population := "New York", 8500000
       fmt.Println(city, population)
   }
   ```

   Here, `city` and `population` are declared and assigned values in a single line.

### Blank Identifier:

1. **Used to Discard Values:**
   ```go
   _, result := someFunction()
   ```

   In this example, we use the underscore (`_`) as a blank identifier to discard a return value from `someFunction()`.

### Constants:

1. **Declaration:**
   ```go
   const pi = 3.14159
   ```

   Constants are declared using the `const` keyword and must be assigned a value at the time of declaration.

### Notes:

- In Go, variables must be used once declared; otherwise, the code won't compile.
- Variable names must start with a letter and can contain letters, numbers, and underscores.
- The type of a variable can be explicitly specified, or it can be inferred by the compiler based on the assigned value.

These examples cover the basics of declaring and using variables in Go. It's important to understand the scope of variables, which is determined by where they are declared within the code. Global variables have package-level scope, while variables declared within functions are local to those functions.

## Constants
In Go, constants are values whose values cannot be changed once they are assigned during the compilation process. Constants in Go are declared using the `const` keyword. Here's an overview of how constants work in Go:

### Declaration:

```go
const pi = 3.14159
```

In this example, a constant named `pi` is declared with the value `3.14159`. Constants must be assigned a value at the time of declaration, and their values cannot be modified later in the program.

### Typed Constants:

You can explicitly specify the type of a constant:

```go
const myConst int = 42
```

### Enumeration with Constants:

Constants can be used for enumeration-like constructs:

```go
const (
    Monday    = 1
    Tuesday   = 2
    Wednesday = 3
    // ...
)
```

In this example, each day is assigned a unique constant value.

### Enumeration with `iota`:

The `iota` identifier is used to create a sequence of related constants:

```go
const (
    Sunday = iota
    Monday
    Tuesday
    Wednesday
    Thursday
    Friday
    Saturday
)
```

Here, `iota` starts at 0 and increments by 1 for each subsequent line.

### Untyped Constants:

Constants in Go can be untyped, and their types are determined by the context in which they are used:

```go
const x = 42
const y float64 = x
```

In this example, `y` is implicitly typed as `float64` because it's assigned the value of `x`, which is an untyped constant.

### Use Cases:

1. **Mathematical Constants:**
   ```go
   const pi = 3.14159
   const e = 2.71828
   ```

2. **Flag Values:**
   ```go
   const (
       FlagRead  = 1 << iota // 1
       FlagWrite              // 2
       FlagExecute            // 4
   )
   ```

   This is an example of using bitwise operators with constants.

3. **Days of the Week:**
   ```go
   const (
       Sunday = iota
       Monday
       Tuesday
       Wednesday
       Thursday
       Friday
       Saturday
   )
   ```

   Here, `iota` is used for a sequence of related constants.

### Note:

- Constants in Go are a compile-time concept, and they are evaluated and replaced with their values during the compilation process.
- Typed constants provide additional type safety.
- The `iota` identifier simplifies the creation of sequences of related constants.

Constants are useful for defining values that should not change during the execution of a program and for creating symbolic names for constant values.


## Pointer 
Let's break down the concepts:

1. **Memory Location where Data is Stored:**
   - A pointer in Go stores the memory address of a variable rather than the actual value.
   - When you have a variable, its value is stored in a specific memory location, and a pointer is a variable that holds the memory address of another variable.

2. **Memory Address Representation (e.g., 0x7fffa0757dd4):**
   - Memory addresses in Go are typically represented in hexadecimal format.
   - Example: `0x7fffa0757dd4` is the hexadecimal representation of a memory address.

3. **Dereferencing a Pointer (`*ptr`):**
   - To access the value stored at the memory address pointed to by a pointer, you use the `*` operator.
   - For example, if `ptr` is a pointer, `*ptr` gives you the value stored at the memory address held by `ptr`.

4. **Address of Variable (`&var`):**
   - The `&` operator is used to get the memory address of a variable.
   - Example: If `var` is a variable, `&var` gives you the memory address where its value is stored.

5. **Storing a Memory Address (`var := &otherVar`):**
   - You can assign the memory address of a variable to a pointer variable.
   - Example: `var` is a pointer variable, and `otherVar` is a variable. `var := &otherVar` assigns the memory address of `otherVar` to `var`.

6. **Stores a Memory Address, Stores a Value:**
   - A pointer variable stores a memory address.
   - The value stored at that memory address can be accessed or modified using the pointer.

Here's a small example in Go:

```go
package main

import "fmt"

func main() {
    var num int = 42
    var ptr *int // Declare a pointer variable

    ptr = &num   // Assign the memory address of num to ptr

    fmt.Println("Value of num:", num)
    fmt.Println("Memory address of num:", &num)
    fmt.Println("Value stored at memory address (dereferenced):", *ptr)
    fmt.Println("Memory address stored in ptr:", ptr)
}
```

In this example, `ptr` is a pointer variable that stores the memory address of `num`. The `*ptr` expression gives the value stored at that memory address. The output will show the value of `num`, its memory address, the dereferenced value, and the memory address stored in `ptr`.
