---
tags:
  - FP
  - Lecture
---
---
Simon Fowler 14/10/2024

---
## Evaluation
**Lazy vs Eager Evaluation**
Haskel uses lazy evaluation - this means that it only evaluates (computes) variables when required. Where as python (in general) uses eager eval, meaning it will evaluate all values in a file before computation.

**benefit** - only evaluates when necessary and also only if used. Redundant code is not detrimental to computation time. 
**draw back** - error finding.

---
## Polymorphism
**Parametric** - shapes of arguement focused vs types of paramater
examples:
id :: a -> a
const :: a -> b -> c
map :: (a -> b) -> a -> b
filter
length

const can only be written in one way, because it is so generic it cannot be written in any other way.



**Ad-hoc** - via typeclasses acts in similar way to overwrite in java
allows reuse of same method names for method that are similar but have different logic between dif typeclasses

on creation of data MyData the method show will need to be implemented for the specific MyData typeclass.

