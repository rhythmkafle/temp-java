## Writing Comments

Comments are non-executable lines in code that improves readability and explains the program’s logic. Java supports 3 types of comments:

1. Single Line Comment
    
    ```java
    // This is a single line comment
    ```
    

1. Multi-line Comment
    
    ```java
    /*
    This is a multi line comment
    */
    ```
    
2. Documentation Comment
    
    ```java
    /*
    * This is a 
    * Java Documentation Comment
    */
    ```
    

---

## Primitive Data Types, Variables and Constants

Java has 8 primitive data types, which holds simple values:

  1. Integers

- byte (8 bit)
- short (16 bit)
- int (32 bit)
- long (64 bit)

1. Floating Point
    - float (32 bits)
    - double (64 bit)

1. Character Type
    - char (16 bit)

1. Boolean Type
    - boolean (stores true or false)

### Variables

Variable is a named memory location that stores a value. It must be declared with specific data type.

Syntax:

```java
dataType variableName = value;
```

Eg:

```java
int age = 21;
char grade = 'A';
```

### Constants

A constant is a variable whose value cannot be changed after it has been initialized. In java, `final` keyword is used to declare a constant. 

Eg:

```java
final double PI = 3.14;
```

---

## Type Conversion and Casting

Type conversion is the process of converting one data type into another.

It is of two types:

1. Implicit Conversion
    - It is the automatic conversion from smaller to larger data types.
    - It is also called widening conversion.
    
    Eg:
    
    ```java
    int x = 10;
    double y = x;
    System.out.println(y);
    
    // Output: 10.0 -> because integer value 10 gets converted to double value 10.0
    ```
    

1. Explicit Conversion
    - It is the manual conversion of data types. It may result in data loss.
    - It is also called narrowing conversion.
    
    Eg:
    
    ```java
    double x = 9.8;
    int y = (int)x;
    System.out.println(y)
    // Output: 9 -> Data loss happened as the decimal part (.8) is removed
    ```
    

---

## Operators

Operators are special symbols that helps perform operations on different variables and values. 

The different types of operators in Java are:

1. Arithmetic
    - `+, -, /, *, %`
    
    Eg:
    
    ```java
    int a = 10;
    int b = 5;
    int add = a + b;
    int sub = a - b;
    int div = a/b;
    int mul= a*b;
    int modulo = a%b; // % means modulo i.e.remainder
    ```
    

1. Assignment Operator
    - used to assign values
    - `=, +=, -=, etc`
    Eg:
    
    ```java
    int a = 5;
    x += 3;
    ```
    
2. Unary Operator
    - Such operators only need one operand to perform their function.
    - `++, --, !`
    
    Eg:
    
    ```java
    int a = 5;
    
    a++; // here, we dont need only one operand ('a') to increment the value,
    			// and hence it is an unary operator
    ```
    

1. Relational Operator
    - These operators are used to check for relations like equality, greater than, less than.
    - They return boolean values i.e. `True` if the condition is true, and `False` if otherwise.
    - `==, <, >, <=, >=, !=`
    
    Eg:
    
    ```java
    int a = 10;
    int b = 5;
    
    System.out.println((a>b)); // True
    System.out.println((a<=b)); // False
    ```
    

1. Logical Operators
    - Such operators are used to perform logical operations such as AND and OR.
    - `&&, ||, !`
    
    Eg:
    
    ```java
    System.out.println(True && True); // True
    System.out.println(!True); // False
    ```
    
2. Ternary Operator
    - This operator is the shorthand version of the `if-else` statement.
    - Syntax: `condition ? if true : if false`
    
    Eg:
    
    ```java
    public class Ternary {
      
        public static void main(String[] args)
        {
            int a = 20, b = 10;
            
            (a > b) ? System.out.println("a is greater") : System.out.println("b is greater");
        }
    }
    ```
    

The above code works the same as the below code:

```java
...
int a = 20, b = 10;
if (a>b) {
	System.out.println("a is greater");
} else {
	System.out.println("b is gereater");
}
```

