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
