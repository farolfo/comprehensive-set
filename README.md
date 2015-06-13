# Comprehensive Set
Build sets in mathematical [set-builder notation](https://en.wikipedia.org/wiki/Set-builder_notation) notation with Java, like { x | x E {1,2} ^ x is even }.

### Usage and motivation

In algebra we are able to define sets using set-builder notation, also known as set comprehension. For example, this computes the even numbers in a set of integers

```java
{ x | x E {1,2,3,4} ^ x is even }
// gives {2,4}
```

which is read as __give me the set of all x such that x belongs to {1,2,3,4} and x is even__.

Now this is how you achieve this in Java with Comprehensive Set

```java
Predicate<Integer> even = x -> x % 2 == 0;

Set<Integer> someIntegers = new HashSet(Arrays.asList(1, 2, 3, 4));

Set<Integer> evens = ComprehensiveSet.suchThat((x) -> {
    x.belongsTo(someIntegers);
    x.is(even);
});
// evens = {2,4};
```

As you may see in the example, Java 8 is needed.

### License

MIT
