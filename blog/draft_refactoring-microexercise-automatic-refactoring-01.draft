---
published: false
categories:
  - sample
  - refactoring
  - refactoring-microexercise
  - microexercise
  - automatic-refactoring
  - spoiler
  - dry
---

Refactoring microexercise: Automatic refactoring

imagine this code (fragment - [^1]):

[^1]: the full code is available [here](https://github.com/alvarogarcia7/refactoring-microexercises/tree/master/java/src/main/java/refactoring)

```java
private PairList sutWith (final int input1, final int output1, final int input2, final int output2) {
	return new PairList(
			asList(
				pair(output1, input1),
				pair(output2, input2)));
}

private PairList sutWith (final int input, final int output) {
	return new PairList(
			asList(
				pair(output, input)));
}
```

Now imagine that it is time for the refactor phase. What would you change first?

  * Duplication for generating ``PairList``
  * Duplication for invoking ``asList``
  * Other
  
# Spoilers below

I've chosen to remove the duplication for the ``new PairList`` first. For that, I'd extract ``new PairList`` to a method (the IDE only suggests extracting everything) and extracting parameter ``asList(...)``. This has the problem that the other method (``sutWith(input, output)``) is not affected and has to be manually refactored, again. Which is duplication in the process.

## DRY - Don't repeat yourself

There's another way (there are more, also) to do this refactor:

  1. Extract the ``asList(...)`` to a variable
  2. Extract a method containing only the ``new`` (with the parameters)
  3. Receive this suggestion: 
  
  > Idea has detected 1 code fragment in this file that can be replaced with a call to the extracted method. [...]
  4. Accept it and you're done
