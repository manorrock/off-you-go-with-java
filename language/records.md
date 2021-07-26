# Records

Since Java 16

## Constructor

The example below defines a Java record that defines a Person class that has
a first and last name. For each of these automatic getters and setters are 
available for use. And internally it has private fields to store said
information.

```java
  record Person(
    String firstName,
    String lastName) {
  }
```

## Overriding default constructor

The example below builds on the previos example to add some validation to the
default constructor.

```java
  record Person(
    String firstName,
    String lastName) {
 
    Person {
      if (firstName == null) {
        throw nre IllegalArgumentException("First name cannot be null");
      }
    }
  }
```

### References

1. [JEP 395: Records](https://openjdk.java.net/jeps/395)
