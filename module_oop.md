# OOP questions

## Software design

### Error handling

#### What does 'fail fast' mean in terms of exception handling? Why is it a good practice?
- The fail fast principle stands for stopping the current operation as soon as any unexpected error occurs. Adhering to this principle generally results in a more stable solution.

## Computer Science

### Data structures

#### How to find the middle element of singly linked list in O(n)?
- Traverse the list and count the nodes. Traverse again till the count/2.

- Traverse the list with two pointers. Move one pointer by one and other by two. When the faster is in the end of the list, the firs will be in middle.

#### Given an array of integers going from 1 to 100 (both inclusive) there is a duplicated entry. How to find it?
-     public static void main(String[] args) {
          int[] my_array = {1, 2, 5, 5, 6, 6, 7, 2};
   
          for (int i = 0; i < my_array.length-1; i++)
          {
              for (int j = i + 1; j < my_array.length; j++)
              {
                  if ((my_array[i] == my_array[j]) && (i != j))
                  {
                      System.out.println("Duplicate Element : " + my_array[j]);
                  }
              }
          }
      } 
#### What is a linked list? How to find if a linked list has a loop?
- a linked list consists of nodes where each node contains a data field and a reference(link) to the next node in the list.

- Traverse the list one by one and store every element in a set. If the current element is already in the set then the list has a loop.

#### What is the Big O time complexity of the common operations in an ArrayList, LinkedList, HashMap? And of a bubble sort, quicksort, finding items in a Binary Search tree?
**ArrayList:**
- add() – takes **O(1)** time
- add(index, element) – in average runs in **O(n)** time
- get() – is always a constant time **O(1)** operation
- remove() – runs in linear **O(n)** time. We have to iterate the entire array to find the element qualifying for removal
- indexOf() – also runs in linear time. It iterates through the internal array and checking each element one by one. So the time complexity for this operation always requires **O(n)** time
- contains() – implementation is based on indexOf(). So it will also run in **O(n)** time

**LinkedList**
- add() – supports O(1) constant-time insertion at any position
- get() – searching for an element takes O(n) time
- remove() – removing an element also takes O(1) operation, as we provide the position of the element
- contains() – also has O(n) time complexity

**HashMap:**
- every task takes a single operation (except in edge cases, like hash clash).

**Bubble Sort:**
- needs a nested for loop: **O(n^2)**

**Quicksort:**
- on average: **O(log n)**
- worst case: **O(n^2)**

**Binary Search Tree:**
- **O(log n)**
- worst case (degenerate tree): **O(n)**
#### How does HashMap work?
- A HashMap store items in "key/value" pairs, and you can access them by an index of another type (e.g. a String).
- One object is used as a key (index) to another object (value). It can store different types.
#### Why is it important for keys in a map to have an immutable type? (Consider String for example.)
- HashMap is a data-structure where data is organized as key and values pairs. i.e. for every value there must be a  key to be produced to be stored into the hashmap.
  Keys are normally generated using hashcode() method.
  Key’s hash code is used primarily in conjunction to its equals() method, for putting a key in map and then searching it back from map. So if hash code of key object changes after we have put a key-value pair in map, then its almost impossible to fetch the value object back from map. It is a case of memory leak. To avoid this, map keys should be immutable.
### Other

#### What is a garbage collector, in a nutshell?
- Java garbage collection is the process by which Java programs perform automatic memory management. Java programs compile to bytecode that can be run on a Java Virtual Machine, or JVM for short. When Java programs run on the JVM, objects are created on the heap, which is a portion of memory dedicated to the program. Eventually, some objects will no longer be needed. The garbage collector finds these unused objects and deletes them to free up memory.

## Programming paradigms

### Procedural

#### What is casting? What is the difference between up vs downcasting?
- Casting is when you assign a value of one primitive data type to another type.

**Upcasting**
- Upcasting is the typecasting of a child object to a parent object. 
Upcasting can be done implicitly. 
Upcasting gives us the flexibility to access the parent class members but it is not possible to access all the child class members using this feature. 
Instead of all the members, we can access some specified members of the child class. 
For instance, we can access the overridden methods.

**Downcasting**
- Similarly, downcasting means the typecasting of a parent object to a child object. 
Downcasting cannot be implicitly.

#### Which order should we catch the exceptions? Why?
- From the most specific to the most generic.
- Because if we catch first the generic we'll get a compilation error.

### Object-oriented

#### What is a class?
- A class describes what the object will be, but is separate from the object itself.
In other words, classes can be described as blueprints, descriptions, or definitions for an object. You can use the same class as a blueprint for creating multiple objects.
- Each class has a name, and each is used to define attributes and behavior.
    - attributes: describes the current state of an object (name, height, age, ...)
    - behavior: describes what the object is capable of doing (walk, run, jump, ...)

