
The algorithm used behind decision tree is ID3 algorithm. The ID3 algorithm builds trees using a top-down, greedy approach. 

#### Steps are as blow:

1. identify the attributes and classifications (target) in the training set.
2. determin the best attribute in the training set. The best attribute is the one splits the data with the lowest impurity.
3. split the training set into subgroups corresponding to the groups of the best attribute.
4. start building the tree with the best attribute as the root.
5. repeat step 2 to step 4 with the subgrouped data in step 3.
  - attributes cannot be reused
  - if there is no more attributes to split on, then choose the most popular classfication as the final result
  - each subset from a node/root will run step 2 to determine the best attribute and repeat the spliting

#### Pseudocode:

```
def id3(examples, classification_attribute, attributes): 
  creat a root node for the tree
  if all examples are positive/yes:
    return root node with positive/yes label
  else if all examples are negative/no:
    return root node with negative/no label
  else if there are no attributes left:
    return root node with most popular classification_attribute label
  else:
    best_attribute = attribute from attributes that best classifies examples
    for each value in best_attribute:
      add branch below root node for the value
      branch_examples = [examples that have that value for best_attribute]
      if branch_examples is empty:
        add leaf node with most popular classification_attribute label
      else:
        add subtree id3(branch_examples, classification_attribute, attributes - best-attributes)
  
```

#### Best Attribute

In ID3, the best attribute is defined as the one bringing the most information gain, measuring how well the attribute split the subsamples. Entropy is used quantity information gain and measuring the purity of the split. Entropy equals to 0 that means all classification in a subgroup is the same. If entropy equals to $log_{2}{n}$, where n is the number of categories of the target variable.

$$Entropy(S) \=\ -\sum_{i=1}^{C} p_{i}\\log_2 p_{i}$$









