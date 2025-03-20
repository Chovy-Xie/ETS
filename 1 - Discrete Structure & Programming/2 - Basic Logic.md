# Week 2: Basic Logic (Propositional & Predicate Logic, De Morgan's Laws)


## Truth Table
> AND(∧), OR(∨), NOT(¬), IMPLIES(→)

```
	P	Q		P∧Q		P∨Q		¬P		P→Q 	P↔Q
	
	T	T		T		T		F		T		T
	T	F		F		T		F		F		F
	F	T		F		T		T		T		F
	F	F		F		F		T		T		T
```


## Logical Equivalence
> P ≡ Q

### Fundamental Logical Equivalences

- Identity Laws
	- P ∧ true ≡ P
	- P ∨ false ≡ P

- Domination Laws
	- P ∨ true ≡ true
	- P ∧ false ≡ false

- Idempotent Laws 
	- P ∨ P ≡ P
	- P ∧ P ≡ P

- Double Negation
	- ¬(¬P) ≡ P

### De Morgan's Laws

- Negation of AND
	- ¬(P ∧ Q) ≡ ¬P ∨ ¬Q
	- e.g., "it's not the case that both A and B are true" is the same as "Either A is false or B is false"

- Negation of OR 
	- ¬(P ∨ Q) ≡ ¬P ∧ ¬Q
	- e.g., "it's not the case that A or B is true" is the same as "Both A and B are false"

### Implication Equivalences

- Implications can be rewritten using OR
	- P → Q ≡ ¬P ∨ Q
	- e.g., "if it rains, then the ground is wet" implies "it doesn't rain or the ground is wet"

- Contrapositive is logically equivalent to an implications
	- P → Q≡ ¬Q → ¬P
	- e.g., "if I study, then I pass" is the same as "if I don't pass, then I didn't study"

### Distributive and Absorption Laws 

- Distributive Laws 
	- P ∧ (Q ∨ R) ≡ (P ∧ Q) ∨ (P ∧ R)
	- P ∨ (Q ∧ R) ≡ (P ∨ Q) ∧ (P ∨ R)
	- e.g., "I will buy (apples OR oranges) if they are cheap" is the same as "I will buy apples if they are cheap OR I will buy oranges if they are cheap"

- Absorption Laws
	- P ∨ (P ∧ Q) ≡ P
	- P ∧ (P ∨ Q) ≡ P
	- e.g., "I will study OR (I will study AND play) simplifies to "I will study"


## Quantifiers
> Universal Quantifier (∀), Existential Quantifier (∃)

### Universal Quantifier (∀) - "For all"
> ∀ expresses that a statement is true FOR ALL elements in a given domain

- Notation: ∀x ∈ D, P(x)
	- This reads as "for all x in domain D, P(x) holds"
	- Equivalent to saying: "P(x) is true for every x in D"

- Mathematics Example: ∀x ∈ R, x^2 ≥ 0
	- "For all real numbers x, x^2 is non-negative"

- Programming (Loop Condition)
```
// checks if all elements in numbers are positive
all_positive = all(x > 0 for x in numbers)
```

- Negation of ∀ (Using De Morgan's Law): ¬(∀x ∈ D, P(x)) ≡ ∃x ∈ D, ¬P(x)
	- This means "it's not true that P(x) holds for all x" is the same as saying "there exists some s for which P(x) is false"

### Existential Quantifier (∃) - "There exists"
> ∃ expresses that there is at least one element in the domain for which the statement is true 

- Notation: ∃x ∈ D, P(x)
	- Reads as "there exists an x in domain D such that P(x) holds"

- Mathematics Examples: ∃x ∈ Z, x^2 = 9
	- "There exists an integer x such that x^2 is equal to 9 (i.e., x = 3 or x = -3)

- Programming 
```
// checks if there is at least one negative number in the list
has_negative = any(x < 0 for x in numbers)
```

- Negation of ∃ (Using De Morgan's Law): ¬(∃x ∈ D, P(x)) ≡ ∀x ∈ D, ¬P(x)
	- Meaning: "it's not true that some x satisfies P(x)" is the same as "for all x, P(x) is false"

### Quantifier Interactions & Logical Equivalences

- Implication with Quantifiers: ∀x, P(x) → Q(x) ≡ ∀x, ¬P(x) ∨ Q(x)
	- ∀x ∈ Z, (x is even → x is divisible by 2)
	- e.g., "if a number is even, then it's divisible by 2"

- Mixing ∀ and ∃: Order Matters!
	- ∀x∃y, P(x, y) != ∃y∀x, P(x, y)
	- e.g., "for every student, there exists a book they like" (Different books for different students)
	- e.g., "there exists one book that every students likes" (One specific book liked by all)

	- Common Mistakes in Negations
		- Incorrect: ¬(∀x, P(x)) = ∀x, ¬P(x)
		- Correct: ¬(∀x, P(x)) = ∃x, ¬P(x)