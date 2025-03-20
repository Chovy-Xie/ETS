# Week 1: Functions, Relations, & Sets


## Functions: Injective (one-to-one), Surjective (onto), Bijections (injective+surjective), Inverse Functions 

### One-to-One (Injective) Function 
> if different inputs always produce different outputs

Def: f(x1) = f(x2) => x1 = x2

e.g., f(x) = 2x + 3 is injective because: 

2a + 3 = 2b + 3 => a = b

e.g., f(x) = x^2 is not injective because: 

f(2) = 4, f(-2) = 4 => 2 != -2

### Onto (Surjective) Function 
> if every element in the codomain has at least one preimage in the domain

Def: A -> B is surjective if ∀y ∈ B, ∃x ∈ A such that f(x) = y

e.g., f(x) = x - 3, where f: R -> R, is surjective because every real number y has a corresponding x = y + 3

e.g., f(x) = x^2 where f: R -> R, is not surjective because negative numbers in the codomain (e.g., -1) have no preimage in R


## Relations: Reflexive, Symmetric, Transitive
> Relation is equivalence iff it's reflexive, symmetric, and transitive

### Reflexive
> (a,b) ∈ R for all a in A

e.g., R = {(a,b) | a ≡ b (mod 3)}

Reflexive: a ≡ a

### Symmetric
> (a,b) ∈ R => (b,a) ∈ R 

e.g., R = {(a,b) | a ≡ b (mod 3)}

Symmetric: if a ≡ b, then b ≡ a 

### Transitive
> (a,b) ∈ R and (b,c) ∈ R => (a,c) ∈ R 

e.g., R = {(a,b) | a ≡ b (mod 3)}

Transitive: a ≡ b and b ≡ c, then a ≡ c

R = {(a,b) | a ≡ b (mod 3)} is an equivalence relation. 


## Sets & Operations

### Union
> A ∪ B, elements in A or B 

A = {1,2,3}, B = {3,4,5}

A ∪ B = {1,2,3,4,5}

### Intersection
> A ∩ B, elements in both A and B

A = {1,2,3}, B = {3,4,5}

A ∩ B = {3}

### Complement
> A', elements not in A

U = {1,2,3,4,5}, A = {1,2}

A' = {3,4,5}

### Cartesian Product
> A × B, Ordered pairs (a,b) where a ∈ A, b ∈ B

A = {1,2}, B = {3,4}

A × B = {(1,3), (1,4), (2,3), (2,4)}