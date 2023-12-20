---
{"dg-publish":true,"permalink":"/big-o/"}
---

defines a set of functions with a similar upper bound 
# Formal Definition 

>Let $f : \mathbb{N}_0 \to \mathbb{R}^+$ and $g : \mathbb{N}_0 \to \mathbb{R}^+$ be functions where $g(n)$ is strictly positive for large enough values of $n$. Then,  $f(n) \in O(g(n)) \leftrightarrow \exists_c\;,\forall_n \geq n_0 \; (|f(n)|\leq c \cdot g(n))$
>
>where $c\in\mathbb{R}^+$ and $n_0\in \mathbb{N}_0$ . The notation $f(n) = O(g(n))$ is also often used to denote $f(n)\in O(g(n))$. 


Ok.. Let's uncover what this means: 

| Symbol                | Meaning                                                                                      |
| --------------------- |:-------------------------------------------------------------------------------------------- |
| $\mathbb{N}_0$        | set of natural numbers (includes 0)                                                          |
| $\mathbb{R}^+$        | set of *positive* real numbers                                                               |
| $x \in S$             | $x$ is an element of a set denoted by $S$ ($x$ is in $S$)                                                   |
| $f :A \to B$          | $f$ is a function w/ domain set $A$ and codomain set $B$ ($f$ is a function from $A$ to $B$) |
| $a \leftrightarrow b$ | $a$ if, and only if $b$ ($a$ iff $b$)                                                        |
| $a \to b$             | $a$ implies $b$                                                                              |
| $O(\cdot)$            | Big-O of $\cdot$                                                                             |

So in other words, we can read this as: Let $f$ and $g$ be function from the set of integer or the set of real numbers to the set of real numbers, We say that $f(x)$ is $O(g(x))$ if there are constants $C$ and $k$ such that $|f(x)| \leq C|g(x)|$, whenever $x > k$ and $c$ and $k$ are called **witnesses** to the relationship $f(x)$ is $O(g(x))$. 
# How to derive Big-O
>[!WARNING] Caution!
> Depending on the context, there may be more or less strict definitions of Big-O. Generally, it is acceptable to state the Big-O as the tightest bound of a function. However is cases (such as proofs), it can include functions with higher bounds, as long as it's greater than the function. 
## sets + simple functions 
Prove $T(n)\in O(n^2)$ , when $T(n) = 2n^2+3n-2$. 
	*Using implication, slowly increase the terms*
	$T(n) = 2n^2 + 3n - 2$
	$\implies T(n) \leq 2n^2 + 3n + 2$
	$\implies T(n) \leq 2n^2 + 3n^2 + 2$
	$\implies T(n) \leq 2n^2 + 3n^2 + 2n^2$
	$\implies T(n) \leq (2 + 3 + 2)n^2$
	$\implies T(n) \leq 7n^2$
	 $\hphantom{\implies} \therefore  T(n) \leq c \cdot n^2$, where $c=7$

If you're looking at code excerpts, look at [[Algorithm Analysis\|Algorithm Analysis]]! 
## formal proofs
In a more rigorous setting, let's take a look at big-O here: 

Example: Show that $f(x) = x^2 + 2x + 1$ is $O(x^2)$ 
Let us proceed [[Proofs#Direct Proofs\|directly]]. 
1) $x^2 \leq x^2$, $\forall x>1$ 
2) $2x \leq x^2$, $\forall x>2$ 
3) $1 \leq x^2$, $\forall x>1$ 
4) $x^2 + 2x + 1 \leq 3x^2$, $\forall x > 2$ 
Thus with $k = 2$ and $C = 7$, as witnesses $f(x) = x^2 + 2x + 1$ is $O(x^2)$ by definition of big O $\blacksquare$. 

Example: Show that $7x^2$ is $O(x^3)$
Let us proceed directly. 
1) $7x^2 \leq 7x^3$, $\forall x > 1$ -> $0$ doesn't work b/c $7.01^2 > 7.01^3$ 
With $k = 1$ and $C = 7$ as witnesses for $7x^2$ is $O(x^3)$ $\blacksquare$. 

Example: Show that $n^2$ is not $O(n)$ 
Let us proceed using a proof by contradiction. Assume $n^2$ is $O(n)$. By definition of big-O. there exists $C$, $k \in \mathbb{R}$ s.t...
1) $|n^2| \leq C|n|$, $\forall n > k$ 
2) $n^2 \leq C|n|$, $\forall n > k$ since $n^2 > 0$, $\forall n$ 
If $k$ is negative, choose a new $k$ to be positive that gives...
3) $n^2 \leq C \cdot n$, $\forall n > k$ 
4) $n \leq C$, $\forall n > k$
Note that this is a contradiction because $C$ is a constant and since $n$ grows infinitely, $n$ can't be bounded by $C$. We can always find a $n > C$. Thus our assumption was wrong, which means that $n^2$ is not $O(n) \blacksquare$.

