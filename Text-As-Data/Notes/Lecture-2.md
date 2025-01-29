---
tags:
  - TAD
  - Lecture
---
---
# Set Based Similarity Drawbacks
Issue with setbased similarity is weighting of words, frequency not accounted, rarity of a word in any type of document and more

# Sparse Vectors

### This is all term-frequency
changing a set to vector.
**creating a dictionary**
- go through all documents and create a bit list of all the recurrence of the tokens

**problem**
- a list of recurrence of tokens of  since the english language is big and document space is smaller
[1,0,0,3,0,0,2,0,38, ...]

**sparse representation**
[(1,3), (5,6), (19,1), (26,3), ...]
(tokenID, recurrence)

if the representation is sparse many zeros then use later, if has many recurrences then use binary list thingy

**what is a word is passed in and you dunno** - add a unknown enum state and count it.
**allow punctation?** - probably not but some cases are relevant, n't does give value

### example
![[Screenshot 2025-01-21 at 13.37.53.png]]
### IDF
inverse document frequency - number doc / (log(word frequency))

this weight frequent words less important and rare ones more

### Zipf's law
Cool graph displaying rank vs frequency - rank is t index of sorted frequency list 

---
# Geometric Space
**instead of the list of tupil representation above**
- have an N-dimensional array where N is the number of unique tokens.
- vectors in this space are documents.
 ![[Screenshot 2025-01-21 at 14.06.07.png]]
nice little diagram
**euclidian distance** - doesn't work great because these are far apart
**use angle** - better and many geometric ideas we can apply
**cosine correlation** - is one of these cos(V1, V2) = V1 . V2 / (|V1| * |V2|)

---
# Clustering
