# Chapter 6

- [Chapter 6](#chapter-6)
  - [Predefined Functions](#predefined-functions)
  - [User-Defined Functions](#user-defined-functions)
  - [Value-Returning Functions](#value-returning-functions)
    - [Syntax: Value-Returning Function](#syntax-value-returning-function)
    - [Syntax: Formal Parameter List](#syntax-formal-parameter-list)
    - [Function Call](#function-call)
    - [Syntax: Actual Parameter List](#syntax-actual-parameter-list)
    - [`return` Statement](#return-statement)
    - [Syntax: `return` Statement](#syntax-return-statement)
    - [Function Prototype](#function-prototype)
    - [Syntax: Function Prototype](#syntax-function-prototype)
    - [Value-Returning Functions: Some Peculiarities](#value-returning-functions-some-peculiarities)
    - [More Examples of Value-Returning Functions](#more-examples-of-value-returning-functions)
    - [Flow of Compilation and Execution](#flow-of-compilation-and-execution)
  - [Void Functions](#void-functions)
  - [Value Parameters](#value-parameters)
  - [Reference Variables as Parameters](#reference-variables-as-parameters)
  - [Value and Reference Parameters and Memory Allocation](#value-and-reference-parameters-and-memory-allocation)
  - [Reference Parameters and Value-Returning Functions](#reference-parameters-and-value-returning-functions)
  - [Scope of an Identifier](#scope-of-an-identifier)
  - [Global Variables, Named Constants, and Side Effects](#global-variables-named-constants-and-side-effects)
  - [Static and Automatic Variables](#static-and-automatic-variables)
  - [Debugging: Using Drivers and Stubs](#debugging-using-drivers-and-stubs)
  - [Function Overloading: An Introduction](#function-overloading-an-introduction)
  - [Functions with Default Parameters](#functions-with-default-parameters)

## Predefined Functions

## User-Defined Functions

## Value-Returning Functions

### Syntax: Value-Returning Function

### Syntax: Formal Parameter List

### Function Call

### Syntax: Actual Parameter List

### `return` Statement

### Syntax: `return` Statement

### Function Prototype

### Syntax: Function Prototype

### Value-Returning Functions: Some Peculiarities

### More Examples of Value-Returning Functions

### Flow of Compilation and Execution

## Void Functions

### Function Definition

The function definition for a void function with parameters has the following syntax:

  ```c++
  void functionName(formal, parameters, list) {
    statements
  }
  ```
  
__Statements__ are usually declaration and/or executable statements. Even with the
  formal parameter list being empty, the parenthesis still need to be present.

### Formal Parameter List

The formal parameter list can include value and/or reference parameters.

### Function Call

```c++

```

## Value Parameters

## Reference Variables as Parameters

See the [Value Parameters](#Value-Parameters) section for how value parameters
  work. Because reference parameters _receive the address_ (memory allocation)
  of the actual parameter, they can pass one or more values from a function and
  can change the value of the actual parameter.

Reference parameters are useful in three situations:

- When the value of the actual parameter needs to be changed
- When you want to return more than one value from a function
- When passing the address would save memory space and time relative to copying
    a large amount of data.

Recall that attaching `&` after the `DataType` in the formal parameters list,
  the variable following becomes a reference variable.

## Value and Reference Parameters and Memory Allocation

When a function is called, memory is allocated in the function data areas for
  its formal parameters and local variables.

> Stream variables (including `std::ifstream` and `std::ofstream`) should be
> passed by reference to a function, as the state of the input/output stream
> can then be passed outside the function.

## Reference Parameters and Value-Returning Functions

It _is_ possible to use reference parameters in value-returning functions, but
  not recommended. [Value-returning](#Value-Returning-Functions) functions are,
  by definition, only to return one value. If more than one value is needed to
  be returned, change it to a void function and use reference parameters to
  return the values.

## Scope of an Identifier

The __scope__ of an identifier refers to where in the program an identifier is
  accessible (visible).

Some definitions:

- __Local Identifier__: Identifiers declared within a function (or block)
  - Not accessible outside function block
- __Global Identifier__: Identifiers declared outside of every function
  definition

Now, to define their scope:

1. Global Identifiers (such as variables) are accessible by a function/block if:
   - Identifier is declared before the function/block
   - The function name is different than the identifier
   - All parameters of the function have different names than the identifier
   - All local variables have different names than the identifier
2. __(Nested Block)__ An identifier declared within a block is accessible:
   - Only within the block from the point at which it is declared until its end
   - By those blocks that are nested within that block if it does not have an
      identifier of the same name.
3. The scope of a function name is similar to the scope of an identifier
    declared outside any block. That is, the scope of a function name is the same
    as the scope of a global variable.

Some things to note about global variables:

1. C++ does not automatically initialize variables. Some compilers, however,
    initialize _global_ variables to their default.
2. In C++, `::` is called the __scope resolution operator__. For an example, the
    `main()` function can reference global variable `z` as `z` or `::z`.
3. There is a way to access a global variable declared after the definition of
    a function. The function must not contain the identifier with the same name
    as the global variable. The reserved word `extern` is used for this. It
    announces a global variable and is used like so:
    ```c++
    extern int identifier;
    ```

## Global Variables, Named Constants, and Side Effects

Using global variables has side effects. If more than one function is using
  the same global variable and something is to go wrong, it is difficult to
  debug what went wrong where.

## Static and Automatic Variables

So far, we have learned two simple rules regarding variables:

1. Memory for a global variable remains allocated as long as the program
    executes.
2. Memory for a variable declared within a block is allocated at block entry and
    deallocated at block exit.

A variable for which memory is allocated at block entry and deallocated at block
  exit is called an __automatic variable__. A variable for which memory is
  allocated as long as the program executes is called a __static variable__.
  Static variables are declared using the C++ reserved word `static`.

As memory for static variables remains allocated between function calls, static
  variables allow the use of the value from one function call to another. Local
  scope will prevent the functions from manipulating the global variables value.

## Debugging: Using Drivers and Stubs

Usually when a program contains a lot of functions each one is tested
  individually on its own. __Driver__ programs are what is used to test a
  function. If a function depends on the results calculated by another function,
  that function cannot be tested alone as it has _dependencies_.

Function __stubs__ are functions not fully written. A `void` function stub may
  simply be a function header with a set of empty braces. For a value-returning
  function, it may contain only a `return` statement with an easy-to-use return
  value. For example:

  ```c++
  double pool_capacity(double len, double width, double dep) {
    return 1000.00;
  }
  ```

## Function Overloading: An Introduction

In C++, several functions can have the same name and this is called
  __function overloading__. Before going into the rules of overloading, note the
  following:

Two functions are said to have different formal parameter lists if both
  functions have:

- A different number of formal parameters _or_
- The same number of formal parameters and data types but differ in at least one
    position in the order listed.

When a function is overloaded and called, the parameter list decides which
  function to execute. It is used when you have the same action for different
  sets of data.

## Functions with Default Parameters

Default parameters are specified in the function prototype. In general, these
  rules apply to functions with default parameters:
  
- If you do not specify the value of a default parameter, the default value is
  used for that parameter.
- All of the default parameters must be the far-right parameters of the function
- Suppose a function has more than one default parameter. In a function call, if a
  value to a default parameter is not specified, then you must omit all of the
  arguments to its right.
- Default values can be constants, global variables, or function calls.
- The caller has the option of specifying a value other than the default for any
  default parameter.
- You cannot assign a constant value as a default value to a reference parameter.
