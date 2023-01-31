# Random Experiment
An experiement where all possible outcomes are known but the result of one instance of conducting the experiment is not known.
# Sample Space
The set of all possible outcomes of a RE.
# Event
A subset of outcomes in which we are interested.
# $\sigma$-Algebra $\mathscr{A}$
## The good set principles
1. Probability is defined on events.
2. Probability of whole space must be known.
3. Probability of something not happening must be known if that of it's happening is known
4. Probability of things happening together must be known.
## Requirements
1. $\mathscr{A}\subseteq2^{\Omega}$
2. $\Omega\in \mathscr{A}$
3. $A\in \mathscr{A} \implies A^C \in \mathscr{A}$
4. $\{A_n\}_ 1^{\infty}\subseteq \mathscr{A} \implies \bigcup_1^{\infty}\in \mathscr{A}$
## Examples
1. $\{\phi,\Omega\}$
2. $2^{\Omega}$
3. $\sigma(A)=\{\phi,\Omega,A,A^C\}$
4. **Borel $\sigma$ Algebra**:= $\sigma(\{open\ subsets\ of\ \mathbb{R}\})$
5. $\sigma(A_1,\dots,A)$ with $2^{2^{n}}$ elelements.

# Probability Axioms
1. $Pr:=$ $\mathscr{A} \rightarrow [0,1]$, a bounded measure function defined on the sigma algebra called the event space.
2. $Pr(\Omega)=1$
3. **Countable Additivity**, i.e $Pr(\bigsqcup_1^{\infty}A_i)=\Sigma_1^{\infty}Pr(A_i)$

## Derived Propositions
1. $Pr(\phi)=0$
2. Finite Additivity
3. $Pr(A^C)=1-Pr(A)$
4. $A_1 \subseteq A_2 \implies Pr(A_1)\le Pr(A_2)$, i.e, monotonicity of $Pr$ wrt subset relations, establishing a poset.

## Continuity of Probability Function
### Claim
For an increasing sequence of events $A_1\subseteq A_2\subseteq \dots \subseteq A_n\subseteq \dots$, we have $Pr(\bigcup_1^{\infty}A_i)=lt_{n\rightarrow \infty}Pr(A_n)$
### Proof

Parition $A_n$, $B_n=A_n\backslash A_{n-1}$, thus $\bigsqcup B_i=\bigcup A_i$ and from countable additivity, 

$Pr(\bigcup A_i)=Pr(\bigsqcup B_i)=lim_{n \rightarrow \infty}\Sigma_1^n Pr(B_i)$ (from the convergence of the sum due to bounded+monic-ness of the sequence)

now using finite additivity, $Pr(\bigcup A_i)=lim_{n \rightarrow \infty}Pr(\bigsqcup_1^n B_i)=lim_{n \rightarrow \infty}Pr(A_n)$


# Probability Space
The triplet $(\Omega,\mathscr{A},Pr)$ is called a probability space.
# Absolute convergence and rearrangement thm
## statement
If $\Sigma_{n\in \mathbb{N}} a_i$ is absolutely convergent, i.e., $\Sigma_{n\in \mathbb{N}} |a_i|$ converges then $\forall$ permutation functions $\pi$, we have

$\Sigma_{n\in \mathbb{N}} a_{\pi(i)}= \Sigma_{n\in \mathbb{N}} a_i$
## proof
## use
convergent series of positive values is absolutely convergent hence probabilities can be rearranged in a sum.

# Inclusion-Exluclusion Principle
$Pr(\cup_1^nA_i)=\Sigma_{k=1}^n(-1)^{k+1}\Sigma_{1\le i_1\le\dots\le i_k\le n}Pr(\cap_{j=1}^kA_{i_j})$
## proof
### base case
$Pr(A\cup B)= Pr(A) + Pr(A^C\cap B)$ but $Pr(B)=Pr(A^C\cap B)+ Pr(A\cap B)$ so that $Pr(A\cup B)= Pr(A) +Pr(B)-Pr(A\cap B)$
### induction
$Pr(\cup_1^nA_i)=\Sigma_{k=1}^n(-1)^{k+1}\Sigma_{1\le i_1\lt\dots\lt i_k\le n}P(\cap_{j=1}^kA_{i_j})$

thus, $Pr(\cup_1^{n+1}A_i)=\Sigma_{k=1}^n(-1)^{k+1}\Sigma_{1\le i_1\lt\dots\lt i_k\le n}P(\cap_{j=1}^kA_{i_j}) + Pr(A_{n+1}) - Pr(\cup_1^n(A_i\cap A_{n+1}))$

$Pr(\cup_1^{n+1}A_i)=\Sigma_{k=1}^n(-1)^{k+1}\Sigma_{1\le i_1\lt\dots\lt i_k\le n}P(\cap_{j=1}^kA_{i_j}) + Pr(A_n+1) - \Sigma_{k=1}^n(-1)^{k+1}\Sigma_{1\le i_1\lt\dots\lt i_k\le n}Pr(\cap_{j=1}^k(A_{i_j}\cap A_{n+1}))$

