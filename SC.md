---
tags: [Decision Theory, Standard Choice]
title: 'Standard Choice'
created: '2022-06-19T07:25:10.236Z'
modified: '2022-06-26T13:04:54.529Z'
---

# Choice[^0]
[](----------------------------------------)
## Definitions
[](----------------------------------------)
- <a id="nonemptiness"></a> **Finite Nonemptiness** : If a choice function $$c(A)$$ is nonempty for every finite $$A \in \mathcal{P}(X)$$ 
- <a id="WARP"></a> **Choice Coherence (WARP)** : $$\forall x,y \in X$$ and $$\forall A,B \in \mathcal{P}(X)$$, $$~x,y \in A \cap B : x\in c(A) \land y\not\in c(A) \implies y\not\in c(B)$$
- <a id="complete"></a> **Completeness** : $$\forall x,y \in X : x \succcurlyeq y \lor y \succcurlyeq x$$
- <a id="transitive"></a> **Transitivity** : $$x \succcurlyeq y \land y \succcurlyeq z \implies x \succcurlyeq z$$
[](----------------------------------------)
### Results
[](----------------------------------------)
1. <a id="0.1"></a> If $$u:X \to \mathbb{R}$$, then the preference relation $$\succcurlyeq_{u}$$ defined by $$x \succcurlyeq_{u} y$$ if $$u(x) \geq u(y)$$ is [complete](#complete) and [transitive](#transitive)
  > **Proof** 
  > - `completeness`
  > Let us take arbitrary elements $$x,y \in X$$
  > $$u(x) \geq u(y) \lor u(y) \geq u(x) \implies x \succcurlyeq_{u} y \lor y \succcurlyeq_{u} x$$
  > Q.E.D
  > - `transitivity`
  > Let us take arbitrary elements $$x,y,z \in X$$
  > Let us assume that $$x \succcurlyeq_{u} y \land y \succcurlyeq_{u} z$$
  > $$x \succcurlyeq_{u} y \iff u(x) \geq u(y) \land y \succcurlyeq_{u} z \iff u(y) \geq u(z)$$
  > Since $$u(x), u(y), u(z) \in \mathbb{R} : u(x) \geq u(y) \land u(y) \geq u(z) \implies u(x) \geq u(z)$$ 
  > [Order of $$\mathbb{R}$$]
  > $$u(x) \geq u(z) \iff x \succcurlyeq_{u} z$$
  > Q.E.D
[](----------------------------------------)
2. <a id="0.2"></a> If $$u:X \to \mathbb{R}$$, then the choice function $$c_{u}(A) := \{x\in A ~⎮~ \forall y\in A : u(x) \geq u(y)\}$$, where $$A\subseteq X$$, satisfies [finite nonemptiness](#nonemptiness) and [choice coherence](#WARP)
  > **Proof**
  > - `WARP`
  > Let us take arbitrary elements $$x,y\in A\cap B$$ and let $$x\in c_{u}(A) \land y\not\in c_{u}(B)$$
  > $$x \in c_{u}(A) \implies \forall z\in A : u(x) \geq u(z)$$
  > $$y \not\in c_{u}(A) \implies \exists w\in A : u(w)  > u(y)$$
  >  $$\forall z\in A, \exists w\in A : u(x) \geq u(z) \land u(w)  > u(y) \implies u(x)   > u(y)$$ [Order of $$\mathbb{R}$$]
  > Since $$u(x)   > u(y) \land x,y\in B$$, it must be the case that $$y\not\in c_{u}(B)$$
  > Q.E.D
  > - `finite nonemptiness`
  > Let us take an arbitrary (finite non-empty) set $$A \in \mathcal{P}(X)$$
  > $$U_A := \{u(x) ~⎮~ \forall x\in A \}$$ 
  > Since $$A$$ is a finite non-empty set, $$U_A$$ is a finite non-empty set
  > Given order of $$\mathbb{R}$$, we can find an element in $$r \in U_A$$ such that $$\forall r'\in A : r \geq r'$$
  > Thus there must exist a corresponding element (to $$r$$) in $$A$$ [let's call it $$w$$] such that $$\forall y\in A : u(w) \geq u(y)$$
  > Hence $$c_u(A)\neq \emptyset$$
  > Q.E.D
[](----------------------------------------)
3. <a id="0.3"></a> If $$\succcurlyeq$$ is a [complete](#complete) and [transitive](#transitive) binary relation on $$X$$, then the choice function 
$$c_{\succcurlyeq}(A) := \{x\in A ~⎮~ \forall y\in A: x\succcurlyeq y\}$$, where $$A\subseteq X$$, satisfies [finite non-emptiness](#nonemptiness) and [choice coherence](#WARP)
  > **Proof**
  > - `WARP`
  > Let us take arbitrary elements $$x,y\in A\cap B$$ and let $$x\in c_{\succcurlyeq}(A) \land y\not\in c_{\succcurlyeq}(A)$$
  > $$x\in c_{\succcurlyeq}(A) \implies \forall z \in A : x \succcurlyeq z$$
  > $$y \not\in c_{\succcurlyeq}(A) \implies \exists w\in A : y \not\succcurlyeq w$$
  > Given $$\succcurlyeq$$ is a complete relation on $$X$$, it must be the case that $$w \succcurlyeq y$$
  > Given $$\succcurlyeq$$ is a transitive relation on $$X$$, it must be the case that $$x \succcurlyeq w \succcurlyeq y \implies x \succcurlyeq y$$
  > $$y \not\succcurlyeq x$$ since $$y \succcurlyeq x \land x\succcurlyeq w \implies y\succcurlyeq w$$ which directly contradicts $$y\not\succcurlyeq w$$
  > $$x \succcurlyeq y \land y \not\succcurlyeq x \implies y\not\in c_{\succcurlyeq}(B)$$
  > Q.E.D
  > - `finite non-emptiness`
  > Proof by induction on cardinality of $$A$$ $$\to$$ `imposes that this must be a countable set`
  > Base Case: $$⎮A⎮ = 1$$
  > Given completeness $$x \succcurlyeq x$$, thus $$x\in c_{\succcurlyeq}(A)$$
  > Assumption: Let $$c_{\succcurlyeq}(A)$$ be non-empty for $$⎮A⎮=n-1$$
  > Inductive Step: $$⎮A⎮=n$$
  > Let us take some element $$x_0 \in A$$, thus we can say $$A':= A\setminus x_0$$ where 
  $$⎮A'⎮=n-1$$
  > From the Assumption step we know that $$A'$$ has a maximal element, i.e $$\exists x\in A: \forall y\in A : x\succcurlyeq y$$
  > Given $$\succcurlyeq$$ is a complete relation on $$X$$, it must be the case that $$x \succcurlyeq x_0 \lor x_0 \succcurlyeq x$$
  > $$x\succcurlyeq x_0 \implies x\in c_{\succcurlyeq}(A)$$
  > Given $$\succcurlyeq$$ is a transitive relation on $$X$$, $$x_0 \succcurlyeq x \land \forall y\in A' : x\succcurlyeq y \implies \forall z\in A : x_0\succcurlyeq z \implies x_0\in c_{\succcurlyeq}(A)$$
  > Thus $$c_{\succcurlyeq}(A)$$ is non-empty for $$⎮A⎮=n$$ assuming that it is non-empty for 
  $$⎮A'⎮=n-1$$
  > Q.E.D
[](----------------------------------------)
4. <a id="0.4"></a> If a choice function $$c$$ satisfies [finite non-emptiness](#nonemptiness) and [choice coherence](#WARP), then 
$$\succcurlyeq_{c}~ := ~x\succcurlyeq_{c} y ~⎮~ x\in c(\{x,y\})$$ is [complete](#complete) and [transitive](#transitive)
  > **Proof**
  > - `completeness`
  > Since $$c$$ satisfies finite non-emptiness, it must be the case that $$x\in c(\{x,y\}) \lor y\in c(\{x,y\})$$
  > $$x\in c(\{x,y\}) \implies x \succcurlyeq_c y$$
  > $$y\in c(\{x,y\}) \implies y \succcurlyeq_c x$$
  > $$x \succcurlyeq_c y \lor y \succcurlyeq_c x$$
  > Q.E.D
  > - `transitivity`
  > Assume that $$x \succcurlyeq_c y \land y \succcurlyeq_c z$$
  > Given choice coherence, $$y \not\in c(\{x,y,z\})$$ since $$x \succcurlyeq_c y \implies x \in c(\{x,y\})$$
  > Given choice coherence, $$z \not\in c(\{x,y,z\})$$ since $$y \succcurlyeq_c z \implies y \in c(\{y,z\})$$
  > Given finite non-emptiness, $$x\in c(\{x,y,z\})$$
  > Given choice coherence, $$x\in c(\{x,y,z\}) \implies z\not\in c(\{x,z\})$$
  > Given finite non-emptiness $$z\not\in c(\{x,z\} \implies x\in c(\{x,z\} \implies x \succcurlyeq_c z$$
  > Q.E.D
[](----------------------------------------)
5. <a id="0.5"></a> If a choice function $$c$$ satisfies [finite non-emptiness](#nonemptiness) and [choice coherence](#WARP), then 
$$c_{\succcurlyeq_{c}}(A) := \{x\in A ~⎮~ \forall y\in A : x \succcurlyeq_{c} y\}$$, where $$A\subseteq X$$, satisfies [finite non-emptiness](#nonemptiness) and [choice coherence](#WARP)
  > **Proof**
  > From [0.4](#0.4), we know that $$\succcurlyeq_{c}$$ is complete and transitive
  > From [0.3](#0.3), we know that if $$\succcurlyeq_{c}$$ is complete and transitive then $$c_{\succcurlyeq_{c}}(A)$$ satisfies finite non-emptiness and choice coherence
  > Q.E.D
[](----------------------------------------)
6. <a id="0.6"></a> If a choice function $$c$$ satisfies [finite non-emptiness](#nonemptiness) and [choice coherence](#WARP), then for every $$A \subseteq X$$ it is the case that $$c(A) = \emptyset \lor c(A) = c_{\succcurlyeq_{c}}(A)$$
  > **Proof**
  > - $$c(A) \subseteq c_{\succcurlyeq_{c}}(A)$$
  > If $$c(A)\neq\emptyset$$ let us take an arbitrary set $$A \subseteq X$$ and arbitrary element $$x\in c(A)$$
  > Given choice coherence $$\forall y \in A\setminus\{x\} : y\not\in c(\{x,y\})$$
  > Given completeness $$\forall y \in A\setminus\{x\} : x\in c(\{x,y\})$$
  > Hence we can say that $$\forall y \in A\setminus\{x\} : x \succcurlyeq_{c} y$$
  > Thus we can say that $$x\in c_{\succcurlyeq_{c}}(A)$$
  > Every element of $$c(A)$$ is in $$c_{\succcurlyeq_{c}}(A)$$ hence $$c(A) \subseteq c_{\succcurlyeq_{c}}(A)$$
  > Q.E.D
  > - $$c_{\succcurlyeq_{c}}(A) \subseteq c(A)$$
  > If $$c(A)\neq \emptyset$$ let us take an arbitrary element $$x\in c_{\succcurlyeq_{c}}(A)$$
  > $$x\in c_{\succcurlyeq_{c}}(A) \implies \forall y\in A: x \succcurlyeq_{c} y$$
  > In that case $$\forall y\in A: x\in c(\{x,y\})$$
  > Given choice coherence [The IIA formulation is more direct to see], $$x\in c(A)$$
  > Every element of $$c_{\succcurlyeq_{c}}(A)$$ is in $$c(A)$$ hence $$c_{\succcurlyeq_{c}}(A) \subseteq c(A)$$
  > Q.E.D

[](----------------------------------------)
Go to [definitions](#definitions)
[](----------------------------------------)


## No-Better-Than Sets
- <a id="LCS"></a> For a preference relation $$\succcurlyeq$$ defined on a set $$X$$ and for $$x\in X$$ the no-better-than $$x$$ set is 
$$NBT(x):=\{y\in X ~⎮~ x\succcurlyeq y\}$$[^4] 
Also known as weak $$\succcurlyeq-$$lower contour set
- <a id="UPS"></a>In the same vein we can define weak $$\succcurlyeq-$$upper contour set[^4] as 
$$NWT(x):=\{y\in X ~⎮~ y\succcurlyeq x\}$$
[](----------------------------------------)
### Results
[](----------------------------------------)
1. <a id="1.1"></a> If $$\succcurlyeq$$ is [complete](#complete) and [transitive](#transitive), then $$\forall x\in X: NBT(x)\neq \emptyset$$
  > **Proof**
  > Given completeness of $$\succcurlyeq$$ we can say that $$x\succcurlyeq x$$
  > Thus it is always the case that $$x\in NBT(x)$$
  > Q.E.D
[](----------------------------------------)
2. <a id="1.2"></a> If $$\succcurlyeq$$ is [complete](#complete) and [transitive](#transitive), then $$\forall x,y\in X : x \succcurlyeq y \iff NBT(y) \subseteq NBT(x)$$
  > **Proof**
  > - $$\implies$$
  > Let us assume that $$x \succcurlyeq y$$
  > $$\forall z\in NBT(y) : y \succcurlyeq z$$
  > Given transitivity of $$\succcurlyeq$$, $$x \succcurlyeq y \land y \succcurlyeq z \implies x \succcurlyeq z$$
  > Thus $$z\in NBT(x)$$
  > Q.E.D
  > - $$\impliedby$$
  > Let us assume that $$NBT(y)\subseteq NBT(x)$$
  >   - Case 1: $$NBT(y)\subset NBT(x)$$ [proper subset]
  > Hence, $$\forall z\in NBT(y) : z\in NBT(x)$$ and $$\exists w\in NBT(x) : w\not\in NBT(y)$$
  > $$z\in NBT(y) \implies y \succcurlyeq z$$
  > $$w\in NBT(x) \implies x \succcurlyeq w$$
  > $$w\not\in NBT(y) \implies y \not\succcurlyeq w$$
  > Given completeness of $$\succcurlyeq$$, it must be the case that $$w \succcurlyeq y$$
  > Given transitivity of $$\succcurlyeq$$, $$x \succcurlyeq w \land w \succcurlyeq y \implies x \succcurlyeq y$$
  > Additionally $$y \not\succcurlyeq x$$ since, given transitivity, $$y \succcurlyeq x \land x \succcurlyeq w \implies y\succcurlyeq w$$ which we have alreadt shown cannot be true
  > Q.E.D
  >   - Case 2: $$NBT(y) = NBT(x)$$ [equal sets]
  > From [1.1](#1.1) we know that $$y\in NBT(y) \land x\in NBT(x)$$
  > Since they are equal sets, $$y\in NBT(y) \implies y\in NBT(x)$$ and $$x\in NBT(x) \implies x\in NBT(y)$$
  > $$x\in NBT(y) \implies y \succcurlyeq x$$
  > $$y\in NBT(x) \implies x\succcurlyeq y$$
  > Q.E.D
[](----------------------------------------)
3. <a id="1.3"></a> If $$\succcurlyeq$$ is [complete](#complete) and [transitive](#transitive), then for any two elements $$x,y\in X$$, it is the case that 
$$NBT(x)\subset NBT(y) ~\lor~ NBT(x)\supset NBT(y) ~\lor~ NBT(x) = NBT(y)$$
  > **Proof**
  > Given completeness of $$\succcurlyeq$$, it must be the case that $$x \succcurlyeq y \lor y \succcurlyeq x$$ 
  > From [1.2](#1.2), we know that $$x \succcurlyeq y \implies NBT(y)\subseteq NBT(x)$$
  > From [1.2](#1.2), we know that $$y \succcurlyeq x \implies NBT(x)\subseteq NBT(y)$$
  > $$NBT(y)\subseteq NBT(x) ~\lor~ NBT(x)\subseteq NBT(y)$$
  > Q.E.D
[](----------------------------------------)
4. <a id="1.4"></a> If $$X$$ is finite and $$\succcurlyeq$$ is [complete](#complete) and [transitive](#transitive), then the function $$u: X\to \mathbb{R}$$ given by $$u(x):=⎮NBT(x)⎮$$ satisfies $$x\succcurlyeq y \iff u(x)\geq u(y)$$
  > **Proof**
  > - $$\implies$$
  > Let us assume that for some $$x,y\in X$$ it is the case that $$x\succcurlyeq y$$
  > From [1.2](#1.2) we know that $$x\succcurlyeq y \iff NBT(y)\subseteq NBT(x)$$
  > Hence $$⎮NBT(x)⎮ \geq ⎮NBT(y)⎮$$ which means that $$u(x) \geq u(y)$$
  > Q.E.D
  > - $$\impliedby$$
  > Let us assume that that for some $$x,y\in X$$ it is the case that $$u(x) \geq u(y)$$
  > $$u(x) = ⎮NBT(x)⎮$$ and $$u(y) = ⎮NBT(y)⎮$$
  > $$⎮NBT(x)⎮ \geq ⎮NBT(y)⎮$$
  > From [1.3](#1.3) we know that it is case that $$NBT(y)\subseteq NBT(x) ~\lor~ NBT(x)\subseteq NBT(y)$$
  > Since $$⎮NBT(x)⎮ \geq ⎮NBT(y)⎮$$ it must be that $$NBT(y)\subseteq NBT(x)$$
  > From [1.2](#1.2) we can say that, since $$NBT(y)\subseteq NBT(x)$$ it must be the case that $$x \succcurlyeq y$$
  > Q.E.D

[](----------------------------------------)
Go to [NBT sets](#no-better-than-sets) 
[](----------------------------------------)

## Strict Preference and Indifference
- <a id="strictpref"></a> **Strict Preference** : $$x \succ y := x\succcurlyeq y \land y\not\succcurlyeq x$$
- <a id="indiff"></a> **Indifference** : $$x \sim y := x \succcurlyeq y \land y \succcurlyeq x$$
[](----------------------------------------)
### Results
[](----------------------------------------)
1. <a id="2.1"></a> If $$\succcurlyeq$$ is [complete](#complete) and [transitive](#transitive), then
    1. $$x \succ y \iff y\not\succcurlyeq x$$
    2. $$\succ$$ is [asymmetric](#R-asym)
    3. $$\succ$$ is [negatively transitive](#R-negtrans)
    4. $$\sim$$ is [reflexive](#R-reflex)
    5. $$\sim$$ is [symmetric](#R-sym)
    6. $$\sim$$ is [transitive](#R-trans)
    7. $$[x \succ y \land y \succcurlyeq z] \implies x \succ z$$ 
    8. $$[x \succcurlyeq y \land y \succ z] \implies x \succ z$$
    9. $$\succ$$ is [transitive](#R-trans)
  > **Accepted without proof** : it's trivial

[](----------------------------------------)
Go to [$$\succ$$ and $$\sim$$](#strict-preference-and-indifference) 
[](----------------------------------------)

## Infinite Sets and Utility Representation
Objective is to prove that:
<div style="background-color:rgba(100, 100, 100, 0.3); text-align:center; vertical-align: middle; padding:15px 50px;">
If $$\succcurlyeq$$ is a complete and transitive binary relation on an arbitrary set $$X$$, then some function $$u: X\to \mathbb{R}$$ exists that represents $$\succcurlyeq$$; i.e $$x\succcurlyeq y \iff u(x) \geq u(y)$$
</div>

[](----------------------------------------)
### Results
1. <a id="3.1"></a> If $$\succcurlyeq$$ is a [complete](#R-comp) and [transitive](#R-trans) binary relation on a [countable](#countable) set $$X$$, then there exists a $$u:X\to\mathbb{R}$$ such that $$x\succcurlyeq y \iff u(x) \geq u(y)$$
  > **Proof**
  > Let $$\{x_1, x_2 ...\}$$ be an enumeration of the set $$X$$
  > Let us define $$d:X\to\mathbb{R}$$ by $$d(x_n) = \left(\frac{1}{2}\right)^n$$
  > Let us define $$u(x) = \sum_{z\in NBT(x)} d(z)$$
  > - $$\implies$$
  > Let us assume that $$x\succcurlyeq y$$
  > From [1.2](#1.2), we can say that $$NBT(y)\subseteq NBT(x)$$
  > $$NBT(y)\subseteq NBT(x) \implies ⎮NBT(y)⎮ \leq ⎮NBT(x)⎮$$
  > Given $$NBT(y)\subseteq NBT(x)$$ and $$⎮NBT(y)⎮ \leq ⎮NBT(x)⎮$$ we can say that $$u(x)\geq u(y)$$ as $$NBT(x)$$ contains all the same elements, and more, as $$NBT(y)$$ does
  > Q.E.D
  > - $$\impliedby$$
  > Let us assume that $$u(x) \geq u(y)$$
  > From [1.3](#1.3), we know that $$NBT(y)\subseteq NBT(x) \lor NBT(x)\subseteq NBT(y)$$
  > $$u(x) > u(y) \implies \sum_{z\in NBT(x)} d(z) \geq \sum_{z\in NBT(y)} d(z)$$ 
  > $$NBT(x)\subseteq NBT(y) \implies ⎮NBT(x)⎮ \leq ⎮NBT(y)⎮$$
  > $$⎮NBT(x)⎮ \leq ⎮NBT(y)⎮ \implies \sum_{z\in NBT(x)} d(z) \leq \sum_{z\in NBT(y)} d(z) \implies u(x) \leq u(y)$$ since all summands are positive
  > This contradicts our initial assumption, thus $$NBT(y)\subseteq NBT(x)$$
  > $$NBT(y)\subseteq NBT(x)\iff x\succcurlyeq y$$
  > Q.E.D
[](----------------------------------------)
2. <a id="3.2"></a> If $$\succcurlyeq$$ is a [complete](#R-comp) and [transitive](#R-trans) preference relation on a set $$X$$, then $$\succcurlyeq$$ can be represented by a utility function if and only if there exists a [countable](#countable) and [order dense](#dense) set $$X^*\subseteq X$$
  > **Proof**
  > We will only prove the case where existence of countable, order dense $$X^* \subseteq X$$ implies utility function representation
  > Let us assume that countable, order dense $$X^* \subseteq X$$ exists
  > We can enumerate $$X^*$$ as $$\{x^*_1, x^*_2 ...\}$$
  > Let us define $$d(x_n) = \left(\frac{1}{2}\right)^n$$ [can only be defined if there is an $$n$$]
  > Let us define $$u(x) = \sum_{z\in NBT(x)\cap X^*} d(z)$$
  >> - $$\implies$$
  >> Let us assume that $$x\succcurlyeq y$$
  >> From [1.2](#1.2), we can say that $$x \succcurlyeq y \iff NBT(y)\subseteq NBT(x)$$
  >> $$NBT(y)\subseteq NBT(x) \implies NBT(y)\cap X^*\subseteq NBT(x)\cap X^*$$
  >> $$NBT(y)\cap X^*\subseteq NBT(x)\cap X^* \implies ⎮NBT(y)\cap X^*⎮ \leq ⎮NBT(x)\cap X^*⎮$$
  >> Hence we can say that since all summands are positive $$u(x)\geq u(y)$$
  >> Q.E.D
  >> - $$\impliedby$$
  >> Let us assume that $$u(x)\geq u(y)$$
  >> $$\sum_{z\in NBT(x)\cap X^*} d(z) \geq \sum_{z\in NBT(y)\cap X^*} d(z)$$
  >> From [1.3](#1.3), we can say that $$NBT(y)\subseteq NBT(x) \lor NBT(x)\subseteq NBT(y)$$
  >> $$NBT(x)\subseteq NBT(y) \implies NBT(x)\cap X^*\subseteq NBT(y)\cap X^*$$
  >> $$NBT(x)\cap X^*\subseteq NBT(y)\cap X^* \implies ⎮NBT(x)\cap X^*⎮ \leq ⎮NBT(y)\cap X^*⎮$$
  >> Since all summands are positive and $$NBT(x)\cap X^*\subseteq NBT(y)\cap X^*$$, it must be that $$\sum_{z\in NBT(x)\cap X^*} d(z) \leq \sum_{z\in NBT(y)\cap X^*} d(z)$$
  >> This gives us a contradiction, thus $$NBT(x)\subseteq NBT(y)$$ must be false
  >> Hence $$NBT(y)\subseteq NBT(s)$$
  >> From [1.2](#1.2), since $$NBT(y)\subseteq NBT(s)$$ it must be the case that $$x\succcurlyeq y$$
  >> Q.E.D
[](----------------------------------------)

### Continuity
- <a id="continous"></a> **Continuity** : [Complete](#R-comp) and [transitive](#R-trans) $$\succcurlyeq$$ on $$X = \mathbb{R}^k_+$$ is continuous if 
$$\forall x,y\in X : x\succ y \implies \exists \epsilon>0 : \forall x', y'\in X : d(x,x')<\epsilon \land d(y',y)<\epsilon \implies x' \succ y'$$
[](----------------------------------------)
### More Results
3. <a id="3.3"></a> If $$X=\mathbb{R}^k_+$$ and $$\succcurlyeq$$ is [complete](#R-comp), [transitive](#R-trans) and [continuous](#continuous) on $$X$$, then $$x \succcurlyeq y \iff u(x) \geq u(y)$$ 
  > **Proof**
  > Suppose $$x\succ y$$ and consider all elements $$\forall a \in [0,1] : ax + (1-a)y$$ [these elemets make a line segment between $$x$$ and $$y$$] 
  > Given continuity of $$\succcurlyeq$$, $$\exists \epsilon>0 : \forall y'\in X : d(y',y)<\epsilon \implies x \succ y'$$
  > Some of these $$y'$$ will be on the line joining $$x,y$$
  > Consider the upper contour set of x $$NWT(x) := \{a\in[0,1] : ax + (1-a)y \succcurlyeq x\}$$
  > $$a_1 := \inf(NWT(x))$$
  > Given $$x\succ y$$, we can say that $$a_1 > 0$$
  > $$x_1 := a_1 x + (1-a_1)y$$, note that this $$x_1$$ is also a point on the line $$xy$$
  > Given completeness of $$\succcurlyeq$$, it must be the case that $$x \succ x_1 \lor x\sim x_1 \lor x_1\succ x$$
  > Given continuity of $$\succcurlyeq$$, $$x_1\succ x \implies \exists \epsilon>0 : \forall x_1'\in X : d(x_1,x_1')<\epsilon \implies x_1' \succ x$$
  > Some of these $$x_1'$$ will be on $$xy$$, i.e $$\exists a' < a_1: a'x+(1-a')y\succ x$$
  > $$a'\in \inf(NWT(x))$$ and $$a'<a_1$$, hence $$a_1$$ cannot be the infimum since $$a_1$$ is not a lower bound to $$NWT(x)$$
  >  Given continuity of $$\succcurlyeq$$, $$x \succ x_1 \implies \exists \epsilon>0 : \forall x_1'\in X : d(x_1,x_1')<\epsilon \implies x \succ x_1'$$
  > Some of these $$x_1'$$ will be on $$xy$$, i.e $$\exists a' > a_1: x \succ a'x+(1-a')y$$
  > This $$a'$$ would then become a greater lower bound than $$a_1$$ to $$NWT(x)$$, hence $$a_1$$ can't be its infimum
  > Thus $$x_1 \sim x$$
  > Since $$x_1 \sim x$$, we can say that $$x_1\succ y$$
  > Given continuity of $$\succcurlyeq$$, $$x_1\succ y \implies \exists \epsilon>0 : \forall x_1'\in X : d(x_1,x_1')<\epsilon \implies x_1' \succ y$$
  > Some of these $$x_1'$$ will be on $$xy$$, i.e $$\exists a' < a_1: a'x+(1-a')y\succ y$$
  > However, since $$a_1 = \inf(NWT(x))$$ it must be that $$x\succ a'x+(1-a')y$$
  > Thus we can say that $$\exists a_2 < a_1$$ such that $$x_2 := a_2x+(1-a_2)y$$ $$x\succ x_2 \succ y$$
  > Given continuity, each $$x_2'$$ in a ball of radius $$\epsilon'$$ around $$x_2$$ that gives us $$x\succ x_2'$$
  > Given continuity, each $$x_2''$$ in a ball of radius $$\epsilon''$$ around $$x_2$$ that gives us $$x_2'\succ y$$
  > Taking $$\mu = \min(\epsilon', \epsilon'')$$, we have an element $$z$$ in a ball of radius $$\epsilon$$ around $$x_2$$ that gives us $$x\succ z \succ y$$
  > Given we are in $$\mathbb{R}^k_+$$, $$\exists x^* : d(x^*,x_2)<\mu \implies x\succ x^*\succ y$$ and $$\forall k : x^*_k\in\mathbb{Q}$$
  > Let us take $$X^* := \{x\in X ~⎮~ \forall k : x_k\in\mathbb{Q}\}$$
  > $$X^*$$ is a countable, order-dense subset of $$X$$
  > From [3.2](#3.2), we can say that $$x \succcurlyeq y \iff u(x) \geq u(y)$$
  > Q.E.D


[](----------------------------------------)
## Other definitions[^1]
- <a id="R-reflex"></a> **Reflexivity** : $$\forall x\in S : x R x$$
- <a id="R-comp"></a> **Completeness** : $$\forall x,y\in S : xRy \lor yRx$$[^2] 
- <a id="R-trans"></a> **Transitivity** : $$\forall x,y,z\in S : [xRy \land yRz] \implies xRz$$[^2] 
- <a id="R-antisym"></a> **Anti-Symmetry** : $$\forall x,y\in S : [xRy \land yRx] \implies x=y$$
- <a id="R-asym"></a> **Asymmetry** : $$\forall x,y\in S : xRy \implies \neg yRx$$
- <a id="R-sym"></a> **Symmetry** : $$\forall x,y\in S : xRy \implies yRx$$
- <a id="R-negtrans"></a> **Negatively Transitive** : $$\forall x,y,z\in S : xRz \implies [xRy \lor yRz]$$ or its contrapositive $$\forall x,y,z\in S : [\neg xRy \land \neg yRz] \implies \neg xRz$$
- <a id="countable"></a> **Countable** : A set $$S$$ is countable if $$⎮S⎮ \leq \aleph_0$$ <div style="background-color:rgba(255, 255, 255, 0); text-align:center; vertical-align: middle;"><b>alternatively</b></div> A set $$S$$ is countable if there a bijective mapping between $$S$$ and $$\mathbb{N}$$
- <a id="dense"></a> **Order-Dense** : $$\forall x,y \in X : x \succ y \exists : s \in S : x \succ s \succ y$$, then we say that S is $$\succcurlyeq$$-dense (or, order-dense) in X[^3] 
- <a id="preorder"></a> **Pre-Order** : A binary relation $$R$$ which satisfies [reflexivity](#R-reflex) and [transitivity](#R-trans)[^5]
- <a id="weakorder"></a> **Weak-Order** : A binary relation $$R$$ which satisfies [completeness](#R-comp) and [transitivity](#R-trans)[^5]
- <a id="linorder"></a> **Linear-Order** : A binary relation $$R$$ which satisfies [completeness](#R-comp), [transitivity](#R-trans) and [anti-symmetric](#R-antisym)[^5]

[^0]: Largely from <u>Microeconomic Foundations 1, Kreps, 2013</u>
[^1]: <u>Collective Choice and Social Welfare, Sen, 2017</u>
[^2]: Same as the definition given earlier in [definitions](#definitions)
[^3]: <u>"Real Analysis with Economic Applications", Efe Ok, 2007</u>
[^4]: Terminology borrowed from <u>"Real Analysis with Economic Applications", Efe Ok, 2007</u>
[^5]: From David Ahn's [notes](https://eml.berkeley.edu/~dahn/201notes.pdf) on binary relations






