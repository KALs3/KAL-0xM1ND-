abstract classes are meant to be a generic way to define how the subclasses of it should work and what kind of **abstract methods** it should implement 
whoever when we define a class as an abstract WE can't **insatiate** it because the class only acts like a single blueprint of what the subclasses should Look and **acts like it's like a template** 

when it comes to abstract classes we can have abstract methods too 
which is just a method defined by it's header 
ex: ```
```java
public abstract void get_salary();
```

by only defining this method like this in our class for each subclass to inherit our superclass they are going to have to implement this specific method body according to what each subclass tries to do or solve 


**ALSO** in our abstracted class we can define normal non-abstracted methods which will be inherited normally and reduce the amount of effort and code that could go in the subclasses for example if we have a getter and setter methods for a "name" attribute 

Note : **An abstract class should contain at least one abstract method and MUST be overridden by the subclasses**


## When to use abstract classes?
Usually when you have many classes that have common
features:
1. Common attributes,
2. Common methods, that has the same signature and
   implementation.
3. Common methods that has the same signature but
   different implementation.

In this case you create an abstract class (Super class) that has all the common
features, wherein the common methods that have same signature but
different implementation are represented as abstract methods.
And you will need concrete subclasses to complete the implementation of
abstract methods.



# Interfaces

An interface specifies a list of methods that a
group of unrelated classes should implement,
so that their instances can interact together by
responding to a common subset of messages.

Interfaces are “like” classes, but they may ONLY have:

1. Abstract methods, i.e. method header but NO method
code.
• All methods in an interface are automatically public.
• No need to writ public in the method header.

2. Constants, but NO instance variables.
• All constants in an interface are automatically public static final.
• Note that an interface is NOT a class and will have NO instances of
its own, and so it has NO attributes and NO constructor.


```java
public interface InterfaceName
{
constant declarations;
abstract method signatures;
}

public interface Edible {
/** Describe how to eat */
public abstract String howToEat();
}
```

To make use of an interface we need a
class to **implement** the interface.

```java
public class Chicken implements Edible{

......
public String howToEat() { }
}
```

1
