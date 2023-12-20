---
{"dg-publish":true,"permalink":"/predicate-logic/"}
---

Here the variable decides the truth value of the function. 

$x < 3$
- **Subject**: $x$
- **predicate**: $< 3$ -- =="property about the subject"==
- **Propositional function ($P$ at $x$)**: This entire statement can be represented by $P(x)$, where $P$ denotes the predicate and $x$ is the variable
- The domain of a variable is the set of all possible values for the variable

The Quantifiers have higher precedence than all logical operators than [[Propositional Logic\|Propositional Logic]] operators 
# The Universal Quantifier 
The **Universal Quantifier** of $P(x$): "$P(x$) for all values of $x$ in the domain.", written as $\forall x P(x)$; "for all $x$ $P(x)$" or "For every $x$ $P(x)$"
- Finding a single $x$ in the domain which makes $P(x)$ false creates a *counterexample* to $\forall x P(x)$ 

For example: 
- For all natural numbers $x$ and $y$, $x + y > 0$
	- This is False when you set $x = y = 0$

Overall, $\forall x P(x)$... 
- $P(x)$ is true for all $x$ 
- There is any $x$ that makes $P(x)$ false 

# The Existential Quantifier 
The **existential quantification** of $P(x$) has the proposition: "There exists an element x in the domain such that $P(x)$" or "There's an $x$ such that $P(x)$", written as $\exists x P(x)$. It's *true* as long as at least 1 $x$ makes $P(x)$ a true statement. 

For example: 
- There exits a natural number $x$, such that $3^x = 1$
	- This is True for $x$ = 0

Overall, $\exists x P(x)$... 
- There is at least 1 $x$ that makes $P(x)$ true
- All values of $x$ make $P(x)$ false

# The Uniqueness Quantifier 
**Uniqueness** means that there must exit 1 and only 1. For example: $\exists ! x P(x)$ states "There exists a unique $x$ such that P(x) is true" 

For example: 

Overall, $\exists ! x P(x)$... 
- There is at least 1 $x$ that makes $P(x)$ true
- All other values of $x$ make $P(x)$ false

# DeMorgan's Laws 
Applying DeMorgan's Laws results in such: 
- $\neg \forall x P(x) \equiv \exists x \neg P(x)$
- $\neg \exists x P(x) \equiv \forall x \neg P(x)$

# The Nested Quantifier 

A **nested quantifier** is when one quantifier is within the scope of another (ORDER MATTERS). The logical expression is a [[Propositional Logic\|proposition]] if all the variables are bound! 

Example: $\forall x \forall y (x + y > 0)$, where domain is set of real numbers 
- Negation $\exists x \exists y (x + y \geq 0)$ {not bigger than 0 means you can flip the sign :D}

Example: $\forall x \exists y (x - 2y = 5) \equiv \forall x Q(x)$ 
- where $Q(x) = \exists y P(x -2y = 5)$ where $P(x,y) = x - 2y = 5$. 

Example: Find the truth value of $\exists x \forall y (x^{2023} > y)$
- Negation: $\forall x \exists y (x^{2023} \leq y)$
- False! 

Example: Find the truth value of $\exists x \exists y (x + y = 4 \wedge x - y = 1)$
- True! 

Example: Find the truth value of $\forall x \forall y \exists z(z = \frac{(x + y)}{2023})$
- True, because you are just depended on z...  

Applying De Morgan's Law, we obtain these values: 
![Screenshot 2023-09-01 at 9.16.38 PM.png|200](/img/user/Screenshot%202023-09-01%20at%209.16.38%20PM.png)

