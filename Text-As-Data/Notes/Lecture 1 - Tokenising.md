---
tags:
  - Lecture
  - TAD
---
---
# Rational


---
# Tokens
Tokens are a meaningful part of text. This could be words, letters or collections of words - this could also extend to numbers or emojis, really just anything that we as humans may assign meaning to.
- to me this seems like a filtering pre-processing stage similar to normalisation or b-splitting

**three main types of possible tokens**
* letters
* n-gram (n number of letters/punctutation)
* tokens (meaningful words)

### Spacy
Spacy is a python library for tokenising text.

### Stemming
this removes common suffixes - this is not always good, can reduce different meaning words to the same, emerge and emergency -> emerg

better stemming is...
### Lemmatization
is an extension of stemming, so will not remove suffixes if they add value to the word over some other similar removed word with a suffix

### NLP Pipeline
data cleaning
tokenising
normalisation
stopword removal

---
# Similarity
similarity of documents often described by the sets of tokenised docs and then performing some similarity check on them.

list of similarity measrues:
- |X inter Y|
- |X inter Y| / min(|X|, |Y|) 