---
tags:
  - FP
  - Lecture
---
---
## Recursion

**this fucntion is recursive**
listSum :: [int] -> Int
listSum [] = 0 ### base case
listSum (x:xs) = x + (listSum xs) ### other case

### Tail recursion
tail recursive is used to avoid stack overflows.
the above is not. listSum' which is tail recursive would pass a value i as another param, it is the value that is the current some so that reference of where the step came from is just a value rather than ref to a function call

### Mutual recursion


---
## Alg Datatypes

