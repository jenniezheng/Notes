# Java


## History

- Java is a combination of Smalltalk and C++, created by Sun Microsystems

- Built for embedded systems but rose in popularity thanks to HotJava applets

- Machine dependent which encourages portability but causes machine to machine differences.


## About
- Statically type
- Has Java Virtual Machine (JVM), a set of rules for compiling Java to bytecode
- Many other languages like Scala and Clojure use JVM
- Garbage collection, and no pointers,
- Everything is reference type, except for primitive types (note: arrays are objects rather than primitives)


## Types
**Types** - Set of values and operations on values. Why Types?
- storage efficieny
- allow predictable behavior
- catch typos
- overloading

**Static vs Dynamic type checking** - Static type checking predicts types before program runs to ensure safety and speed, while dynamic type checking conclude types as program runs like in Python and Javascript

**Duck Typing** - If woddle and quack like duck, it's a duck. Base object on behavior rather than type. Example: Python.

**Abstract vs. exposed types** - Abstract types have value and operations, while exposed types have value and representation in memory
Name vs Structural type equivalence - Name means same name; structural means same internal structure

## Subtypes

**Subtypes** - Strictly add functionality but do not take any away. Etc: subclass.

**Syntax** - Subtypes declared with extends or implements

**Inheritance** - Everything inherits object. Some inherit from superclass

**Interface vs Class** - Interface has collection of variables and method declarations, while class has defined methods.


**Multiple Inheritance** - In Java, object can implement many interfaces but only extend one class. But in other languages like C++, object can extend multiple classes.

**Abstract Class** - An interface with a class. Cannot create an object of an abstract class.

**Bounded Wildcards** - Relaxes restrictions on variable and allows polymorphism.

```java
/*Only accepts general shapes*/
Collection <Shape> shapes

/*Lower Bounded wildcard accepts parents of shape*/
Collection<? super T> shapes

/*Upper bounded wildcard accepts subtypes of shape*/
Collection <? extends Shape> shapes;

/*Unbounded wildcard accepts anything*/
Collection <?> objects;
```
**Implementation** - Bytecode interpreter only deals with specific types. Occasionally it'll erase an originally known type and cast at runtime.


## Names

When is variable bound?

- Global is bound before execution
- Local is bound upon execution of declaration
- Static is bound at link time
- Local and need address is bound at function entry

Where is an object's functions and variables visible?

- public - everywhere
- protected - from class, subclasses, and superclass
- (none) - from class and subclasses
- private - from class

**Labaled Namespaces** - aka structures in ML, namespace in C++, packages in Java and Ada, module in Python



## Objects

Objects are passed as pointers, while primitives are passed by value.

**Object Class** - superclass to all classes in Java

```java
public class Object {
    /* imporant methods for Java */

    /* Constructer for testing code */
    public Object();

    /* Default for comparing addresses */
    public boolean equals(Object obj);

    /* Default for hashing an object's pointer */
    public int hashCode();

    /* returns at compile time information at runtime */
    public final Class getClass();

    /* returns a string represenation of an object */
    public String toString();

    /* last will of an object */
    protected void finalize() throws Throwable;

    /* clone any object */
    protected Object clone() throws CloneNotSupportedException;
}
```


## Concurrency
Java allows threads.

Use `Thread` or `Runnable` class

Use `synchronized` key word

Use `volatile` key word for variables which will be used by many threads and need to be stored in main memory and accessed with synchronization

Use `AtomicIntegerArray` and other classes for atomic data storage

