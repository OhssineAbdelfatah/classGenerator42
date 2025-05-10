# generate_class

A simple command-line tool written in Python to generate C++ class files (`.hpp` and `.cpp`) with the Orthodox Canonical Form.

## Features

- Generates a header file (`ClassName.hpp`) with:
  - Proper header guards.
  - Constructor, destructor, copy constructor, and copy assignment operator declarations.
  - A placeholder for private member variables.
- Generates a source file (`ClassName.cpp`) with:
  - Definitions of the constructor, destructor, copy constructor, and assignment operator.
  - Placeholder comments for implementations.

## Installation

1. Clone the repository or download the script.
2. Make the script executable:
   ```bash
   chmod +x generate_class


3. Move the script to a directory in your PATH:

```bash
mv generate_class ~/.local/bin/
```
Ensure ~/.local/bin is in your PATH by adding the following line to your .zshrc (if it's not already there):

```bash
export PATH="$HOME/.local/bin:$PATH"
Reload your shell:
```

```bash
source ~/.zshrc
```

## Usage

1. Basic Usage

To generate class files for a class named MyClass:

```bash
generate_class MyClass
```

This creates:

MyClass.hpp with the class declaration.

MyClass.cpp with the class definition.

2. Chain with Additional Commands

You can chain additional commands after generating the files. For example, to compile the class immediately:

```bash
generate_class MyClass g++ -o MyClass MyClass.cpp
To open the files in an editor (e.g., vim or code):
``

```bash
generate_class MyClass code MyClass.cpp MyClass.hpp
```

## Help

If you need usage information:

```bash
generate_class --help
Example Output
```

MyClass.hpp

```cpp
#ifndef MYCLASS_HPP
#define MYCLASS_HPP

class MyClass {
public:
    MyClass();
    ~MyClass();

    MyClass(const MyClass& other);
    MyClass& operator=(const MyClass& other);

private:
    // Add member variables here
};
#endif // MYCLASS_HPP
```


MyClass.cpp

```cpp
#include "MyClass.hpp"

MyClass::MyClass() {
    // Constructor implementation
}

MyClass::~MyClass() {
    // Destructor implementation
}

MyClass::MyClass(const MyClass& other) {
    // Copy constructor implementation
}

MyClass& MyClass::operator=(const MyClass& other) {
    // Copy assignment operator implementation
    if (this != &other) {
        // Perform deep copy
    }
    return *this;
}
```

## Contributing

Contributions are welcome! Feel free to open issues or submit pull requests.
