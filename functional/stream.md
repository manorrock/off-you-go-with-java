# Stream

## Iterate over each element in the stream

Often times you would want to do something which each element in the stream. The forEach method is your friend here.

```java
int[] integers = { 1, 3, 7, 5, 1, 5, 11 };
  Arrays.stream(integers)
    .forEach(System.out::println);
```

The example above prints each element to System.out.

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

## Determine if any of the elements match the specified predicate

If you want to know if any elements matches a specific condition you can use a predicate with anyMatch to do so. For an example see below.

```java
  int[] integers = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
  Arrays.stream(integers)
    .anyMatch(n -> n == 1);
```

The example above determines if any of the elements equals to 1, which is true for this example.

## Randomly get one of the elements of your stream

If you want a random element from your stream you can use findAny. The example below illustrates how you would do so.

```java
  int[] integers = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
  Arrays.stream(integers)
    .findAny()
    .getAsInt();
```

Note since the element is random it could be any of the elements in the stream described above.

## Generate a stream using a Supplier

You can generate a stream using a Supplier.

```java
  Stream<Integer> stream = Stream.generate(
      new Supplier<Integer>() { 
          Random random = new Random();
          public Integer get() { 
              return random.nextInt();
          }
      } 
  );
  stream
    .limit(10)
    .forEach(System.out::println);
```

The example above create a stream using a Supplier that uses the Random class to generate random integers and it prints the first 10.

## Combining streams together

Using the concat method you can combine streams together.

```java
  Stream integers1 = Arrays.stream(new Object[] { 1, 2, 3, 4, 5 });
  Stream integers2 = Arrays.stream(new Object[] { 6, 7, 8, 9, 10 });
  Stream integers = Stream.concat(integers1, integers2);
  integers.count();
```

The example above combines the two streams together and counts the number of elements. In this particular case it would return 10.

## Determine the maximum of the stream

Sometimes you would want to know the maximum of the stream. The following examples shows you how to do that.

```java
  int[] integers = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
  Arrays.stream(integers)
    .max()
    .getAsInt();
```

For the example above the maximum is 10 as this is a stream of integers.

## Determine the minimum of the stream

Sometimes you would want to know the minimum of the stream. The following examples shows you how to do that.

```java
  int[] integers = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
  Arrays.stream(integers)
    .min()
    .getAsInt();
```

For the example above the minimum is 1 as this is a stream of integers.

## Drop a number of elements based on a predicate

When processing a stream you might want to drop a number of element matching a predicate until it no longer matches. 

```java
  int[] integers = { 1, 3, 7, 5, 1, 5, 11 };
  Arrays.stream(integers)
    .dropWhile(i -> i < 7)
    .forEach(System.out::println);
```

The example above creates a stream that drops all elements less than 7 at the beginning of the stream until it no
longer matches the predicate.

### References

1. [JavaDoc](https://docs.oracle.com/en/java/javase/16/docs/api/java.base/java/util/stream/Stream.html)
