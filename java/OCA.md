# OCA

1. Checked exceptions are meant for...
 + exceptional conditions external to an application that a well written application should anticipate and from which it can recover.
 + sublcass of Exception
 + invalid conditions in areas outside the imeediate control of the program
2. RuntimeExeption(unchecked) it's sublcass of Exception!
3. String String = "string isa string";  System.out.println(String.substring(3, 6)); -> "ing"
4. Throwable is a super class of Exception
5. Any exception that extends java.lang.Exception but is not a subclass of java.lang.RuntimeException is a checked exception
6. A final variable must be initialized when an instance is constructed.
7. The overriding method cannot decrease the accessibility.
8. you cannot override/hide a static method with a non static method and vice versa

```
          C P S W
public    X X X X
protected X X X
          X X
private   X
```