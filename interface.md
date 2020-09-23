# Inheritance and Interface  
## Interface  
An interface declaration consists of modifiers, the keyword interface, the interface name, a comma-separated list of parent interfaces (if any), and the interface body. For example:

## Abstract Methods, Static methods and Default metods  
The interface body can contain abstract methods, default methods, and static methods. An __abstract method__ within an interface is followed by a semicolon, but no braces (an abstract method does not contain an implementation).   

__Default methods__ are defined with the default modifier, and __static methods__ with the static keyword. All abstract, default, and static methods in an interface are implicitly public, so you can omit the public modifier.

In addition, an interface can contain constant declarations. All constant values defined in an interface are implicitly public, static, and final. Once again, you can omit these modifiers.

Example of an interface:
```
public interface Relatable {
        
    // this (object calling isLargerThan)
    // and other must be instances of 
    // the same class returns 1, 0, -1 
    // if this is greater than, 
    // equal to, or less than other
    public int isLargerThan(Relatable other);
}
```
Then in the class RectanglePlus:  
```
....
    // a method required to implement
    // the Relatable interface
    public int isLargerThan(Relatable other) {
        RectanglePlus otherRect 
            = (RectanglePlus)other;
        if (this.getArea() < otherRect.getArea())
            return -1;
        else if (this.getArea() > otherRect.getArea())
            return 1;
        else
            return 0;               
    }
```
__NOTE__: The isLargerThan method, as defined in the Relatable interface, takes an object of type Relatable. The line of code, shown in bold in the previous example, casts other to a RectanglePlus instance. Type casting tells the compiler what the object really is. Invoking getArea directly on the other instance (other.getArea()) would fail to compile because the compiler does not understand that other is actually an instance of RectanglePlus.  

## Using an Interface as a Type
When you define a new interface, you are defining a new reference data type. You can use interface names anywhere you can use any other data type name. If you define a reference variable whose type is an interface, any object you assign to it must be an instance of a class that implements the interface.  

## Evolving Interface  
Evolve interface by using either default or static methods.  
```
public interface DoIt {

   void doSomething(int i, double x);
   int doSomethingElse(String s);
   default boolean didItWork(int i, double x, String s) {
       // Method body 
   }
   
}

OR extend it  

public interface DoItPlus extends DoIt {

   boolean didItWork(int i, double x, String s);
   
}
```
If you just did this, the interface will  break  
```
public interface DoIt {

   void doSomething(int i, double x);
   int doSomethingElse(String s);
   boolean didItWork(int i, double x, String s);
   
}
```
