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
