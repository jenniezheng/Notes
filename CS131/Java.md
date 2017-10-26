# Java


## History

- Java is a combination of Smalltalk and C++, created by Sun Microsystems

- Built for embedded systems but rose in popularity thanks to HotJava applets

- Machine dependent which encourages portability but causes machine to machine differences.

## About
- Statically typed
- Has Java Virtual Machine (JVM), a set of rules for compiling Java to bytecode
- Many other languages like Scala and Clojure use JVM
- Garbage collection, and no pointers,
- Everything is reference type, except for primitive types (note: arrays are objects rather than primitives)
- Objects are passed by address, while primitives are passed by value

## Types
**Types** - Set of values and operations on values. Why Types?
- storage efficieny
- allow predictable behavior
- catch typos
- overloading

**Static vs Dynamic type checking** - Static type checking predicts types before program runs to ensure safety and speed, while dynamic type checking conclude types as program runs like in Python and Javascript

**Duck Typing** - If woddle and quack like duck, it's a duck. Base object on behavior rather than type. Example: Python.

**Abstract vs. exposed types** - Abstract types have value and operations, while exposed types have value and representation in memory

**Name vs Structural type equivalence** - Name means same name; structural means same internal structure

## Polymorphism
Four types
- Overloading (ex: a + b overloading in C++)
- Parameter coercion (implicit type conversion)
- Parametric polymorphism (type can be many different types)
- Subtype polymorphism (OOL subtypes)

Two styles
- universal polymorphism (infinite types; ex subtype polymorphism and parametric polymorphism)
- ad hoc polymorphism (finite types; overloading and coercion)

##  Scoping

When is variable bound?

- Global is bound before execution
- Local is bound upon execution of declaration
- Static is bound at link time
- Local and need address is bound at function entry
- Late binding more flexible, early binding faster and safer

Where is an object's functions and variables visible?

- public - everywhere
- protected - from class, subclasses, and superclass
- (none) - from class and subclasses
- private - from class

How to scope?
- Blocks
- Labaled Namespaces
- Primitive Namespaces
- Dynamic Scoping
- Separate Compilation

**Labaled Namespaces** - aka structures in ML, namespace in C++, packages in Java and Ada, module in Python

##  Memory Allocation
How to allocate memory?
- Static allocation (no recursion)
- Stack allocation (no inner functions)
- Complex allocation (sophisticated language)

How to garbage collect?
- Mark and Sweep (marked referenced, delete unused)
- Copying (use half, when full, compact and copy to other half)
- Reference Count (can miss cycles, but divides garbage collection time)



## Subtypes

**Subtypes** - Strictly add functionality but do not take any away. Etc: subclass.

**Syntax** - Subtypes declared with extends or implements

**Inheritance** - Everything inherits object. Some inherit from superclass

**Interface vs Class** - Interface has collection of variables and method declarations, while class has defined methods.


**Multiple Inheritance**
    - Problems when multiple classes use same variable/method name, or when diamond inheritance occurs
    - Languages like C++ deal with these issues and allow multiple inheritance.
    - Java allows classes to implement many interfaces but only extend one class. To combine classes, consider forwarding (class has multiple classes as private variables)

**Abstract Class** - An interface with a class. Cannot create an object of an abstract class.

**Final Class** - A final class in Java cannot be subclassed.

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

**Generics** - Allows parameters to be of specific type.
    - Much cleaner and faster than allowing parameter to be of type Object, casting needed class to Object and then casting Object back to needed class.
    - Implemented in C++ and more recently, Java
    - Compiler substitutes specific class in place of T as needed.

```java
interface Stack<T>{
    void add(T item);
}

Stack<String> w;
```



## Objects

**Object Class** - superclass to all classes in Java

```java
public class Object {
    /* Constructer for testing code */
    public Object();

    /* Default for comparing addresses */
    public boolean equals(Object obj);

    /* Default for hashing an object's pointer */
    public int hashCode();

    /* returns at run time time information at compile time,
    final function cannot be overriden and can be inlined for efficiency*/
    public final Class getClass();

    /* returns a string represenation of an object */
    public String toString();

    /* garbage collects for an object, anything that may throw errow must throw throwable*/
    protected void finalize() throws Throwable;

    /* clone any object */
    protected Object clone() throws CloneNotSupportedException;
}
```


## Concurrency
**SMP** - Java takes advantage of shared memory parallelism and symmetric multiprocessing

**Cores** - Most CPUs have 2-8 cores. At higher core numbers, it's difficult to share bus and RAM.

Most of the below classes requires `import java.util.concurrent.*`;

Use `Thread` or `Runnable` class. Threads may sleep, wait, yield, exit, block, notify, notifyAll, etc.

Use `Exchanger`, `CountDownLatch`, `Cyclic Barrier` classes for simple synchronization problems.

Use `synchronized` key word for functions on critical paths.

Use `volatile` key word for changeable variables
- May be used by many threads and need to be stored in main memory and accessed with synchronization
- May be changed by CPU, ex: device register

Use `AtomicIntegerArray` and other classes for atomic data storage



