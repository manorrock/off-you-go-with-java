# Stream

## Collecting results

At the end of processing a stream often times you would need to collect the results.

```java
  int[] integers = { 1, 2, 3, 4, 5 };
  Arrays.stream(integers)
    .collect(Collectors.toList());
```

The example above collects the stream results into a List.

## Counting the number of elements

When processing a stream you might want to know how large the stream is. The example below shows you how.

```java
  int[] integers = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
  System.out.println(Arrays.stream(integers).count());
```

## Getting the distinct elements

When processing a stream you might want to only get the elements that are distinct. 

```java
  int[] integers = { 1, 3, 7, 5, 1, 5, 11 };
  Arrays.stream(integers)
    .distinct()
    .forEach(System.out::println);
```

The example above creates a stream that only contain distinct elements from the original stream.

## Create an empty stream

Sometimes you want to start with an empty stream. See below how you would start with such a stream.

```java
  Stream
    .empty();
```

## Filtering out elements

When processing a stream there are times you would want to filter out certain elements that do not meet the right criteria. Here is where a predicate comes in to determine whether or not a given element matches. If it matches it is retained, if it does not it is filtered out. See for an example below.

```java
  int[] integers = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
  Arrays.stream(integers)
    .filter(e -> e % 2 == 0)
    .forEach(System.out::println);
```

The example above filters out all odd integers out of the given stream.

## Limit the number of elements

When processing a stream there are times you would want to limit the number of elements to a specific size. See for an example below.

```java
  int[] integers = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
  Arrays.stream(integers)
    .limit(5)
    .forEach(System.out::println);
```

The example above will only print the first 5 elements.

## Skipping a number of elements

When processing a stream there are times you would want to skip a number of elements. See for an example below.

```java
  int[] integers = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
  Arrays.stream(integers)
    .skip(5)
    .forEach(System.out::println);
```

The example above will start printing the elements after skipping the first 5 elements.

## Find the first element

If you ever just want to get the first element of the stream see the example below.

```java
  int[] integers = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
  Arrays.stream(integers)
    .findFirst()
    .stream()
    .forEach(System.out::println);
```

The example above should print just the first element, which in this case is 1.

Note that findFirst returns an Optional as the stream could be empty and thus not have a first element.

## Determine if all elements match the specified predicate

If you want to see if all elements math a specific condition you can use a predicate with allMatch to do so. See below.

```java
  int[] integers = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
  Arrays.stream(integers)
    .allMatch(n -> n > 0);
```

The example above determines if all the elements in the stream are greater than 0, which is true in this particular case.

### References

1. [JavaDoc](https://docs.oracle.com/en/java/javase/16/docs/api/java.base/java/util/stream/Stream.html)
