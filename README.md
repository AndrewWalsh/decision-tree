# decision-tree

A [Decision Tree](https://github.com/AndrewWalsh/decision-tree/blob/main/decision_tree.ipynb) applying the `CART`, `ID3`, and `C4.5` algorithms. Decision trees consist of two types of node. *Decision nodes* are split points that route to another branch based on an attribute test. *Leaf nodes* are outcomes in the target class.

- **No third party libraries** other than `pandas` are used to create the decision tree
- Only utility functions from `sklearn` are used to visualise data or help with routine tasks
- Mathematical definitions for functions are defined at the end of the document

## CART: Classification & Regression Tree

- Uses gini impurity to select splits that result in the most homogeneous subsets
- For the attribute test, the weighted gini impurity is the sum of each gini impurity weighted against the probability of the attribute value

## ID3: Iterative Dichotomiser 3

- Uses Shannon entropy to estimate the randomness of subsets following a split on an attribute
- Each split is evaluated through information gain, the expected reduction in entropy
- Decision nodes split the dataset into subsets which maximise information gain

## C4.5 (classification, partial implementation)

- Uses information gain and split information
- Weights a split by accounting for an attribute's branching potential
- Reduces bias towards attributes with greater cardinality
- Not implemented:
  - Ross Quinlan discussed quite a few features, including tree pruning, early-stopping, handling missing values
  - These are not implemented. Only the calculation of InformationGainRatio by virtue of SplitInformation is used
  - This also means that continuous values are not handled

## Dataset Limitations

- Values are assumed to be nominal, and cannot be continuous
- Two output classes `p` `q` of the form 'Yes', 'No', or 1, 0 are assumed

Anonymised patient data detailing [a clinical outcome of a stroke](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset) is used to illustrate classification.


