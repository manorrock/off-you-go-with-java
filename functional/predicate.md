# Predicate

## Object form of a Predicate

object form

## Lambda expression form of a predicate

A predicate can be written in lambda expression form as illustrated below

```java
  Predicate<Integer> even = e -> e % 2 == 0;
```

The example above creates a predicate that could be used to test whether an integer is odd or even.

## Using a predicate for testing

A predicate can be used for testing using its test method as shown below.

```java
  Predicate<Integer> even = e -> e % 2 == 0;
  even.test(1);
```

The example above illustrates how the predicate can be used to test if a given integer is even. If it is it would return `true`, if it is not it would return `false`.

## Negating a predicate

negate method

## Testing equality using a predicate

isEqual method

## Combining predicates using a logical AND

and method

## Combining predicates using a logical OR

or method

### References

1. [JavaDoc](https://docs.oracle.com/en/java/javase/16/docs/api/java.base/java/util/function/Predicate.html)