$=\Sigma_{k=1}^n(-1)^{k+1}\Sigma_{1\le i_1\lt\dots\lt i_k\le n}P(\cap_{j=1}^kA_{i_j} +  Pr(A_n+1) + \Sigma_{k=2}^{n+1}(-1)^{k+1}\Sigma_{1\le i_1\lt\dots\lt i_k\lt i_{k+1}=n+1}Pr(\cap_{j=1}^k(A_{i_j}\cap A_{n+1}))= \Sigma_{k=1}^{n+1}(-1)^{k+1}\Sigma_{1\le i_1\lt\dots\lt i_k\le n+1}Pr(\cap_{j=1}^kA_{i_j})$ 
## corollory
$N(\cup_1^nA_i)=\Sigma_{k=1}^n(-1)^{k+1}\Sigma_{1\le i_1\le\dots\le i_k\le n}N(\cap_{j=1}^kA_{i_j})$

assigning equal probabilities to the event of choosing any subset.

# Dearrangements
* RE: pick one of the possoble arrangements
* $\Omega:=$ set of all n-permutations
* $\mathscr{A}:=$ $2^{\Omega}$
* Assigned probabilities:= uniform
* Event of interest $Q_i$ permutations that fix the $i^{th}$ element

* required event $Q:=$permutations that fix nothing$=\cap_0^nQ_i^C$
* $\frac{D_n}{n!}=Pr(Q)=1-Pr(\cup_0^nQ_i)$ $=1-\frac{1}{n!}\Sigma_{k=1}^n(-1)^{k+1}\Sigma_{1\le i_1\lt \dots \lt i_k\le n}N(\cap Q_{i_k})$ $=1-\frac{1}{n!}\Sigma_{k=1}^n(-1)^{k+1}\begin{pmatrix}n\\k\end{pmatrix}(n-k)!$ $=1+\Sigma_{k=1}^n(-1)^k\frac{1}{k!}$

* thus, $D_n=n!(\Sigma_{k=0}^n(-1)^k\frac{1}{k!})$


# Random Variable
$X: \Omega \rightarrow \mathbb{R}$, measurable, i.e., the pullback of any borel subset of $\mathbb{R}$ is an element of $\mathscr{A}$

Now this map defines a probability on the borel-space

$Pr_X(B)=Pr(X^{-1}(B))$ defined $\forall\ B\in \mathscr{B}_ {\mathbb{R}}$

# Distribution Function
$F_X(a)=Pr_X((-\infty,a))$
1. $F_X:\mathbb{R}\rightarrow [0,1]$
2. is monotonically increasing.
3. is right continous
4. 0 and 1 are its asymptotes.

# Discrete and Continous rv
* $F_X$ is a step function $\rightarrow$ discrete rv
* density function is **absolutely continous** $\rightarrow$ continous rv
# Expected value
* Weighted Average
* Linear function
* for a countable sample space, $E(X)=\Sigma_{\omega \in \Omega}X(\omega)Pr({\omega})$

# Moment
$E(X^k)$ the kth moment of $X$
# First Momement Method
for non-ve integer valued functions $X$
* $E(X)\lt 1\implies Pr(X=0)\gt0$
* $E(X)\gt 1 \implies Pr(X\gt1)>0$
* $E(X)=1$ and $X$ is not a constant function $\implies Pr(X=0)\gt0$ and $Pr(X\gt 1)\gt0$
Use $E(X)=\Sigma p_x(x)$
# Existence of Dearrangement
* RE: pick a permutation of $[n]$ uniformly $Pr(\pi)=1/n!\ \forall\ \pi:[n]\rightarrow^{bijection}[n]$
* set $X_i(\pi)=\begin{cases} 1, & \text{if $\pi(i)=i$} \\ 0, & \text{otherwise}\end{cases}, X(\pi):=\Sigma_{i\in [n]}X_i(\pi)$ , the number of elements fixed by the permutation $\pi$
* $X$ is obviously not a constant function, and $E(X)=1$ so that we have $Pr(X=0)\gt 0$?????????????

# PHP
let there be $n$ pigeons and $m$ holes.

take a function $f:[n]\rightarrow [m]$, assigning a hole to a pigeon

* RE: pick a hole uniformly. $Pr(i)=1/m \ \forall i \in [m]$ 
* define $X_i(k):=\begin{cases} 1, & \text{if $f(i)=k$} \\ 0, & \text{otherwise}\end{cases}$, $X(k):=\Sigma_{i \in [n]}X_i(k)$, the number of pigeons in hole k
Now $E(X)=n/m$ by linearity and if $n\gt m$ then $E(X)\gt 1\implies Pr(X>1)\gt 0$


# Independence
$Pr(A\cap B)=Pr(A).Pr(B)$
