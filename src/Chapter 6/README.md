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
  not recommended. [Value-returning](#Value-Returning-Functions) funtions are,
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

## Global Variables, Named Constants, and Side Effects

## Static and Automatic Variables

## Debugging: Using Drivers and Stubs

## Function Overloading: An Introduction

## Functions with Default Parameters
