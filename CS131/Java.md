# Java

## About
- Statically type
- Has Java Virtual Machine (JVM), a set of rules for compiling Java to bytecode
- Many other languages like Scala and Clojure use JVM
- No pointers, and garbage collection
- Everything in a class, except for primitive values

#### Subtypes
**Definition** - Strictly add functionality but do not take any away.
**Syntax** - Subtypes declared with extends or implements
**Inheritance** - Everything inherits object. Some inherit from superclass
**Interface vs Class** - Object can implement many interfaces but only extend one class. Interface has collection of method declarations, while class has defined methods.

#### Parameter Passing
Everything passed by value. Nonprimitives are passed as pointers.

#### Concurrency
Use `Thread` or `Runnable` class
Use `synchronized` key word
Use `volatile` key word for variables which will be used by many threads and need to be stored in main memory and accessed with synchronization
Use `AtomicIntegerArray` and other classes for atomic data storage