- Creating class:
-       public class Animal {
            void bark() {
                System.out.println("Woof-Woof");
            }
        }
#### What is an object?
- In OOP, each object is an independent unit with a unique identity.
- Each object has three dimensions: 
    - identity 
    - attributes: describes the current state of an object (name, height, age, ...)
    - behavior: describes what the object is capable of doing (walk, run, jump, ...)
- an object is an instance of a class.

- Creating object:
-     class MyClass {
          public static void main(String[ ] args) {
              Animal dog = new Animal();
              dog.bark();
          }
      }
#### What is a constructor?
- A constructor in Java is a special method that is used to initialize objects. The constructor is called when an object of a class is created. It can be used to set initial values for object attributes.

#### Do we require parameter for constructors?
- No

#### What is an interface?
- An interface is a completely "abstract class" that is used to group related methods with empty bodies.

- To access the interface methods, the interface must be "implemented" by another class with the implements keyword.

- A class can implement multiple interfaces.

#### What are access modifiers?
- Access modifiers, are used to set the access level for classes, attributes, methods and constructors.

**Types:**
- public : The code is accessible for all classes.

- protected : The code is accessible in the same package and subclasses.

- private : The code is only accessible within the declared class.

- default : The code is only accessible in the same package. This is used when you don't specify a modifier.

#### What is data hiding?
- Data hiding is a software development technique specifically used in object-oriented programming (OOP) to hide internal object details (data members). Data hiding ensures exclusive data access to class members and protects object integrity by preventing unintended or intended changes.

#### Can a static method use non-static members?
- Yes it can use non-static members, but it needs to create an object to access those members.

#### What is the difference between hiding a static method and overriding an instance method?
- Hiding does not work like overriding, because static methods are not polymorphic.

#### Define the following terms: Instantiation, Attribute, Method
**Instantiation**
- creating an object from class

**Attribute**
- An attribute is another term for a field. It's typically a public constant or a public variable that can be accessed directly

**Method**
- A method is a block of code which only runs when it is called.

- You can pass data, known as parameters, into a method.

- Methods are used to perform certain actions.

#### Could we access a static variable (or method) from a non-static method? Why?
- Yes we can.

- If it's public we can access from anywhere.

- If it's private only in the same class.

- doesn’t need an instance of the class

#### Could we access a non-static variable (or method) from a static method? Why?
- No because that variable belongs to an instance.

- We need to create an object to use those fields and methods.

#### How many instances you have of a static variable of a given class?
- One

#### Why is it not a good practice to write a lot of static methods?
- Static methods don't fully support OOP design.

#### What are the features of static attributes and static methods of a class? What are the benefits, when to use them?
#### What is the ‘this’ reference?
- refference the object of the current class.

#### What are base class, subclass and superclass?
- When we use Inheritance a subclass (child) extends superclass (parent) and inherits all its properties.

- A base class is a class will be extended

#### Draw an object oriented family (as entities, with relations) on the whiteboard.

#### Difference between overloading and overriding?
**Overloading**
- method with same name but different parameters.

**Overriding**
- change an inherited method.

#### What are the Object Oriented Principles? Explain the concepts with realistic examples!
- inheritance

- polymorphism - uses inherited methods to perform different tasks.

- encapsulation - "sensitive" data is hidden from users. (get and set methods to access).

- Abstraction - process of hiding certain details and showing only essential information to the user.

#### What is method overloading?
#### What is method overriding?

#### Explain how object oriented languages attempt to simplify memory management for Programmers.
- Heap - objects - bigger - garbage collector

- Stack - LIFO - primitives - object references - slower

#### Explain the “Single Responsibility” principle!
- every module or class should have only one responsibility.

#### What is an object oriented program? Explain, show.
- creating objects that contain both data and functions.

- class (fruit)
- object (apple, orange, banana)

#### How do you make a class immutable? What do you need to watch out for?
- Declare class final
- Declare class members final
- Create getter methods and no set method.

#### How many instances can be created for an abstract class?
- 0

## Programming languages

### Java

#### What is autoboxing and unboxing?
- Autoboxing and Unboxing. Autoboxing is the automatic conversion that the Java compiler makes between the primitive types and their corresponding object wrapper classes

#### If you have a variable, that shall store a positive whole number between 0 and 200, what primitive type would you use to store it?
- Short or int because byte can store digits only between -128 and 127 (short: -32,768 - 32,767)

#### What is the "golden rule" of variable scoping in Java? What is the lifetime of variables?
- A variable is available only in the scope it was defined (curly brackets). 

#### What is the purpose of the ‘equals()’ method?
- comparison of values in the objects.

#### What is the difference between '==' and 'equals()'?
- "==" compares the objects.

- "equals()" compares the values of the objects.

#### What does the ‘static’ keyword mean?
- static variable or method is available at the class level.
- don't need to create an instance of the class to access it.

