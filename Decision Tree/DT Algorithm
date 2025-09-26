
The algorithm used behind decision tree is ID3 algorithm. The ID3 algorithm builds trees using a top-down, greedy approach. Steps are as blow:

1. identify the attributes and classifications (target) in the training set.
2. determin the best attribute in the training set. The best attribute is the one splits the data with the lowest impurity.
3. split the training set into subgroups corresponding to the groups of the best attribute.
4. start building the tree with the best attribute as the root.
5. repeat step 2 to step 4 with the subgrouped data in step 3.
  - attributes cannot be reused
  - if there is no more attributes to split on, then choose the most popular classfication as the final result
  - each subset from a node/root will run step 2 to determine the best attribute and repeat the spliting

Pseudocode:

def id3(examples, classification_attribute, attributes):
  

