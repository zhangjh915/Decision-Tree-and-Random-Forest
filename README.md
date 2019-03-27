# Decision Tree and Random Forest based on C4.5 Algorithm

## Description:
An implementation of decision tree and the ensemble of decision tree- random forest based on [C4.5 algorithm](https://en.wikipedia.org/wiki/C4.5_algorithm) written in Python 3.
This model uses the "data.csv" file as the training dataset.

## Performance Metrics:
Some of the most widely used metrics are applied here to judge the performance of the model:

precision = true_positive/ (true_positive + false_positive)

recall = true_positive/ (true_positive + false_negative)

accuracy = correct_classifications / total_number_examples

[Gini Impurity](https://en.wikipedia.org/wiki/Decision_tree_learning#Gini_impurity) and [Gini Gain](https://en.wikipedia.org/wiki/Information_gain_in_decision_trees).


## Model Performance:
The accuracy of the decision tree and random forest are 0.8457 and 0.4727, respectively. The parameters might be tuned to a better performance.

## Algorithm for Decision Tree:
For this implementation of decision tree, a variational version of [C4.5 algorithm](https://en.wikipedia.org/wiki/C4.5_algorithm) is used as below:

1. Check for base cases:
   1. If all elements of a list are of the same class, return a leaf node with the appropriate class label.
   2. If a specified depth limit is reached, return a leaf labeled with the most frequent class.
2. For each attribute alpha: evaluate the normalized gini gain gained by splitting on attribute `alpha`.
3. Let `alpha_best` be the attribute with the highest normalized gini gain.
4. Create a decision node that splits on `alpha_best`.
5. Repeat on the sublists obtained by splitting on `alpha_best`, and add those nodes as children of this node

## Random Forests
For this implementation of random forest, a technique called [Bootstrap Aggregating](https://en.wikipedia.org/wiki/Bootstrap_aggregating) is used. This technique can be written as below:

1. For every tree:
   1. Subsample the examples in accordance with a provided example subsampling rate.
   2. From the sample in the first step, choose attributes at random to learn on.
   3. Fit a decision tree to the subsample of data.

2. Classification for a random forest is then done by taking a majority vote of the classifications yielded by each tree in the forest after it classifies an example.

## Code Usage:
All rights preserved. No one should use the code without permission from the author.