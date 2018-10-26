# Chapter 5

- [Chapter 5](#chapter-5)
  - [`while` Looping Structure](#while-looping-structure)
    - [Designing `while` loops](#designing-while-loops)
    - [Count-Controlled `while` Loops](#count-controlled-while-loops)
    - [Sentinel-Controlled `while` Loops](#sentinel-controlled-while-loops)
    - [Flag-Controlled `while` Loops](#flag-controlled-while-loops)
    - [EOF-Controlled `while` Loops](#eof-controlled-while-loops)
      - [eof Function](#eof-function)
    - [More on Expressions in `while` Statements](#more-on-expressions-in-while-statements)
  - [`for` Looping Structure](#for-looping-structure)
  - [`do... while` Looping Structure](#do-while-looping-structure)
    - [Choosing the Right Looping Structure](#choosing-the-right-looping-structure)
  - [`break` and `continue` Statements](#break-and-continue-statements)
  - [Nested Control Structures](#nested-control-structures)
  - [Avoiding Bugs by Avoiding Patches](#avoiding-bugs-by-avoiding-patches)
  - [Debugging Loops](#debugging-loops)

## `while` Looping Structure

Looping structures allow you to repeat a statement until a certain condition is
  met. The general form for a `while` statement is:

  ```c++
  while (expression) {
    statement
  }
  ```

Here is an implementable example:

  ```c++
  int i = 0;

  while (i <= 20) {
    cout << i << " ";
    i = i + 5;
  }

  cout << '\n';
  ```

### Designing `while` loops

The body of the `while` executes only when the __expression__ in the while
  statement evaluates to `true`. Typically, it checks a variable called the
  __loop control variable (LCV)__ and sees if it satisfies conditions.

### Count-Controlled `while` Loops

### Sentinel-Controlled `while` Loops

### Flag-Controlled `while` Loops

### EOF-Controlled `while` Loops

#### eof Function

### More on Expressions in `while` Statements

## `for` Looping Structure

## `do... while` Looping Structure

### Choosing the Right Looping Structure

## `break` and `continue` Statements

## Nested Control Structures

## Avoiding Bugs by Avoiding Patches

## Debugging Loops
