Both files contain SageMath code to implement algorithms defined in the paper: [How to bounce your canon permutation](http://arxiv.org/abs/2603.22565).

## bperm.md
This file has one function 'bperm' which takes a single argument of type DyckWord and returns a Permutation. 
This function implements Algorithm 3.6 of the paper. 
It returns bperm d for any Dyck path d (see Definition 3.7 of the paper).

## vperm.md
This file contains three functions: 
The function 'can' takes two arguments, a DyckWord and a Permutation, and returns a list. 
This list is the canon permutation associated to the Dyck path and permutation.

The function 'is_contained' takes two arguments, both of type DyckWord, and returns a bool. 
This checks if the first Dyck path is contained in the second, i.e., if the first Dyck path is always under the second when drawn in the plane.

The function 'vperm' takes a single argument of type DyckWord and returns a Permutation. 
This function requires the functions 'can' and 'is_contained' to be defined. 
This function implements Algorithm 5.3 of the paper. 
It returns vperm d for any Dyck path d (see Definition 5.4 of the paper).
