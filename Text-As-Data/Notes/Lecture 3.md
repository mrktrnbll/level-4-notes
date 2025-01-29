---
tags:
  - TAD
  - Lecture
---
---
# Language models
Uses predictive probabilities to evaluate the likeliness of the next word or phrase or sentence

cool use for audio input - audio processor might not know between but her or butter but within the context of other easier to understand words around filtered through LLM one makes more sense.

### Probability
**deck of cards** 
probability of 8 being drawn - 4/52
probability of card being red - 1/2

**joint probability**
8 and red - 1/26

**conditional probability**
P(A|B)
given a what is probability of b

**bayes theorm**
P(A|B) = P(B|A * P(A) / P(B)

whats the probabiliity of me shagging your maw if it is raining outside?
- this is independent - P(A|B) = P(A)


### Smoothing
if a word does not exist in the corpus then its prob of occuring is 0
this is bad so we perform smoothing
take some probability off non-zero words and give to 0 words

**laplace smooth**

**interpolated smoothing**

**Jelinek-Mercer smoothing**

### Evaluating
idealist eval 
grammatically/syntactically
P("TAD I LIKE") < P("I LIKE TAD")

semantically - conveys meaning
P(“I saw an elephant at the circus”) > P(“I saw a supernova at the circus”) P(“I saw a supernova at the planetarium”) > P(“I saw an elephant at the planetarium”)

