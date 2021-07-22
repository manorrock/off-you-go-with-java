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
    String lastName)
```
