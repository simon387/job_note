# OCA

+ Checked exceptions are meant for...
  + exceptional conditions external to an application that a well written application should anticipate and from which it can recover.
  + sublcass of Exception
  + invalid conditions in areas outside the immediate control of the program
+ RuntimeException(unchecked) it's sublcass of Exception!
+ String String = "string isa string";  System.out.println(String.substring(3, 6)); -> "ing"
+ Throwable is a super class of Exception
+ Any exception that extends java.lang.Exception but is not a subclass of java.lang.RuntimeException is a checked exception
+ A final variable must be initialized when an instance is constructed.
+ The overriding method cannot decrease the accessibility.
+ you cannot override/hide a static method with a non static method and vice versa

+ 
  ```
            C P S W
  public    X X X X
  protected X X X
            X X
  private   X
  ```
+ Remember that a String once created cannot be changed
+ Default methods enable us to add new functionalities to interfaces without breaking the classes that implements that interface.
+ always return 1
  ```java
  try {
    throw new Exception();
  }
  catch(Exception exception) {
    return 0;
  }
  finally {
    return 1;
  }
  ```
+ ```new Object[] {"asd", {}};``` will not compile for ```{}```
+ A constructor cannot be final, static or abstract.
+ super classes can catch() subclass Exception
+ abstract classes can implements interface (obv without implementing methods)
+ Multiple inheritance of state includes ability to inherit instance fields from multiple classes.
+ Multiple inheritance of type includes ability to implement multiple interfaces and/or ability to extend from multiple clases.
+ there is no constructor in Short that takes an int
+ class ```ArrayList<E>``` has the ```add(int, <E>)``` method
+ this will print ```QBANK``` when executed
  ```java
  class Super { static String ID = "QBANK"; }
  
  class Sub extends Super{
     static { System.out.print("In Sub"); }
  }
  public class Test{
     public static void main(String[] args){
        System.out.println(Sub.ID);
     }
  }
  ```
  As per Section 12.4.1 given here: http://docs.oracle.com/javase/specs/jls/se7/html/jls-12.html
  A class or interface type T will be initialized immediately before the first occurrence of any one of the following:
  + T is a class and an instance of T is created.
  + T is a class and a static method declared by T is invoked.
  + A static field declared by T is assigned.
  + A static field declared by T is used and the field is not a constant variable (§4.12.4).
  + T is a top level class (§7.6), and an assert statement (§14.10) lexically nested within T (§8.1.3) is executed.
  + A reference to a static field (§8.3.1.1) causes initialization of only the class or interface that actually declares it, even though it might be referred to through the name of a subclass, a subinterface, or a class that implements an interface.
  + Invocation of certain reflective methods in class Class and in package java.lang.reflect also causes class or interface initialization.
  
  A class or interface will not be initialized under any other circumstance.
+ ```RETURNTYPE=double```
  ```java
  public RETURNTYPE methodX( byte by){
    double d = 10.0;
    return (long) by/d*3;
  }
  ```
+ Note that Arrays are Objects (i.e. cA instanceof Object is true)
+ octal 042 (08=error)
+ hex 0x42
+ binary 0b101010
+ static members are evaluated before constructor()
+ valid:
  ```java 
  new Long("123");
  Long.parseLong("123");
  Long.valueOf(mStr).longValue();
  ```
+ not valid:
  ```java
  new Long();
  ```
+ long cannot be used in switch statement
+ label everywhere but declarations
+ boolean operator ```!=``` has more precedence than ```=```
+ virtual method: A virtual method is a method in which the specifi c implementation is not determined until runtime. In fact, all non-fi nal, non-static, and non-private Java methods are considered virtual methods, since any of them can be overridden at runtime.
+ 
```java
List s1 = new ArrayList();
s1.add("a");
s1.add("b");
s1.add("c");
s1.add("a");
System.out.println(s1.remove("a") + " " + s1.remove("x")); //true false
```
+ new AssertionError() is an Error, NOT AN EXCEPTION
+ String has NOT the method reverse(); StringBuilder does
+ Autoboxing caches -128 to 127
+ LocalDateTime
```java
java.time.LocalDateTime.of(2015, 10, 1, 10, 10);
```
+ Double extends Number


---


## lambdas

what you need to know for the OCA exam

```java
a -> a.canHop()
(Animal a) -> { return a.canHop(); }
```

```java
print(a, b -> a.startsWith("test")); // DOES NOT COMPILE
print(a -> { a.startsWith("test"); }); // DOES NOT COMPILE
print(a -> { return a.startsWith("test") }); // DOES NOT COMPILE
```

```java
public interface Predicate<T> {
	boolean test(T t);
}
```

```java
List<String> bunnies = new ArrayList<>();
bunnies.add("long ear");
bunnies.add("floppy");
bunnies.add("hoppy");
System.out.println(bunnies);  // [Long ear, floppy, hoppy]
bunnies.removeIf(s -> s.charAt(0) != 'h');
System.out.println(bunnies);  // [hoppy]
```

