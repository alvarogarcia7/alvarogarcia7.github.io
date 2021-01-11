---
published: false
layout: post
categories: 
  - legacy-code
  - code
---

For a series of posts and other writings, I'm producing, on purpose, legacy code. With tests, but legacy code. 

TODO expand:

Imagine a Venn diagram with:
  * clean code
  * Legacy code
  * 
  * Omega (everything), including the two above

Which relationship is there between the clean code and the legacy code?
  * Legacy includes clean
  * Clean includes legacy
  * They totally overlap (disjunction is empty)
  * they partially overlap
  * Disjoint sets (no overlapping)
  
* for a visual representation of overlapping sets, see [here](http://www.codeproject.com/Articles/33052/Visual-Representation-of-SQL-Joins)
* for more information on Venn diagrams, see [its wikipedia page](http://en.wikipedia.org/wiki/Venn_diagram)

  

## My way of getting there

I'm trying to create code that is legacy, but still clean code. The responsibilities should be separated, naming, SOLID, KISS, etc. And I'm finding more and more difficulties to write it, so it does not always exploit the same (few) smells:

  * TODO smell 1: too many dependencies. breaking dependencies
  * TODO smell 2: tests are too high-level / slow / not good enough
  * TODO smell 3: so many complicated codes after stack of patches.
  * TODO smell 4: lack of refactoring


## Why writing legacy code with TDD is harder

  * you follow dependency injection and therefore, greatly reduce hardcoded dependencies
  * functions without side effects are easier to test than effectful ones

TODO: idea - spikes where you have the failing test in your head. is this the same