1. Bitwise Operator
    - These are used for performing Binary Operations on values.
    - Types of Bitwise Operators are:
        - **`&` (Bitwise AND):** returns bit-by-bit AND of input values.
        - **`|` (Bitwise OR):** returns bit-by-bit OR of input values.
        - **`^` (Bitwise XOR):** returns bit-by-bit XOR of input values.
        - **`~` (Bitwise Complement):** inverts all bits (one's complement).

## Precedence & Associativity of Operators

Operator precedence determines the order in which operators are evaluated in an expression (e.g., multiplication and division have higher precedence than addition and subtraction). 

Associativity defines the order of evaluation when operators have the same precedence (e.g., most binary operators are left-associative).

Eg:

```java
int eg = 10 + 20 * 3; // here, multiply happens first, and then only addition 
		// happens.
		// This is operator precedence. This is the same as BODMAS rule
		
int eg = 10 * 20 * 30; // here, all operators have the same precedence, so now, 
		// operation occurs from left to right i.e. first 10*20, then only 30
```

---

## Control Statements

Control Flow refers to the order of execution of statements. 

Control Statements are the fundamental components of programming that allows programmer to control the order of execution.

### Conditional Statements

They are used to execute certain blocks of code based on conditions.

1. If statement
    
    ```java
    import java.io.*;
    
    class GFG {
        public static void main(String[] args)
        {
            int a = 5;
            if (a == 5) {
                System.out.println("a is equal to 5");
            }
        }
    }
    ```
    
2. If-else statement
    
    ```java
    import java.io.*;
    
    class GFG {
        public static void main(String[] args)
        {
            int a = 10;
            if (a == 5) {
                System.out.println("a is equal to 5");
            }
            else {
                System.out.println("a is not equal to 5");
            }
        }
    }
    ```
    
3. If-else-If statement
    
    ```java
    import java.io.*;
    
    class GFG {
        public static void main(String[] args)
        {
            int a = 15;
            if (a == 5) {
                System.out.println("a is equal to 5");
            }
            else if (a == 10) {
                System.out.println("a is equal to 10");
            }
            else {
                System.out.println("a is not equal to 5 or 10");
            }
        }
    }
    ```
    
4. Ternary Statement
    
    ```java
    import java.io.*;
    
    class GFG {
        public static void main(String[] args)
        {
            int a = 10;
            System.out.println(a == 5 ? "a is equal to 5"
                                      : "a is not equal to 5");
        }
    }
    ```
    
5. Switch Statement
    
    ```java
    import java.io.*;
    
    class GFG {
        public static void main(String[] args)
        {
            int a = 15;
            switch (a) {
            case 5:
                System.out.println("a is equal to 5");
                break;
            case 10:
                System.out.println("a is equal to 10");
                break;
            default:
                System.out.println("a is not equal to 5 or 10");
            }
        }
    }
    ```
    

### Looping Statements

They are also known as iteration or repetition statements. They are used in programming to repeatedly execute a block of code.

1. For Loop
    
    ```java
    for (int i = 1; i <= 5; i++) {
        System.out.println("Number: " + i);
    }
    ```
    
2. While Loop
    
    ```java
    int count = 5;
    while (count > 0) {
        System.out.println("Count: " + count);
        count--;
    }
    ```
    
3. Do While Loop
    
    ```java
    int count = 0;
    do {
        System.out.println("This will be printed at least once.");
        count++;
    } while (count < 1);
    ```
    
4. For-each loop
    - For-Each loop is a specialized for loop in Java, which is used to loop through the data of an array, or other data structures.
    
    ```java
    String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
    for (String i : cars) {
      System.out.println(i);
    }
    
    ```
    

**Nested Loops**

Nested Loops are loops within a loop. They are used for complex logic and pattern making.

```java
// Outer loop
for (int i = 1; i <= 2; i++) {
  System.out.println("Outer: " + i); // Executes 2 times
  
  // Inner loop
  for (int j = 1; j <= 3; j++) {
    System.out.println(" Inner: " + j); // Executes 6 times (2 * 3)
  }
} 
```

### Jump Statements

Jumping statements are control statements that transfer execution control from one point to another point in the program. There are three Jump statements that are provided in the Java programming language:

1. break
    - terminates the execution of the nearest looping statement or switch statement
    
    ```java
    import java.io.*;
    
    class GFG {
        public static void main(String[] args)
        {
            int n = 10;
            for (int i = 0; i < n; i++) {
                if (i == 6)
                    break;
                System.out.println(i);
            }
        }
    }
    
    Output:
    
    ```
    
2. continue
3. returns