---
tags:
  - TAD
  - Lecture
---
---
# Contextual Word Embeddings
### Word Vectors
![[lingust-quote.png]]

Doing this -> take the surrounding words to a single word.
watch = {video: 3168, apple: 1702, time: 868}
clock = {time: 2614, hour: 806, alarm: 438}
elephant = {baby: 108, species: 100, ears: 97}

These are called **Distributiional word vectors**

vectors become really large, they are hard to calculate

How to compress sparse to dense vectors -> Truncated Singular Value Decomposition (SVD)

Word2Vec is a downloadable tool and dict for all english language word

**Limitations**
- good for handling words that are kind of unique
- bad for polysemy - match means football game, puzzle solve, pairing extra and since the word is described by the words around then this mean match has large *vector variance*

### Context into Vectors
instead of vector(word) we want vector(word | context) where | is where
Deep learning type stuff

Big innovations:
- self attention
- subword-tokenisation
- transformers
- language model pre-training

### Self Attention
From word vectors where to we place relevance on the word? the 5 around might be filler...

The functions we want:
- add_context('match' | 'the', 'burns', 'brightly') : vectors
- relevance('the' | 'match') G(vector/vector) = 12.1
	relevance('burns' | 'match') = 89.3
	

### Subword Tokenisation
To avoid UNK tokenisation - instead split known words up
staycation deepfake cryptocurrency microfinance onboarding truthiness annoyingly

This will depend on language and type of text - tweet vs science
Benefit
- more likely to see subwords
- give idea of new words
- can reduce overall vocab size

**Byte Pair Encoding - (BPE)**
algorithm - [[Text-As-Data/Lecture-Slides/Lecture-5.pdf#page=46&selection=17,13,17,14|Lecture-5, page 46]]

example: peter piper picked a peck of pickled peppers

split - ([p,e,t,e,r], [p,i,p,e,r], [p,i,c,k,e,d], [a], [p,e,c,k], [o,f], [p,i,c,k,l,e,d], [p,e,p,p,e,r,s])

current vocab - [a,c,d,e,f,i,k,l,o,p,r,s,t]

most frequent par = ('p', 'e') - merge

split is now - [pe,t,e,r], [p,i,pe,r], [p,i,c,k,e,d], [a], [pe,c,k], [o,f], [p,i,c,k,l,e,d], [pe,p,pe,r,s]

new vocab - [a,c,d,e,f,i,k,l,o,p,r,s,t,pe]

in the end
learned vocab is - [a,c,d,e,f,i,k,l,o,p,r,s,t,pe,pi,ck,per,pick]

