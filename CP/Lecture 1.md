---
tags:
  - CP
  - Lecture
---
---
### Info
lecture notes
[lecture notes](https://github.com/magicicada/cp/blob/main/topics/intro-cp-co/intro_cp_and_co.md)

### example prob
**max clique**
on graph G= V, E a clique is a group V that make "walkable path" to each other.
max'l and max'm are decided on the number of edges in the clique. some graph with a clique with 4 edges, 3 sets of cliques with 3 edges will define the clique of four edges as max'm the rest may be max'l

**colouring vertices**
graph K -> V, E can you have number of colour <= E

**satisfiability - cnf sat**
given formula f - ands of or -> (a or b or c ) and (!b or c or !c) to be true
this is a decision - opt would be get the entrie formula to be as false as possible

## solvers
type of solvers;
- cp solvers based on search
- SAT solver
- Int programming solvers
- SIMPLEX
- not-garunteed to be optimal solvers