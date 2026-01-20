Both files contain SageMath code to implement algorithms defined in LINK TO PAPER.

## bperm.md
This file has one function 'bperm' which takes a single argument of type DyckWord and returns a Permutation. 
This function implements Algorithm NUMBER of LINK TO PAPER. 
It returns bperm d for any Dyck path d defined in Definition NUMBER of LINK TO PAPER.

## vperm.md
This file contains three functions:
The function 'can' takes two arguments, a DyckWord and a Permutation, and returns a list. It returns the canon permutation associated to the Dyck path and permutation.
The function 'is_contained' takes two arguments, both of type DyckWord, and returns a bool. This checks if the first Dyck path is contained in the other (REFERENCE).

The function 'vperm' takes a single argument of type DyckWord and returns a Permutation. 
This function implements Algorithm NUMBER of LINK TO PAPER. 
It returns vperm d for any Dyck path d defined in Definition NUMBER of LINK TO PAPER.