#### Why is the main() method declared as static? Explain.
- Java main() method is always static, so that compiler can call it without the creation of an object or before the creation of an object of the class

#### What is the default access modifier in a class?
- can access from the same package.

#### What is the JVM (Java Virtual Machine) ?
- The Java compiler converts the java file to Byte Code and the JVM converts the Byte Code to Machine Code for the Operating System.

#### What is the difference between the JRE (Java Runtime Environment) and the JDK (Java Development Kit) ?
- The JRE contains the JVM and other libraries
- The JDK contains the JRE and the development kits

#### What is the difference between long and Long?
- long is an primitive type and Long is a class.

#### Can a long store bigger numbers than a Long?
- no

#### What kind of packages do you know under java.util.* ? Bring at least 3 examples.
- java.util.ArrayList;
- java.util.Collections;
- java.util.List;

#### What are the access modifiers in Java? Which one could we use for class?
- public, private, protected and default. For class we can use public and default.

#### Can an “enum” contain methods in Java? Explain.
- Enum can contain constructors, methods, fields.

#### When would you use a private/protected/public attribute? What is the difference?
-Private is used when you want to limit access only insde the class, protected inside the class but can be accessed if that class is inherited.
 Using public you can access the class from anywhere.
 
#### How do you prevent developers from subclassing a class?
- Create a private constructor, make the class final.

#### How do you prevent developers from overriding a method in a subclass?
- Use the final keyword.

#### How do you prevent developers from changing the value of a variable?
- Make the variable static final.

#### Think about money ;) How would you store a currency value, that shall support decimal parts? Think it through again, and try to think outside of the box!
- The BigDecimal class provides operations on double numbers for arithmetic, scale handling, rounding, comparison, format conversion and hashing. It can handle very large and very small floating point numbers with great precision.

#### What happens if you try to call something, that you have no access to, because of data hiding?
- get an error that Java compiler can't find that member.

#### What happens if you try to delete/drop an item from an array, while you are iterating over it?
- IndexOutofbounds exception.

#### What happens if you try to delete/drop/add an item from a List, while you are iterating over it?
- you will get ConcurrentModificationException exception.

#### What happens if you try to add an item to the end of an array, while you are iterating over it?
- ArrayIndexOutOfBoundsException

#### If you need to access the iterator variable after a for loop, how would you do it?
- save it into a variable.

#### Which interfaces extend the Collection interface in Java. Which classes?
- List
- Queue
- Set

#### What is the connection between equals() and hashCode()? How are they used in HashMap?
- If two objects are equal, then they must have the same hash code. 
- If two objects have the same hash code, they may or may not be equal.

#### What is the difference between checked exceptions and unchecked exceptions? Could you bring example for each?
- Checked exception are the exceptions that happen whe you compile a program and uncheked at runtime.

- Checked exception - ClassNotFoundException

- Unchked exception - ArithmeticException

#### What is Error in Java and how does it relate to Exception?
- Exception and Error classes are inherited from Throwable class.

#### When does 'finally' block run? What it is used for? Could you give an example from your projects when you would use 'finally'?
- it always runs at the end of the exception handling.

#### What is the largest number you can work with in Java?

#### When you use method overriding, can you change the access level of the method, from protected to public? Why?When you use method overriding, can you change the access level of the method, from public to protected? Why?
- has to be at the same access level with super.

#### Can the main method be overridden? Explain your answer!
- no because it's static

#### When you use method overriding, can you throw fewer exceptions in the subclass than in the parent class? Why?
- An overriding method (the method of child class) can throw any unchecked exceptions, regardless of whether the overridden method (method of base class) throws exceptions or not. However the overriding method should not throw checked exceptions that are new or broader than the ones declared by the overridden method. The overriding method can throw those checked exceptions, which have less scope than the exception(s) declared in the overridden method.

#### When you use method overriding, can you throw more exceptions in the subclass than in the parent class? Why?

#### What does "final" mean in case of a variable, method or a class?
- In variable using final, you create a constant

- For methods, prevent method overriding.

- For classes, prevent inheritance.

#### What is the super keyword?
- refers to the current class's superclass (parent class)

#### What are “generics”? When to use? Show examples.
- when we want to run the same method with different type.

- example: List **< generic >**

#### What is the benefit of having “generic” containers?
- Generics add stability to your code by making more of your bugs.

#### Given two Java programs on two different machines. How can you communicate between the two? What are the possible ways?
#### What is an annotation? What can be annotated and how? Show examples.
- allows you to embed metadata in source code

### Database

#### How can you connect your application to a database server? What are the possible ways?
- You can use JDBC whichs is a standard to connect to a database and execute querry or JPA which is a more advanced way to connect to database and use ORM.

#### What do you know about database normalization?
- Normalization is the process of organizing data in a database.