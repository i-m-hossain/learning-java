# Functional Interface and Lambda expressions
<!-- TOC -->
* [Functional Interface and Lambda expressions](#functional-interface-and-lambda-expressions)
  * [What is functional interface?](#what-is-functional-interface)
  * [What is lambda expression?](#what-is-lambda-expression)
  * [How to use Functional interface with lambda expression?](#how-to-use-functional-interface-with-lambda-expression)
  * [Types of functional interface?](#types-of-functional-interface)
    * [Consumer](#consumer)
    * [Supplier](#supplier)
    * [Function](#function)
    * [Predicate](#predicate)
  * [How to handle use cases when functional interface extends from other interface (or Functional interface)](#how-to-handle-use-cases-when-functional-interface-extends-from-other-interface-or-functional-interface)
<!-- TOC -->

## What is functional interface?
- A functional interface is an interface with a **single abstract method**(SAM). They are the target for lambda expressions and method references. 
  The **@FunctionalInterface** annotation is used to indicate that an interface is intended to be a functional interface, though it's not mandatory.
  ```java
  @FunctionalInterface
  interface Greeting {
      String sayHello(String message);
  }
  ```
- Functional interface may have default method implementation, static method implementation and Method inherited from object class methods such as toString(), clone(), equals(), hashCode() etc.
  ```java
  @FunctionalInterface
  interface TestInterface{ 
    String test(); //public abstract method
    default void canEat(){ //default method implementation allowed
        System.out.println("you can eat");
    }   
    static void getHeight(){ // static method implementation allowed
        System.out.println("getting my height");
    }
    String toString(); //object class method allowed
  }
  ```
## What is lambda expression?
- Lambda expressions provide a clear and concise way to implement functional interfaces.
  They are essentially shorthand for creating instances of functional interfaces.
  
## How to use Functional interface with lambda expression?

```java
/*--- without using lambda expression an anonymous class representation with functional interface ---*/
public static  void main(String[] args){
  Greeting greeting = new Greeting() {
    @Override 
    public String sayHello(String message) {
        return message;
    }
  };
  System.out.println(greeting.sayHello("hello world")); // hello-world
}

/* Now this code snippet can be rewritten below by using lambda expression */
public static void main(String[] args){
  Greeting greeting = message->message;
  System.out.println(greeting.sayHello("hello world"));
}
```
- So lambda expression minimizes the boilerplate code and provides an elegant syntax to work with

## Types of functional interface?
### Consumer
A Consumer represents an operation that accepts **a single input argument** and **returns no result**. It is typically used for operations that **perform side effects**.
- **Signature**;
```java
@FunctionalInterface
public interface Consumer<T> {
  void accept(T t);
}
```
- **Example:**
```java
import java.util.function.Consumer;

public class Main {
    public static void main(String[] args) {
      List<Integer> numbers = Arrays.asList(1,2,3,4,5,6,7,8,9,10);
      Consumer<Integer> printConsumer = num-> System.out.println(num);
      //way 1:
      numbers.stream().forEach(printConsumer);
      //way 2:
      for (int num:numbers){
        printConsumer.accept(num);
      }
      //way 3:
      number.stream().forEach(num-> System.out.println(num));
    }
}
```
- **Use case:**
  - It is typically used for operations that perform side effects.
  - Processing items in a collection, such as printing each element.


### Supplier
A Supplier represents a supplier of results. It does not take any arguments and returns a result. It is typically used for lazy generation or fetching of values.
- **Signature:**
```java
@FunctionalInterface
public interface Supplier<T> {
    T get();
}
```
- **Code Example:**
```java
import java.util.function.Supplier;

public class Main {
    public static void main(String[] args) {
        Supplier<String> supplier = () -> "Hello, World!";
        System.out.println(supplier.get()); // Output: Hello, World!
    }
}

```
- **Use Case:**
  - Generating values on demand, such as providing default values or creating new instances.

### Function
A Function represents a function that accepts one argument and produces a result. It is typically used for transforming or mapping a value from one type to another.
- **Signature:**
```java
@FunctionalInterface
public interface Function<T, R> {
    R apply(T t);
}
```
- **Code example:**
```java
import java.util.function.Function;

public class Main {
    public static void main(String[] args) {
        //example 1:
        Function<String, Integer> stringToLength = s -> s.length();
        System.out.println(stringToLength.apply("Hello, World!")); // Output: 13
        //example 2:
        //implementation 1
        List<Integer> numbers = Arrays.asList(1,2,3,4,5,6,7,8,9,10);
        Function<Integer, Integer> doubleEachItem = item-> item*2;
        List newNums = numbers.stream().map(doubleEachItem).toList();
        //implementation 2
        List newNumbers =  numbers.stream().map(item->item*2).toList();
        System.out.println(newNumbers);
        
    }
}

```
- **Use Case:**
  - Converting values from one type to another, such as parsing a string to an integer.
### Predicate
A Predicate represents a predicate (boolean-valued function) of one argument. It is typically used for testing or matching conditions.
- **Signature:**
```java
@FunctionalInterface
public interface Predicate<T> {
    boolean test(T t);
}
```
- **Example code:**
```java
import java.util.function.Predicate;

public class Main {
    public static void main(String[] args) {
      Predicate<String> isEmpty = s -> s.isEmpty();
      System.out.println(isEmpty.test("")); // Output: true
      System.out.println(isEmpty.test("Hello")); // Output: false
        
        //second example:
      Predicate<Integer> isEvenNumber = item -> item%2 ==0;
      List filteredNumbers = numbers.stream().filter(isEvenNumber).toList();
      System.out.println(filteredNumbers);
    }
}

```
- Use Case:
  - Filtering collections based on certain criteria.

## How to handle use cases when functional interface extends from other interface (or Functional interface)
In Java, when a functional interface extends another interface (whether it's a functional interface or a regular interface), it can inherit abstract methods. To remain a functional interface, it must still have exactly one abstract method, even if that method is inherited from the parent interface