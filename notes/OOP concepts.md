# Object oriented programming
<!-- TOC -->
* [Object oriented programming](#object-oriented-programming)
  * [Object Oriented Programming:](#object-oriented-programming-1)
  * [What does object consist of?](#what-does-object-consist-of)
  * [Procedural vs OOP:](#procedural-vs-oop)
  * [Pillars of OOP:](#pillars-of-oop)
    * [1. First Pillar - Data ABSTRACTION](#1-first-pillar---data-abstraction)
    * [2. Second Pillar - Data ENCAPSULATION](#2-second-pillar---data-encapsulation)
    * [3. Third Pillar - INHERITANCE](#3-third-pillar---inheritance)
    * [4. Fourth Pillar - POLYMORPHISM](#4-fourth-pillar---polymorphism)
  * ['Is a' relationship AND 'Has a' relationship:](#is-a-relationship-and-has-a-relationship)
<!-- TOC -->

## Object Oriented Programming:
Object-oriented programming aka _OOP_ is a computer programming model that organizes software design around **data or objects**, rather than functions and logic. **An object** can be defined as a data field that has unique attributes and behaviour.


## What does object consist of?
- Properties (instance variable/ member variables)
- Behaviour (methods)

## Procedural vs OOP:
| Sl | Procedural                                                                                   | OOP                                                  | 
|----|----------------------------------------------------------------------------------------------|------------------------------------------------------| 
| 1  | Program is divided into parts called function                                                | Program is divided into objects                      |
| 2  | Does not provide proper way to hide data, gives importance to function and data moves freely | Object provide data hiding, gives importance to data |
| 3  | Overloading is not possible                                                                  | Overloading is possible                              |
| 4  | Inheritance not possible                                                                     | Inheritance possible                                 |
| 5  | Code reusability is not possible                                                             | Code reusability is possible                         |
| 6  | Example: C, Fortran etc                                                                      | Example: Java, C++, C# etc                           |
| 7  | Tightly coupled as the data moves freely                                                     | Loosely coupled                                      |

## Pillars of OOP:

### 1. First Pillar - Data ABSTRACTION
- It hides the internal implementation and show only essential functionality to the user
- It can be achieved through interface and abstract classes
- Example:
  - Car - we only care the car speed, not how break pedal works! So the break pedals 
    implementation is ABSTRACTED to us
  - Cellphone - how call is made is abstracted to us
- **Advantage** of abstraction:
  - Increases security and confidentiality
    
### 2. Second Pillar - Data ENCAPSULATION
- Encapsulation bundles the data and the code working on that data in a single unit
- Also known as Data-Hiding
- Steps to achieve encapsulation
  - Declare a variable of a class as private
  - Provide a public getters and setters to modify and view the value of the variables
- **Advantage**:
  - Loosely coupled code
  - Better access control and security
  
### 3. Third Pillar - INHERITANCE
- Capability of a class to **inherit** properties from their parent clas
- It can inherit both functions and variables, so we don't have to write them again in the child class
- Can be achieved using **extends** keyword or through interface
- Types of inheritance:
  - single inheritance
  - Multilevel inheritance
  - Hierarchical inheritance
  - Multiple inheritance - through interface we can resolve the diamond problem
- **Advantages:**
  - Code reusability
  - We can achieve **Polymorphism** using **Inheritance**

### 4. Fourth Pillar - POLYMORPHISM

- Poly mean Many and Morphism means Form
- Same methods behaves differently in different situation
- Example:
  - A person can be Father, Husband, Employee etc.
  - Water can be liquid, solid and gas etc.
- Types of Polymorphism:
  - **Compile time / Static Polymorphism / Method Overloading** -- based on methods parameters in the same class, if a method is different by parameters but name same they will be overloaded. in the same class with same parameter two method is not possible.
  - **Run time / Dynamic Polymorphism / Method overriding** -- based on methods parameters if child with same parameters it will override parents method, if not it will be overloaded
- Example:

```java
/* overloading polymorphism */
public class Sum {
  public int doSum(int a, int b) {
    return a + b;
  }

  public String doSum(String a, String b) {
    return a + b;
  }

  public int doSum(int a, int b, int c) {
    return a + b + c;
  }
}
```

```java
/* overriding polymorphism */
public class Math{
    public int doSum(int a, int b){
        return a+b;
    }
}

public class Sum extends Math{
    @Override
    public int doSum(int a, int b) {
        return super.doSum(a, b);
    }
}
```

## 'Is a' relationship AND 'Has a' relationship:
- Is a relationship:
  - Achieved through inheritance
  - Example: 
    - Dog is an Animal. (Dog - Child class, Animal - Parent class)
  - Inheritance form an is a relation between its parent and child class
- Has a relationship:
  - Whenever, an Object is used in Other Class, its called Has a relationship
  - Relationship could be one-to-one, one-to-many, many-to-many
  - Example:
    - School has Students
    - Bike has Engine
    - School has Classes
  - Association: Relationship between 2 different objects
    - **Aggregation/Weak relation**: Both objects. can survive individually, means ending of one object will not affect/end other object
    - **Composition/Strong relation**: Ending of One Object will end another object. E.g. School and ClassRoom. if School object gets deleted
      corresponding classrooms will also get deleted.

```java
import java.util.List;

public class Teacher {
  private String name;
}

public class Course {
  private int id;
  private String name;
  /* one-to-one relationship between course and teacher*/
  private Teacher teacher;
}

class Student {
  /* one-to-many relationship between Student and course */
  List<Course> courses;

}
```


