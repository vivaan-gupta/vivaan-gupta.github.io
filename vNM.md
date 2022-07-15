---
title: Von Neumann-Morgenstern
created: '2022-06-21T19:18:00.060Z'
modified: '2022-06-26T10:58:34.930Z'
katex: True
---

# Von Neumann-Morgenstern
[](======================)
## Simple Probability Measures
- <a id="SPM"></a> **Simple Probability Measures** : a simple probability measure on $$X$$ is a real-valued function $$P$$ defined on the power set of $$X$$ such that
    1. <a id="SPM.1"></a>$$\forall A\subseteq X : P(A)\geq 0$$
    2. <a id="SPM.2"></a>$$P(X) = 1$$
    3. <a id="SPM.3"></a> $$\forall A,B\subseteq X : A\cap B=\emptyset \implies P(A \cup B) = P(A) + P(B)$$
    4. <a id="SPM.4"></a>$$\exists A\subseteq X : P(A)=1 \land |A|<\infty$$ [this condition distinguishes $$P$$ as a simple probability measure]
- <a id="comb"></a> **Convex Combination of Measures** : If $$P$$ and $$Q$$ are [simple probability measures](#SPM), then $$\alpha P + (1-\alpha)Q$$, for $$\alpha \in[0,1]$$, is the function that assigns the number $$\alpha P(A) + (1-\alpha)Q(A)$$ to each $$A\subseteq X$$

$$P(\{x\})$$, which we will write as $$P(x)$$ is the probability assigned by $$P$$ to the unit subset $$\{x\}$$ of $$X$$
[](======================)
### Results
[](======================)
1. Suppose $$P$$ is a [simple probability measure](#SPM) on $$X$$, then $$P(x)=0$$ for all but a finite number of $$x\in X$$ and $$\forall B\subseteq X : P(B) = \sum_{x\in B} P(x)$$
  > **Proof**
  > Let us assume that $$P$$ is a simple probability measure 
  > Given $$P$$ is a simple probability measure ([4](#SPM.4)), we can take a set $$A$$ such that $$A\subseteq X$$, $$|A|<\infty$$ and $$P(A) = 1$$ 
  > - `finite support`
  > $$\forall x\not\in A : P(x) > 0 \lor P(x) = 0$$
  > Given $$P$$ is a simple probability measure ([3](#SPM.3)), we can say that $$P(x)>0 \implies P(A\cup\{x\}) > 1$$
  > This allows us to that $$P(X)>1$$, which gives us a contradiction ([2](#SPM.2))
  > Hence $$\forall x\not\in A : P(x) = 0$$
  > Since $$A$$ is a finite set, $$P(x)=0$$ holds for all but a finite number of $$x\in X$$
  > Q.E.D
  > - `linearly additive probabilities`
  > Let us take an arbitrary set $$B\subseteq X$$
  > $$|B|<\infty \lor |B|\not< \infty$$ 
  > Given $$P$$ is a simple probability measure ([3](#SPM.3)), $$|B|<\infty \implies P(B) = \sum_{x\in B} P(x)$$ follows immediately
  > If $$|B|\not< \infty$$, then $$C:=\{x\in B ~|~ P(x)>0\}$$ and $$D:=\{x\in B ~|~ P(x)=0\}$$
  > In that case $$C\cap D = \emptyset$$
  > Given $$P$$ is a simple probability measure ([3](#SPM.3)), $$P(B) = P(C) + P(D)$$
  > Since only a finite number of $$x\in X$$ have $$P(x)>0$$, $$|C|<\infty$$
  > Consider the set $$P_+ := \{x\in X ~|~ P(x)>0\}$$, we already know that it is finite from the first half of this proof
  > $$P(P_+)<1 \implies \forall S\subseteq X : P(S)<1$$, which gives us a contradiction ([4](#SPM.4))
  > Hence $$P(P_+) = 1$$
  > $$P(D \cup P_+) > 1 \implies P(X)>1$$, which gives us a contradiction ([2](#SPM.2))
  > Hence $$P(D) = 0$$
  > Thus $$P(B) = P(C)$$, where $$C$$ is a finite set and it can be written as a sum of singelton subset of $$X$$ ([3](#SPM.3))
  > Q.E.D
[](======================)

2. 


