/*
Alivia Kliesen and Cheko Mkocheko

Outside Sources of Help: n/a

*/

Files Required to Run Program:
 1.    DecisionTree.java
 2.    Example.java
 3.    TestClassifier.java
 4.    TreeNode.java
 5.    TestClassifierIncome.java
 6.    income-train-final.txt
 7.    income-test-final.txt
 8.    TestClassifierHepatitis.java

Known Bugs:
	none

Part 2a

  1. How does the decision tree perform on the big sets? Explain results.

Our DecisionTree algorithm has same accuracy and tree as expected for set1 big.
The results show that our algorithm will always output correct values when the
 training data is noise free. The algorithm neither overfits nor under fits the
 data, and there are neither false positives nor false negatives. it has 100%
 accuracy due to the fact that there is no noise in the training data.

Positive examples correct: 100 out of 100
Negative examples correct: 100 out of 100

Similarly our algorithm has the same accuracy and tree as expected for set2 big.
There are 6 false negatives and 5 false positives with a total accuracy rate of
94.5%. The reason that set2 big does not have the same accuracy as set1
big on the test data is that set2 big contains noise and set1 big does not.
Noise refers to the concept that some of the examples in the training dataset
for set2 big that have negative labels share properties that all positive labeled
examples have, which reduces the accuracy of the final decision tree on the
testing dataset. 

Positive examples correct: 94 out of 100
Negative examples correct: 95 out of 100

Differences in accuracy (even when data is noise-free) may be caused by differences
in decisions regarding tie-breaking. For instance, if there are an equal number
of positive and negative labels at a decision node, then the choice of a positive
or negative label is arbitrary (and may be chosen differently by two correct
decision tree algorithms).

Part 2b

  1. How does the decision tree classify hepatitis patients?

	The decision tree classifies hepatitis patients by first looking at whether
  they have varices, and if they don’t have them, then they will survive if
  their histology is false and die if their histology is true. If they do have
  varices, then the decision tree next looks at whether their SGOT test levels
  are greater than 156 or less than 156. If their SGOT test levels are greater
  than 156, then they will only survive if their liver is big and they have
  malaise, or in cases with a big liver and no malaise, only males older than
  30 and females will survive. All other cases not mentioned if SGOT test levels
  are greater than 156 will die. If SGOT test levels are less than 156 and if
  bilirubin levels are greater than 2.9, then anorexic patients will survive
  and non-anorexic patients will die. In cases where bilirubin levels are
  less than or equal to 2.9, all those younger than 31 or older than 50 will
  survive. For those between the ages of 31 and 50, then they will survive
  if they are experiencing fatigue. If they are not experiencing fatigue,
  then they will survive if they don’t have anorexia. The only people
  between the ages of 31 and 50 who die have no fatigue, do have anorexia,
  do have a big liver, and do not show signs of spiders. All others
  between the ages of 31 and 50 will survive.

  2. 86.54% of examples were correctly classified. There were 3 false positives
   and 4 false negatives.

Part 3

  1. Name of the dataset:Income Dataset

  2. Source of dataset: kaggle (https://www.kaggle.com/datasets/mastmustu/income)

  3. This dataset contains demographic information on people who either have an
  income greater than 50k a year or less than 50k a year. It contains information
   such as their age (which we split into 15 binary groups of 5 year increments),
   workclass (employer), education (split into binary groups), marital status,
   occupation, race, gender, number of hours per week (9 binary groups of 10 hour
  increments), and native country (US vs. non-US).

  4. Number of examples in the dataset: There were 43957 examples originally in
  the data set, and we used the first 200 examples for our training dataset and
   the second 200 examples for our testing dataset.

  5. Number of features for each example: In our altered dataset (altered to
  make it binary), we had 78 features.

  6. Our decision tree performed fairly well on the dataset in terms of classifying
  negative examples from the testing dataset (around 80% accuracy), but it didn’t
  do as well classifying positive examples (about 60% accuracy). This indicates
  that our decision tree has a case of overfitting since it is under classifying
  positive examples. We believe this is because our data may have too many
  specific features, particularly in the case of features related to age (there
  were 15 separate binary-coded age groups) and features related to number of hours
  per week (there were 9 separate binary-coded groups). Given additional time, we
  would create binary-coded groups with larger ranges for age and number of hours
  worked per week (so that there would be less individual groups for each
  category overall).

  7. 77.5% of examples were correctly classified. There were 18 false negatives
  and 27 false positives.
