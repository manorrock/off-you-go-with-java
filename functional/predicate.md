# Predicate

## Class form of a predicate

A predicate can be written in class form as seen below.

```java
  public class EvenPredicate implements Predicate<Integer> {

    public boolean test(Integer value) {
      return value.intValue() % 2 == 0;
    }
  }
```

The example above defines the class `EvenPredicate` and it can be used to test whether an integer is odd or even.

## Lambda expression form of a predicate

A predicate can be written in lambda expression form as illustrated below.

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

The example above illustrates how the predicate can be used to test if a given integer is even. If the integer is even it would return `true`, if the integer is not even it would return `false`.

## Negating a predicate

A static method that wraps an existing predicate and negates the boolean result. See for an example below.

```java
  Predicate<Integer> even = e -> e % 2 == 0;
  Predicate<Integer> notEven = Predicate.not(even);
  notEven.test(1);
```

The example above illustrates how to negate the `even` predicate making it the `notEven` predicate as illustrated.

## Testing equality using a predicate

A static method that returns a predicate that will perform an `.equals` check against the given object.

```java
  Predicate<Integer> isZero = Predicate.isEqual(0);
  isZero.test(0);
```

The example above creates a predicate that can be used to determine if a given number is equals to `0`.

## Combining predicates using a logical AND

A static method that returns a predicate that combines the result of 2 predicates by means of a logical AND.

```java
  Predicate<Integer> isNotZero = e -> e != 0;
  Predicate<Integer> even = e -> e % 2 == 0;
  Predicate<Integer> isNotZeroAndEven = isNotZero.and(even);
  isNotZeroAndEven.test(2);
```

The example above combines the `isNotZero` predicate and the `even` predicate together to construct the `isNotZeroAndEven` predicate.

## Combining predicates using a logical OR

or method

### References

1. [JavaDoc](https://docs.oracle.com/en/java/javase/16/docs/api/java.base/java/util/function/Predicate.html)
