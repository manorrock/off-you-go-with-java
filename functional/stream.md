# Stream

## Filtering out elements

When processing a stream there are times you would want to filter out certain elements that do not meet the right criteria. Here is where a predicate comes in to determine whether or not a given element matches. If it matches it is retained, if it does not it is filtered out. See for an example below.

```java
  int[] integers = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
  Arrays.stream(integers)
    .filter(e -> e % 2 == 0)
    .forEach(System.out::println);
```

The example above filters out all odd integers out of the given stream.

### References

1. [JavaDoc](https://docs.oracle.com/en/java/javase/16/docs/api/java.base/java/util/stream/Stream.html)
