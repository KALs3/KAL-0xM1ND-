![[Pasted image 20250312043620.png]]

### Inheritance is an Object oriented feature which allows a class to inherit behavior (methods) and attributes from other class.

##### With the use of inheritance the information is made manageable in a hierarchical order.
### The class whose properties are inherited is known as super Class While The class which inherits the properties of other is known as subclass

### we can think of the relationship between the classes as a parent and child class in which the child class inherits their parent 


We can *Extended* the Capabilities of a class using the **extend** keyword
```java
Public class employee extends Person
```


### A constructor is used to construct an instance of a class. Unlike properties and methods, a superclass's constructors are not inherited in the subclass.

#### They can only be invoked from the subclasses' constructors explicitly, using the keyword *super().*

### The `Super()` keyword can be used in 2 ways
- To call a superclass constructor fromsubclass constructor: super() as a first statement in sub class constructor
- To call a superclass method from a sub-class method: `super.method()`

```java
public class Person  
{  
  
    private String name;  
    private String job;  
    private String  address;  
    private int phoneNumber;  
  
    public Person() {  
  
    }  
	public Person(String name,String job,String address,int phoneNumber)  
    {  
        this.name = name;  
        this.job = job;  
        this.address = address;  
        this.phoneNumber = phoneNumber;  
    }

public class Student extends Person{  
  
    private  int groupId;  
    private  String tutorName ;  
  
  public Student(){  
  
  }  
  
    public Student(String name,String job,String address,int phoneNumber,int groupId,String tutorName)  
    {  
        super(name,job,address,phoneNumber);  
        this.groupId = groupId;  
        this.tutorName = tutorName;  
    }
```


# Method Overriding 
##### Method Overriding means that if we have a method in the superclass and we inherited it to the subclass the subclass can override it and use it's own version of it instead of the superclass one 
#### in more basic terms same method different context 

we use the `@Override` to point out the overridden a method from the superclass

```java
public class Person  
{
public void PrintAllDetails()  
{  
    System.out.println("name: " + name+" job: " + job + " address: " + address + " phone number : "+ phoneNumber);  
}

public class Student extends Person
{
@Override  
public void PrintAllDetails()  
{  
    super.PrintAllDetails();  
    System.out.println("group id : " + groupId+ " tutor name: "+ tutorName);  
}
}
```

## Reference type and object type 
when you use a reference variable from the base class you can only call methods from the base class

```java

public class Student extends Person{
public void speicalmethod(){  
    
}
}

in main function
Person std1 = new Person("james","teacher","23blox",234234);  
Person std2 = new
Student("james","teacher","23blox",234234,555,"micheal");

if you try to call the speical method which only exists in student subclass it will fail 
because we defined our refernce varible to look at the baseclass

```


# The protected Modifier

### when applying the **protected modifier** on data or attributes regarding the superclass it gives you the ability of accessing this data from the subclass but prevent accessing it publicly as it only allows you to use these attributes in the subclasses only 

![[Pasted image 20250313000020.png]]

# The final Modifier

The final class cannot be extended (inherited): final class Math { ... }

The final variable is a constant: final static double PI = 3.14159;

The final method cannot be overridden by its subclasses.

# The instanceof Operator
Use the instanceof operator to test whether an object is an instance of a class:


