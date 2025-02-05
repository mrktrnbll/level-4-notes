---
tags:
  - TAD
  - Lecture
---
---
# Classification of Text
Classification is task of predicting what set of classes an input belongs too

In jakes research he uses classification to find if MESH - research article heading or abstract type to group certain medical docs within correct category

spam email is a big place for classification

Types:
- Binary - cancer being benign or malignant
- Multi-class - language of text (can belong to only one set)
- multi-label - emotion expressed (may have multiple explained)

### Supervised vs Unsupervised
**Supervised** - there is a right answer, labels used to associate samples
ronas masters was supervised... it involved her assigning labels accurately - remember it took ages to setup

**Unsupervised** - no labels and used to explore data, find pattern ect

**ML uses floats not text**
Instead we use vectorisation of words via tf-idf or similar

The way in which a model is trained is well described by this graphic
![[training models.png]]

### Types of Classification Algorithms
**Majority Classifier** - really dumb. If you give training data that has >50% of not spam emails it will only return not spam.

**K-nearest neighbours** -

**Naive Bayes** - applies bayes rule and thresholds probability at 0.5 to decide pos/neg
named naive because it treats each token as independant (unigram)

**Logistic Regression** - assigns weights to input features then applies sigmoid to get prob between 0 and 1

**Support Vector Machine SVM** - treats classification as a geometry problem creates a cutting plane of the data and depending what side of plane will determine the output

**Decision tree** - if else tree that is really just a nested rule based thing

**Neural Networks** - nodes (neurons) continue search towards outcome if weight of input is high enough
![[model comparison.png]]


### ScikitLearn
lecture slides [39-41](obsidian://open?vault=level-4-notes&file=Text-As-Data%2FLecture-Slides%2FLecture-4.pdf) really just talk about doc findable functions

**Hyperparameters** - this is just the function parameters of training models in scikit - see docs and slides for informative parameters to tune

### Evaluation of Models
Split the training data! Have a training set (70%), validation and test set (30%)
compare prediction of test data against the actual data value.
![[Screenshot 2025-02-04 at 14.13.16.png]]This shows graph for Binary classifying problem - called confusion metrics

**Metrics**
- Accuracy - correct / total samples
- Precision - TP / (TP + FP)
- Recall - TP / (TP + FN)

F1 score - ties together recall and precision but **does not account for TN**
=> 2 * TP / (2 * TP + FP + FN) = 2 * precision * recall / (precision + recall)

**Multiclass problems**

![[confusion matrix for multiclass.png]]confusion matrix for multi class
performing evaluation with precision, recall and f1 scores for these. Focusing on one feature, grouping and then counting the others will condense to a 2x2 confusion like above, do this for all them and this is then used as a over view. Can perform then different average techniques:
- macro average
- micro average

**AUC** - this is another metric of model success
it takes the area under the ROC (Receiver Operation Characteristic) curve which is just the graph of true positives against false positive rate![[ROC curve.png]]
Only usable for binary classes

### K-fold Cross-Validation