>Theorem: Let $f(x) = a_nx^n + a_{n-1}x^{x+1}+\dots+a_1x+a_0$, where $a_0, a_1, \dots, a_{n-1}, a_n$ are real numbers. Then $f(x)$ is $O(x^n)$. --> big o is the degree of polynomial
> 
>When $f(x)$ is a rational function, then the big-O is the difference in the degree of the numerator and denominator! 

Example: How can big-o be used to estimate the sum of the first $n$ positive integers? 
$1 + 2 + 3 + \dots + n$ where $n \geq$ all terms in this sum; replace with n 
$1 + 2 + 3 + \dots + n \leq n + n + n + \dots + n = n^2$ -> we can estimate the sum with $n^2$ 

Example: Show that $log(2x)$ is $O(log(x))$ 
1) $log(2x) = log(2) + log(x)$  
2) $log(2) \leq log(x)$, $\forall x \geq 2$ 
3) $log(x) \leq log(x)$, $\forall x \geq 1$ 
4) $log(2) + log(x) = $log(2x) \leq log(x)$, $\forall x \geq 2$, which $C = 2$ and $k=2$ as witnesses. 
Therefore, $log(2x)$ is $O(log(x))$. 

>Theorem: Suppose that $f_1(x)$ is $O(g_1(x))$ and that $f_2(x)$ is $O(g_2(x))$. Then $(f_1+f_2)(x)$ is $O(g(x))$,  where $g(x) = (max(|g_1(x)|, |g_2(x)|)$ for all $x$. 
>  
> Suppose that $f_1(x)$ and $f_2(x)$ are both $O(g(x))$. Then $(f_1+f_2)(x)$ is $O(g(x))$ 

Example: Prove that $log(x^4)log(x^5)$ is $O(x^2)$
$log(x^4)log(x^5) = 4log(x) \cdot 5log(x) = 20log(x)log(x)$ 
- $20 \leq 20 \cdot 1$, $\forall x > 1$
-  $logx \leq x \cdot 1$, $\forall x > 1$
-  $logx \leq x \cdot 1$, $\forall x > 1$
$20$ is $O(1)$, with $C=1$, $k=1$ as witnesses 
$logx$ is $O(x)$, with $C=1$, $k=1$ as witnesses 
$logx$ is $O(x)$, with $C=1$, $k=1$ as witnesses 
By the theorem, $20log(x)log(x) = log(x^4)log(x^5) = O(1*x*x) = O(x^2)$

## Notable Complexity Classes 
| Name         | Set          | Example |
| ------------ | ------------ | ------- |
| Constant     | $O(1)$     |$f(n)=42$         |
| Logarithmic  | $O(log(n))$ |$f(n)=2log(n)+1$         |
| Linear       | $O(n)$     |$f(n) = 4n+2$        |
| Linearithmic | $O(nlog(n))$ |$f(n)=3nlog(n)+2n$        |
| Quadratic    | $O(n^2)$     |$f(n)=5n^2+3n$         |
| Cubic        | $O(n^3)$     |$f(n)=2n^3+n^2+2$         |
| Polynomial   | $O(n^k)$     |$f(n)=c_kn^k+c_(k-1)n^(k-1)+\ldots+c_1n^1+c_0n^0$         |
| Exponential  | $O(k^n)$     |$f(n)=2^n+5$         |

Graphical View: 
```tikz 
\begin{document} 
	\begin{tikzpicture}[domain=0:4, yrange=0:4] 
		\draw[very thin,color=gray] (-0.1,-0.1) grid (4.0,4.0); 
		\draw[->] (-0.1,0) -- (4.2,0) node[right] {$x$}; 
		\draw[->] (0,-0.1) -- (0,4.2) node[above] {$f(x)$}; 
		\draw[color=blue] plot (\x,\x) node[right] {$O(log(n))$}; 
		\draw[color=green] plot (\x,\x+1) node[right] {$O(1)$}; 
		\draw[color=purple] plot (\x,\x) node[right] {$O(n^2$}; 
		
	\end{tikzpicture}
\end{document} 
```


![Pasted image 20230518112424.png](/img/user/Pasted%20image%2020230518112424.png)
