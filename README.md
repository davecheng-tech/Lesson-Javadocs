# Javadocs

When writing methods, it’s important that others — or future you! — can understand what they do. Javadocs are the official, structured format for documenting Java methods, classes, and libraries.

They serve two purposes:

1. They help humans understand your code.
2. Tools (like VS Code, IntelliJ, and Javadoc generators) can extract them to produce documentation pages.

Javadocs look something like this:

```java
/**
 * Prints a line containing the given number of stars.
 * @param length how many stars to print
 */
private void starLine(int length) {
    for (int i = 0; i < length; i++) {
        System.out.print("*");
    }
    System.out.println();
}
```

## What Are Javadocs?

Javadocs give programmers a consistent, structured way to document:

- what a method does  
- what each parameter means  
- what value is returned  

Because the format is standardized, IDEs with advanced Java language support can display pop‑up documentation when a method is hovered or called, like this:

![javadocs](.media/01.png)

In short, Javadocs are structured comments that describe how to use a method.

## What Javadocs Contain

A Javadoc block typically includes:

- A summary sentence  
- One `@param` tag per parameter  
- One `@return` tag for return methods  

### Examples of Javadocs
Here are some examples of methods and corresponding Javadocs:

#### No return value, one parameter
```java
/**
 * Prints a line containing the given number of stars.
 * @param length how many stars to print
 */
private void starLine(int length) {
    for (int i = 0; i < length; i++) {
        System.out.print("*");
    }
    System.out.println();
}
```

#### Multiple parameters
```java
/**
 * Returns the larger of two integers.
 * @param a the first number
 * @param b the second number
 * @return the larger of a and b
 */
private int max(int a, int b) {
    if (a > b) {
        return a;
    } else {
        return b;
    }
}
```

#### More complex logic
```java
/**
 * Counts how many vowels appear in the given uppercase string.
 * @param word the string to examine; should be uppercase
 * @return the number of vowels (A, E, I, O, U)
 */
private int countVowels(String word) {
    int count = 0;
    for (int i = 0; i < word.length(); i++) {
        char c = word.charAt(i);
        if ("AEIOU".indexOf(c) != -1) {
            count++;
        }
    }
    return count;
}
```

#### Making improvements
This example repeats the method name with no meaningful description. No mention of parameter or return values below:

```java
/**
 * Checks for even.
 */
private boolean isEven(int n) {
    return n % 2 == 0;
}
```

A much better version would look like this:
```java
/**
 * Determines whether the given integer is divisible by 2.
 * @param n the number to evaluate
 * @return true if n is an even number, false otherwise
 */
private boolean isEven(int n) {
    return n % 2 == 0;
}
```


## When Should You Use Javadocs?

### Simple methods

If a method is small, obvious, and has no parameters or return values, a short single-line comment is fine:

```java
// Draws a simple tree shape
public void drawTree() {
    rect(200, 400, 30, 90);
    ellipse(215, 360, 100, 100);
}
```

### Methods with parameters or return values

These should **always** have Javadocs so users understand how to call them correctly:

```java
/**
 * Returns true if the number is even.
 * @param n the integer to check
 * @return true if n is even; false otherwise
 */
private boolean isEven(int n) {
    return n % 2 == 0;
}
```

### Methods with non-obvious logic

Document methods that have:

- loops  
- conditions  
- non-obvious logic  

### In Summary

#### Use single-line comments for:
- simple drawing helpers
- trivial one-liners
- methods with no parameters or return values that are obvious from their name

#### Use full Javadocs for:
- any method with parameters  
- any method with a return value  
- any method involving clear logic or validation  
- any method meant for reuse  


<br>

# Practice Problems — Javadocs

Complete the following problems using the concepts from today’s lesson.

## Problem 1 — Add Javadocs to Simple Methods
Write proper Javadoc comments above each of the following simple methods.

```java
private int triple(int n) {
    return n * 3;
}

private boolean isUppercase(String s) {
    return s.equals(s.toUpperCase());
}
```

## Problem 2 — Javadocs with Multiple Parameters
Add full Javadocs describing the behaviour, parameters, and return value.

```java
private int max3(int a, int b, int c) {
    int max = a;
    if (b > max) max = b;
    if (c > max) max = c;
    return max;
}
```

## Problem 3 — Javadocs for Non-Obvious Logic
Write complete Javadocs explaining what *really* happens.

```java
private boolean hasVowel(String word) {
    for (int i = 0; i < word.length(); i++) {
        char c = Character.toUpperCase(word.charAt(i));
        if ("AEIOU".indexOf(c) != -1) {
            return true;
        }
    }
    return false;
}
```

## Problem 4 — Write Both the Javadocs and the Method
Write the missing method and its complete Javadocs.  
The method returns the first 3 characters of `s` repeated `times` times.  
Assume `s` has at least 3 characters.

```java
/**
 * TODO: Write full Javadocs here.
 */
private String frontTimes(String s, int times) {
    // TODO
}
```

