---
tags:
  - FP
  - Lecture
---
---
## Impurity
**has state**, haskel code as a fundamental fact is stateless - a by product of mutation.
**side effect free** - it does not IO, play a beep or show a ui output (outside world)
**total** - defined for all inputs

**benefit**
- ensures repeatability - a function will always evaluate the same if parameters are the same.
- allows mathematical reasoning - not sure why

**why we need side effects**
- allow networking
- get time
- graphics

Naively
![[Pasted image 20241025100122.png]]
removed commutivity
destroys lazy eval

# IO Types
solve the above problem

getLine :: String -> IO ()
maps type String to IO computation - this IO computation will return a string on run
reverse getLine would return error since reverse acts on array but getLine returns IO ()
this allows pure impure seperation!

key word **do** is used to describe a computation on IO

getAndReverse :: IO String
getAndReverse = **do**
	str <- getLine
	let revStr = reverse str
	return revStr
this <- operator is not running getLine, instead jsut describing for when it is.

main :: IO ()
main = do
	getAndReverse

this is how to start and IO comp


