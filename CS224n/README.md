# Language Models
## Introduction

Language Models compute the probability of occurrence of a number of words in a particular sequence. Since the number of words comming before a wrod, varies depending on its location in the input document. The probability dostribution is usually conditioned on a window of n previous words rather than all previous words. The model will give higher scores to " the cat is small" compared to "small the is cat".

Notes: This joint probablity model is to learn the frequency the sequence words. For example, if "AABB" has the most common happens, then  given "A" the mostly like next three will be "ABB". This means the model is not really learn the word but the patterns.

## n-gram Language Models

To compute the probabilities, the count of each n-gram could be compared against the frequency of each word.  This is called an n-gram Language Model. The following equations show the relationship for bigram and trigram models.
![image](./imgs/bigram.png)
