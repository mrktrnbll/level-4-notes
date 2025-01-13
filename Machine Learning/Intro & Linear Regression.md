---
tags:
  - ML
  - Lecture
---
---
# Intro
2 25% assessments
- one soon
- one start of Dec

**office hours**
Thursday 3:30pm - 5pm

# Lecture 1
**example**
software to identify all red squares - solution red image channel others around and map shape then identify

or give teaching data, here are a bunch of pictures with red squares identified heres another with identify -> identify for me

-> is a ml model

### learning type
**supervised**
- regression - continous 
- classification - discrete
we know the expectation of an output
classification could be is it a cat or a dog

**unsupervised**
- clustering - grouping similar objects, we dont know what might group things
- projection - reduces number of variables

projection example could be 1000 patients with 20 gene traits what patients with alopicia have commoned genes?

---
## Olympic 2012 winner

We have all winner times from 1970 for 100m sprinters
Estimate the the winner of 2012.

best fit line
**assumes** 
- that there is a relationship
- that the relation is linear
- that the relationship doesn't have a turning point

### attributes and targets
**attribute** - year
**target** - time to sprint

**model**
create a model such that
t = f(x)
when x = 2012 t evaluates to our winner time guess

t = f(x) = w0 + w1x
w0 and w1 are the parameters of the model

we will adjust these to fit our data best -> creating best model

