---
title: "Demystifying Makefiles"
datePublished: Tue Feb 27 2024 06:30:06 GMT+0000 (Coordinated Universal Time)
cuid: clt3znax0000809l7gq3ofivw
slug: demystifying-makefiles
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/IB0VA6VdqBw/upload/97643e5c588cebbfa3e25daff16bcfcf.jpeg
tags: software-development, golang, backend, build, makefile

---

Makefiles are often overlooked in the software development process. A Makefile is a script used in software development to automate the process of building and compiling programs. It typically contains a set of rules that define how the source code should be transformed into executable files or libraries. Make, the build automation tool, reads the Makefile and executes the specified commands to carry out the build process.

### What is a Makefile?

A Makefile is fundamentally a simple text file with rules for building and managing a project. Originally used for C projects, Makefiles now work across many programming languages.

The primary purpose of a Makefile is to manage dependencies and streamline the compilation process. It helps ensure that only the necessary portions of the code are recompiled when changes are made, saving time and resources.

Some concepts related to Makefiles that need not be memorised but make life easier if known:

1. **Targets:** A Makefile consists of a set of rules, each specifying a target. A target is typically the name of an executable file or a task to be performed, such as compiling a source file or cleaning up temporary files.
    
2. **Dependencies:** Each target has associated dependencies, which are files or other targets that must be present or built before the target can be successfully executed. Make uses the dependency information to determine the order in which targets should be built.
    
3. **Commands:** For each target, there are one or more commands that are executed when the target is built. These commands are typically shell commands or other build tools that perform tasks like compilation, linking, or copying files.
    
4. **Rules:** A rule consists of a target, its dependencies, and the commands to execute. Rules define the relationships between different components of the project and guide the build process.
    
5. **Variables:** Makefiles often use variables to store values that can be reused throughout the file. This includes compiler flags, file paths, or any other values that may need to be changed across the project.
    
6. **Order-Only Prerequisites:** In addition to regular dependencies, Makefiles support order-only prerequisites. These are dependencies that affect the order of execution but don't trigger a rebuild if they are updated.
    
7. **Recursive Make:** Large projects may be organised into subdirectories, each with its own Makefile. Recursive make involves calling Make on each subdirectory, allowing for a modular and organised build process.
    

### Makefile for a Go(lang) Project

```makefile
# Makefile for a Go Project

# Variables
GOCMD = go
GOBUILD = $(GOCMD) build
GOCLEAN = $(GOCMD) clean
GOTEST = $(GOCMD) test
GOGET = $(GOCMD) get

# Targets
all: build

build:
	$(GOBUILD) -o myapp main.go

test:
	$(GOTEST) ./...

clean:
	$(GOCLEAN)
	rm -f myapp

run:
	$(GOBUILD) -o myapp main.go
	./myapp

.PHONY: all build test clean run
```

#### Explanation:

* `GOCMD` defines the Go command-line tool.
    
* `GOBUILD`, `GOCLEAN`, `GOTEST`, and `GOGET` are variables representing various Go commands for building, cleaning, testing, and getting dependencies.
    
* Targets are defined for different tasks:
    
    * `all` is the default target, in this case, it calls the `build` target.
        
    * `build` compiles the Go code into an executable named `myapp`.
        
    * `test` runs tests in the project.
        
    * `clean` removes the compiled binary.
        
    * `run` builds and then runs the executable.
        

To use this Makefile, you would navigate to the directory containing your Go code and Makefile and then run commands like `make build`, `make test`, `make clean`, or `make run`.

### Conclusion

Makefiles provide a powerful and flexible way to manage the build process in software development. They are particularly useful for projects with multiple source files and complex dependencies. By defining the relationships between different components of a project, Makefiles help developers maintain a structured and efficient build system.