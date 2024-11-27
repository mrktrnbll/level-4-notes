---
tags:
  - FP
  - Lecture
---
---
## Tuples
Like python tuples, used to pair different type of variables.
In a tuple pair functions fst and snd return first and second respectivly. Otherwise use
let (x,y,z) -> ("hello", 100, "bye")

## Functions
let func = (\\name -> "hello, " ++ name)

func "mark" return "hello mark"
 
multiple parameters take tuple and access - annoying because package unpackage tuple needed 

**solution is CURRYING**
this is ugly bracketed nested funciton shit :,(

some function n1 and another n2
((\\n1 -> (\\n2 -> n1 + n2)) 5) 10


## Function Composition
the operator . is a short hand for currying??
it performs function g where g is f(h(x)) and syntax is
show . add10 
where f(x) is show and h(x) is add10

## Equations are not Assignments
x = x +1 in python would do this one...
Haskell will do this forever, it is trying to evaluate x by reference of itself - recursion

## Parametric Polymorphism
defining a function that can take lots of different types from same params
type variable solve this??

---
# Lists
[1,2,3] :: [Int]

let infiniteList = [0..]

take 10 infiniteList 
[1,2,3,4,5,6,7,8,9,10]

infinteList
Indefinite list to infinity.

**lazy defintion**
this is where we dont care what it acc is until we evaluate

## list comprehension
haskel allows set builder notation work in list comphensions

## indexing


## zipping
zip key word take two arrays and returns the list with these in lists
zip (a :: [], b :: []) -> [(a, b)]
if not same list it performs until it can.. ocamle throws error

zipWith ( 'x' )
will point wise multiply the lists together return 1 list

---
# Bindings

**let**

**where**

---
# Case Expressions
