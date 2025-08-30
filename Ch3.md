### Procedural vs Object Oriented

Procedural programming is about writing procedures or methods that perform operations on the data, while object-oriented programming is about creating objects that contain both data and methods.

Object-oriented programming has several advantages over procedural programming:

- OOP is faster and easier to execute
- OOP provides a clear structure for the programs
- OOP helps to keep the Java code DRY "Don't Repeat Yourself"
- OOP makes it possible to create full reusable applications with less code and shorter  time

---

## Object Oriented Principles

1. Abstraction
    
    Abstraction is a process of hiding implementation details and exposing only the functionality to the user. In abstraction, we deal with ideas and not events. This means the user will only know “what it does” rather than “how it does”.
    
    There are two ways to achieve abstraction in Java:
    
    - Abstract class (0 to 100%)
    - Interface (100%)
    
2. Encapsulation
    
    Encapsulation is the process of wrapping code and data together into a single unit.
    
3. Inheritance
    
    Inheritance is the process of one class inheriting properties and methods from another class in Java. Inheritance is used when we have is-a relationship between objects.  Inheritance in Java is implemented using extends keyword.
    
4. Polymorphism
    
    Polymorphism is the ability to perform many things in many ways. The word Polymorphism is from two different Greek words- poly and morphs. “Poly” means many, and “Morphs” means forms.
    
    There are two types of polymorphism as listed below:
    
    1. Static or Compile-time Polymorphism
    2. Dynamic or Run-time Polymorphism

---

## Classes, Variables and Methods

A **class** is a blueprint or a template for creating objects. It defines the structure and behavior that all objects of that class will have.

```java
public class ClassName {
	// variables
	// methods
}
```

Example Syntax:

A class consists of variables and methods. In class, variables are also called `attributes`. 

Methods are the actions, functions that a class can perform.

Eg of class, methods and variables:

```java
public class Dog {
    // Variables (fields/attributes)
    String breed;
    int age;

    // Method (functions)
    public void bark() {
        System.out.println("Woof!");
    }
}
```

---

## Creating Objects and Accessing Class Members

Object is an instance of the class. Objects are used to access the methods and variables declared inside a class. 

We can create a new object by using the `new` keyword.

Example Syntax:

```java
ClassName objectName = new ClassName();
```

Example:

```java
Dog myDog = new Dog(); // Creating an object
myDog.breed = "Labrador"; // Accessing a variable
myDog.bark(); // Calling a method
```

---

## Method Parameters and Return Types

Parameters are the placeholders for the values that a method takes. Arguments are the values that are passed to a method from a constructor. 

Example of parameter:

```java
public class Main {
  static void myMethod(String fname) {  // fname is parameter of String data type
    System.out.println("Hello " + fname); 
  }

  public static void main(String[] args) {
    myMethod("Ram"); // Ram is an argument
    myMethod("Shyam");  // Shyam is an argument
    myMethod("Hari");  // Hari is an argumenet
  }
}
// Hello Ram
// Hello Shyam
// Hello Hari
```

We need to specify the data types while declaring a parameter. Example, in the above code, `String fname` , `fname` is specified as a `String` .

**Note: If we pass just primitive data type values in parameters, nothing is changed. But If we pass object, then the value will be updated as the object reference is copied.**

Example:

```java
void change(int a) {
    a = 10;
}

int a = 5;
change(a);   // a is still 5 (unchanged)
// Here, remember that int a inside change() method and int a outside change() 
// method are two different variables. They are not the same. So, change made
// inside the method will not affect the actual variable.

// For Object:
void changeName(Student s) {
    s.name = "Updated";
}

Student st = new Student("Rhythm");
changeName(st);
System.out.println(st.name);  // "Updated"

// Here, The parameter inside changeName is Student s, which is an object, not 
// the regular data type. When we pass st as an argument, we are not passing a copy
// but the actual reference of the object. Hence, the value gets changed in real.
```

### Varargs

Sometimes, we do not know how many parameters are required. In such cases we can use `varargs`.  `varargs` means variable arguments, are denoted by … and can store any number of variables.

```java
int sum(int... numbers) {
    int result = 0;
    for (int n : numbers) {
        result += n;
    }
    return result;
}

System.out.println(sum(1, 2, 3, 4)); // 10
System.out.println(sum(1, 2, 3, 4, 5)); // 15
```

### final parameters

If we declare a variable as `final`,its value cannot be reassigned within the method:

```java
void print(final int x) {
    // x = 20; // ❌ Not allowed
    System.out.println(x);
}
```

### Return Types

In Java, every method has a  return type, which will tell what kind of values will be returned once the method is called. 

Eg: returning an integer value:

```java
int add(int a, int b) {
    return a + b;
}
```

Eg: returning a string value:

```java
String greet(String name) {
    return "Hello, " + name;
}
```

We can return any sort of data, and objects using `return` keyword. If there is no return type specified, it returns `void` i.e. nothing.

Eg:

```java
void printHello() {
    System.out.println("Hello World");
}
```

Example of other return types:

```java
public class ReturnTypeDemo {

    // Primitive type (int, float, char, boolean etc)
    int multiply(int a, int b) {
        return a * b;
    }

    // Reference type (String)
    String getName() {
        return "Rhythm";
    }

    // Array
    int[] getNumbers() {
        return new int[] {1, 2, 3, 4};
    }

    // Custom object
    Dog getDog() {
        return new Dog();
    }

    // Void (no return value)
    void showMessage() {
        System.out.println("This is a message");
    }
}
```

---

## Constructors

A constructor is a special method that is called automatically when an object of a class is created.

Its job is to initialize the object’s fields (variables). The constructor name is the same as the class name. It should not have any return type.

### Types:

1. Default Constructor:
    
    It does not have any parameters.
    
    ```java
    class Student {
        String name;
    
        // Default constructor
        Student() {
    				System.out.println("This is a default constructor");
        }
    }
    
    Student s = new Student();  // Output : This is a default constructor
    ```
    

b. Parameterized Constructor:

It has parameters to initialize the object with certain values:

```java
class Student {
    String name;
    int age;

    // Parameterized constructor
    Student(String n, int a) {
        name = n;
        age = a;
    }
}

Student s = new Student("Rhythm", 21);
System.out.println(s.name + " - " + s.age); // Rhythm - 21
```

### Constructor Overloading

We can have multiple constructor of the same class