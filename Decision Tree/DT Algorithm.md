
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
  creat a root node for the tree<br>
  if all examples are positive/yes:<br>
    return root node with positive/yes label<br>
  else if all examples are negative/no:<br>
    return root node with negative/no label<br>
  else if there are no attributes left:<br>
    return root node with most popular classification_attribute label<br>
  else:<br>
    best_attribute = attribute from attributes that best classifies examples<br>
    for each value in best_attribute:<br>
      add branch below root node for the value<br>
      branch_examples = [examples that have that value for best_attribute]<br>
      if branch_examples is empty:<br>
        add leaf node with most popular classification_attribute label<br>
      else:<br>
        add subtree id3(branch_examples, classification_attribute, attributes - best-attributes)<br>
  
```
