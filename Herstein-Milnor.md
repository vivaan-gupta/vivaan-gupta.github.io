---
title: Herstein - Milnor
created: '2022-07-03T07:42:28.017Z'
modified: '2022-07-12T17:41:50.899Z'
---

# Herstein - Milnor

## Definitions
- <a id="MS"></a> **Mixture Set** : A set $$S$$ is said to be a mixture set if for any $$a,b\in S$$ and any $$\mu$$, $$\mu a + (1-\mu)b \in S$$ where:
    - $$1\cdot a + (1-1)\cdot b = a$$
    - $$\mu a + (1-\mu) b = (1-\mu) b + \mu a$$
    - $$\lambda [\mu a + (1-\mu)b] + (1-\lambda) b = \lambda\mu a + (1-\lambda\mu)b$$
- <a id="OP"></a> **Order-preserving** : A real valued function $$u$$ is order preserving if $$\forall a,b \in S : u(a)>u(b) \iff a\succ b$$
- <a id="MP"></a> **Linear** : A real valued function $$u$$ defined on a mixture set $$\mathfrak{M}$$ is linear if $$\forall a,b \in \mathfrak{M} : \forall \alpha : u[\alpha a + (1-\alpha)b] = \alpha u(a) + (1-\alpha)u(b)$$ 

[](--- lower contour --> everything worse than me ; upper contour --> everything better than me)
## Axioms
1. <a id="weak-order"></a> **Weak Order** :  $$\succcurlyeq$$ on $$S$$ is complete and transitive
2. <a id="continuity"></a> **Archimedean Continuity** : $$\forall a,b,c\in S : \{\alpha ~|~ \alpha a + (1-\alpha)b \succcurlyeq c\}$$ and $$\{\alpha ~|~ c \succcurlyeq \alpha a + (1-\alpha)b \}$$, i.e $$\succcurlyeq$$-upper contour and lower contour, are [closed](#closed-set)
3. <a id="independence"></a> **Independence** : $$a,a'\in S : a\sim a' \implies \forall b\in S : \frac{1}{2}a + \frac{1}{2}b \sim \frac{1}{2}a' + \frac{1}{2}b$$

## Results
1. <a id="1.1"></a> $$\forall a,b,c\in S : a \succcurlyeq b \succcurlyeq c \implies \exists \omega : b\sim \omega a + (1-\omega)c$$
  > **Proof**
  > Let $$T := \{\mu ~|~ \mu a + (1-\mu)c \succcurlyeq b\}$$ [$$\succcurlyeq$$-upper contour set of $$b$$]
  > By [Axiom 2](#continuity), $$T$$ is a closed set and since $$\mu\in [0,1]$$, the upper contour set will be a closed subset of $$[0,1]$$
  > $$a\succcurlyeq b \implies 1\in T \implies T\neq \emptyset$$
  > Let $$W := \{\nu ~|~ b \succcurlyeq \nu a + (1-\nu)c\}$$  [$$\succcurlyeq$$-lower contour set of $$b$$]
  > By [Axiom 2](#continuity), $$W$$ is a closed set and since $$\nu\in[0,1]$$, the lower contour set will be a closed subset of $$[0,1]$$
  > $$b\succcurlyeq c \implies 0\in W \implies W\neq \emptyset$$
  > By [Axiom 1](#weak-order), $$\succcurlyeq$$ on $$S$$ is complete and transitive, thus $$T \cup W = [0,1]$$
  > From [A.1](#A.1), we know that $$[0,1]$$ is a connected set
  > From [A.2](#A.2), we know that $$T\cap W \neq \emptyset$$ 
  > Thus $$\exists \omega\in T\cap W : \omega a + (1-\omega)c \succcurlyeq b \land b \succcurlyeq \omega a + (1-\omega)c$$
  > $$\exists \omega\in T\cap W : b \sim \omega a + (1-\omega)c$$
  > Q.E.D
[](-----------------------------)
2. <a id="1.2"></a> If $$\mu_i a +(1-\mu_i)b \sim c$$ and $$\mu = \underset{i\to\infty}{lt} \mu_i$$, then $$\mu a+(1-\mu b)\sim c$$
  > Let us take a sequence $$\{\mu_i\}$$ such that $$\forall i : \mu_i a +(1-\mu_i)b \sim c$$
  > $$\mu_i a +(1-\mu_i)b \sim c \implies [ \mu_i a +(1-\mu_i)b \succcurlyeq c ] \land [ c \succcurlyeq \mu_i a +(1-\mu_i)b ]$$
  > Given [Axiom 2](#continuity), $$\succcurlyeq$$-upper contour and $$\succcurlyeq$$-lower contour sets are closed
  > From [A.4](#A.4) and [A.5](#A.5), we can say that this set will also contain its limit point
  > This allows us to say that $$\mu \in \succcurlyeq$$-upper contour and $$\mu \in \succcurlyeq$$-lower contour
  > $$\mu a +(1-\mu)b \succcurlyeq c$$ and $$c \succcurlyeq \mu a +(1-\mu)b$$
  > Hence we can say that $$\mu a +(1-\mu)b \sim c$$
  > Q.E.D

 Note : The set containing all mixtures indifferent to $$c$$ also contain its limit point. And in light of [A.7](#A.7), it will also be closed.
[](-----------------------------)
3. <a id="1.3"></a> $$\forall a,b\in S : a\succ b \implies a\succ \frac{1}{2}a + \frac{1}{2}b \succ b$$
  > **Proof**
  > Let us assume that $$\frac{1}{2}a + \frac{1}{2}b\succcurlyeq a \succ b$$
  > From [1.1](#1.1), we can say that $$\exists \mu : a\sim \mu(\frac{1}{2}a + \frac{1}{2}b) + (1-\mu)b = \frac{\mu}{2} a + (1-\frac{\mu}{2})b$$
  > $$T := \{\mu ~|~ a\sim \frac{\mu}{2} a + (1-\frac{\mu}{2})b\}$$
  > From [1.2](#1.2), we can say that this set will also contain its limit point
  > From [A.7](#A.7), we can say that this set is closed
  > $$T \subseteq [0,1]$$
  > Thus we can say that $$T$$ has a least element $$\mu_0$$
  > $$a\sim \frac{\mu_0}{2} a + (1-\frac{\mu_0}{2})b$$
  > Given [Axiom 3](#independence), $$a\sim \frac{\mu_0}{2} a + (1-\frac{\mu_0}{2})b \implies \frac{1}{2}a + \frac{1}{2}b \sim \frac{1}{2}(\frac{\mu_0}{2} a + (1-\frac{\mu_0}{2})b) + \frac{1}{2}b = \frac{\mu_0}{4} a + (1-\frac{\mu_0}{4})b \succcurlyeq a \succ b$$
  > From [1.1](#1.1), we can say that $$\exists \lambda : a \sim \lambda[\frac{\mu_0}{4} a + (1-\frac{\mu_0}{4})b] (1-\lambda)b = \frac{\lambda\mu_0}{4} a + (1-\frac{\lambda\mu_0}{4})b$$
  > However, $$\frac{\mu_0}{2} > \frac{\lambda\mu_0}{4}$$ which contradicts the choice of $$\mu_0$$ as the least element in the set $$\exists x\in T : x=\frac{\lambda\mu_0}{2}$$
  > Similarly, we can show the same for $$a \succ b \succcurlyeq \frac{1}{2}a + \frac{1}{2}b$$
  > Thus $$a\succ \frac{1}{2}a + \frac{1}{2}b \succ b$$
  > Q.E.D
[](-----------------------------)
4.  <a id="1.4"></a> $$\forall a,b\in S : a \succ b \implies \forall \mu\in(0,1) : a \succ \mu a + (1-\mu)b \succ b$$
  > **Proof**
  > Let us define $$\rho = \sum_1^{n(\rho)} \frac{1}{2^i}$$ [$$\rho\in\mathbb{Q}$$]
  > By successively applying [1.3](#1.3), we can say that $$\forall \rho_1, \rho_2\in\mathbb{Q} : \rho_2>\rho_1 \implies a \succ \rho_2 a + (1-\rho_2)b \succ \rho_1 a + (1-\rho_1)b \succ b$$
  > $$\forall \rho_1, \rho_2\in\mathbb{Q} : \exists \mu : 1 > \rho_2 > \mu > \rho_1 > 0$$
  > $$a':= \rho_2 a + (1-\rho_2)b$$ and $$b':= \rho_1 a + (1-\rho_1)b$$
  > $$\forall \rho' \in\mathbb{Q} : \rho_2 > \rho' > \rho_1 \implies a' \succ rho' a + (1-\rho')b \succ b'$$
  > Let $$\mu = lt \rho'$$, i.e $$\mu$$ is a limit of a sequence of rationals
  > From [Axiom 2](#continuity), since $$\succcurlyeq$$-upper contour and $$\succcurlyeq$$-lower contour sets are closed, given [A.7](#A.7), this $$\mu$$ will be also be in $$\succcurlyeq$$-upper contour and $$\succcurlyeq$$-lower contour sets of $$a$$ and $$b$$ respectively
  > Thus we can say that $$a \succ \mu a + (1-\mu)b \succ b$$
  > Q.E.D
[](-----------------------------)
5. <a id="1.5"></a> $$\forall a,a'\in S : a\sim a' \implies \mu a + (1-\mu)a' \sim a$$
  > **Proof**
  > Let us define $$\rho = \sum_1^{n(\rho)} \frac{1}{2^i}$$ [$$\rho\in\mathbb{Q}$$]
  > Given [Axiom 3](#independence), we can say that $$a\sim a' \implies a \sim \frac{1}{2}a + \frac{1}{2}a'$$
  > By successively applying the same, we can say that $$\forall \rho'\in\mathbb{Q} : a \sim \rho' a + (1-\rho') a'$$
  > Let $$\mu = lt \rho'$$, i.e $$\mu$$ is a limit of a sequence of rationals
  > From [1.2](#1.2), we know that the indifference set is closed, given [A.7](#A.7), this $$\mu$$ will also be in the indifference set
  > Hence $$\mu a + (1-\mu)a' \sim a$$
  > Q.E.D
[](-----------------------------)
6. <a id="1.6"></a> $$\forall a,a'\in S : a\sim a' \implies \forall b \in S, \mu\in[0,1] : \mu a + (1-\mu)b \sim \mu a' + (1-\mu)b$$
  > **Proof**
  > Let us assume that $$a\sim a'$$
  > - $$a\sim a' \sim b$$
  > From [1.5](#1.5) we can say that, $$a\sim b \implies a \sim \mu a + (1-\mu) b \sim a' \sim \mu a' + (1-\mu) b$$
  > Q.E.D
  > - $$a\sim a' \succ b$$
  > Given [Axiom 3](#independence), we can say that $$a\sim a' \implies \frac{1}{2}a + \frac{1}{2}b \sim \frac{1}{2}a' + \frac{1}{2}b$$
  > By successively applying the same, we can say that $$\forall \rho\in\mathbb{Q} : \rho a + (1-\rho)b \sim \rho a' + (1-\rho)b$$
  > For any given $$\mu$$ take its $$\succcurlyeq$$-upper contour sets $$T:=\{\lambda ~|~ \lambda a + (1-\lambda)b \succcurlyeq \mu a' + (1-\mu)b\}$$ (and $$W:=\{\lambda ~|~ \lambda a' + (1-\lambda)b \succcurlyeq \mu a' + (1-\mu)b\}$$)
  > Pick a sequence $$\{\rho_i\}$$ approaching $$\mu$$ from the positive side, i.e $$\mu = lt \rho_i$$
  > From [1.4](#1.4), we can say that $$\rho_i a + (1-\rho_i)b \sim \rho_i a' + (1-\rho_i)b \succcurlyeq \mu a' + (1-\mu)b$$ (and $$\rho_i a + (1-\rho_i)b \sim \rho_i a' + (1-\rho_i)b \succcurlyeq \mu a + (1-\mu)b$$)
  > Thus $$\rho_i$$ must also be in $$T$$ (and $$W$$)
  > Given [Axiom 2](#continuity), we can say that $$\mu \in T$$, hence $$\mu a + (1-\mu)b \succcurlyeq \mu a' + (1-\mu)b$$ (and $$\mu a' + (1-\mu)b \succcurlyeq \mu a + (1-\mu)b$$)
  > Thus we can say that $$\mu a + (1-\mu)b \sim \mu a' + (1-\mu)b$$
  > Q.E.D
  > - $$b \succ a\sim a'$$
  > Similar argument as the last case, just go for $$\succcurlyeq$$-lower contour sets instead
  > Q.E.D
[](-----------------------------)
7. <a id="1.7"></a> $$\forall a,b \in S : a \succ b \implies \forall \lambda,\mu\in(0,1) : \lambda > \mu \iff \lambda a + (1-\lambda)b \succ \mu a + (1-\mu)b$$
  > **Proof**
  > Let us assume that $$a\succ b$$
  > - $$\implies$$
  > Let us assume that $$1 > \lambda > \mu > 0$$
  > From [1.4](#1.4), we can say that $$a\succ b \implies a\succ \lambda a + (1-\lambda)b \succ b$$
  > $$1 > \frac{\mu}{\lambda} > 0$$
  > From [1.4](#1.4), we can say that $$\lambda a + (1-\lambda)b \succ b \implies \lambda a + (1-\lambda)b \succ \frac{\mu}{\lambda}[\lambda a + (1-\lambda)b] + (1-\frac{\mu}{\lambda})b \succ b$$
  > $$\frac{\mu}{\lambda}[\lambda a + (1-\lambda)b] + (1-\frac{\mu}{\lambda})b = \mu a + (1-\mu)b$$
  > Thus we can say that $$\lambda a + (1-\lambda)b \succ \mu a + (1-\mu)b$$
  > Q.E.D
  > - $$\impliedby$$
  > Let us assume that $$\lambda a + (1-\lambda)b \succ \mu a + (1-\mu)b$$
  > $$\mu a + (1-\mu)b = \frac{\mu}{\lambda}[\lambda a + (1-\lambda)b] + (1-\frac{\mu}{\lambda})b$$
  > From [1.4](#1.4), we can say that $$a\succ b \implies a\succ \lambda a + (1-\lambda)b \succ b$$
  > From [1.4](#1.4), we can say that $$\lambda a + (1-\lambda)b \succ b \implies \lambda a + (1-\lambda)b \succ \frac{\mu}{\lambda}[\lambda a + (1-\lambda)b] + (1-\frac{\mu}{\lambda})b \succ b$$
  > Thus $$\frac{\mu}{\lambda} < 1 \implies \mu < \lambda$$
  > Q.E.D
[](-----------------------------)
8. <a id="1.8"></a> $$\mu$$ in [1.1](#1.1) is unique
  > **Proof**
  > We already know from [1.1](#1.1) that $$\forall a,b,c\in S : a\succcurlyeq b \succcurlyeq c \implies \exists \mu : b\sim \mu a + (1-\mu)c$$
  > Let $$\mu_1, \mu_2$$ be such that $$b \sim \mu_1 a + (1-\mu_1)c$$ and $$b \sim \mu_2 a + (1-\mu_2)c$$
  > $$b \sim \mu_1 a + (1-\mu_1)c \land b \sim \mu_2 a + (1-\mu_2)c \implies \mu_1 a + (1-\mu_1)c \sim \mu_2 a + (1-\mu_2)c$$
  > - Case 1 : $$\mu_1 > \mu_2$$
  > From [1.7](#1.7), we can say that $$\mu_1 > \mu_2 \iff \mu_1 a + (1-\mu_1)c \succ \mu_2 a + (1-\mu_2)c$$
  > This gives us a contradiction
  > - Case 2 : $$\mu_2 > \mu_1$$
  > From [1.7](#1.7), we can say that $$\mu_2 > \mu_1 \iff \mu_2 a + (1-\mu_2)c \succ \mu_1 a + (1-\mu_1)c$$
  > This gives us a contradiction
  >
  > Hence $$\mu_1 = \mu_2$$
  > Q.E.D

[](-----------------------------)
We have obtained the [linear](#MP) and [order preserving](#OP) structure we had set out to construct.
Assuming $$a\succ b$$, let us take $$S_{ab} := \{a \succcurlyeq x \succcurlyeq b\}$$
Let us also define $$\mu_{ab}(x)$$ as $$x \sim \mu_{ab}(x) a + (1-\mu_{ab}(x)) b$$
Note that under [1.7](#1.7) $$~x\succ y \iff \mu_{ab}(x) > \mu_{ab}(y)$$, which gives us a [order preserving](#OP) structure in $$\mu_{ab}(.)$$
Additionally,
$$\mu' = \mu_{ab}(\alpha x + (1-\alpha)y)$$ would be the value we would mix $$a$$ and $$b$$ with such that $$\alpha x + (1-\alpha)y \sim \mu' a + (1-\mu')b$$
$$\to \alpha [\mu_{ab}(x) a + (1-\mu_{ab}(x))b] + (1-\alpha) [\mu_{ab}(y) a + (1-\mu_{ab}(y))b] \sim \mu' a + (1-\mu')b$$
$$\to \alpha a \mu_{ab}(x)  + \alpha b-\alpha b\mu_{ab}(x) + \mu_{ab}(y) a + b - b\mu_{ab}(y) - \alpha a\mu_{ab}(y) - \alpha b + \alpha b\mu_{ab}(y) \sim \mu' a + (1-\mu')b$$
$$\to \alpha \mu_{ab}(x)[a-b] + \mu_{ab}(y)[a-b] - \alpha \mu_{ab}(y)[a-b] + b \sim \mu' a + (1-\mu')b$$
$$\to [a-b] (\alpha \mu_{ab}(x) + (1-\alpha)\mu_{ab}(y)) + b \sim \mu' a + (1-\mu')b$$
$$\to (\alpha \mu_{ab}(x) + (1-\alpha)\mu_{ab}(y)) a + (1-(\alpha \mu_{ab}(x) + (1-\alpha)\mu_{ab}(y)))b \sim \mu' a + (1-\mu')b$$
Hence it must be the case that $$\mu' = \alpha \mu_{ab}(x) + (1-\alpha)\mu_{ab}(y)$$, giving us a [linear](#MP) structure in $$\mu_{ab}(.)$$ 

However, this only works for $$S_{ab}$$ and not the entire [mixture set](#MS) $$S$$. In order to make it work for the entire $$S$$ let us take two mixtures $$r_0, r_1 \in S_{ab}$$ such that $$r_1 \succ r_0$$. Now take $$a,b$$ such that $$r_0, r_1\in S_{ab}$$ and define for \\[x\in S_{ab}$$ $$$$M_{ab}(x) = \frac{\mu_{ab}(x) - \mu_{ab}(r_0)}{\mu_{ab}(r_1) - \mu_{ab}(r_0)}\\] 
Which will give us an [order preserving](#OP), [linear](#MP) structure with $$M_{ab}(r_0) = 0$$ and $$M_{ab}(r_1) = 1$$. Essentially we have just fixed two points and normalized the scale.
[](-----------------------------)
9. <a id="1.9"></a> Let $$f, g$$ be [order preserving](#OP), [linear](#MP) functions defined on $$S_{ab}$$, such that $$f(r_0) = g(r_0)$$ and $$f(r_1) = g(r_1)$$. Then it must be the case that $$f=g$$ on $$S_{ab}$$
  > **Proof**
  > Let us take an arbitrary $$x\in S_{ab}$$
  > - $$r_1 \succcurlyeq x \succcurlyeq r_0$$
  > From [1.1](#1.1) we know can say that $$x\sim \alpha r_1 + (1-\alpha)r_0$$
  > Since $$f$$ is order preserving, $$f(x) = f(\alpha r_1 + (1-\alpha)r_0)$$
  > Since $$f$$ is linear, $$f(\alpha r_1 + (1-\alpha)r_0) = \alpha f(r_1) + (1-\alpha)f(r_0) = \alpha g(r_1) + (1-\alpha)g(r_0)$$
  > Since $$g$$ is linear $$\alpha g(r_1) + (1-\alpha)g(r_0) = g(\alpha r_1 + (1-\alpha)r_0)$$
  > Since $$g$$ is order preserving $$g(\alpha r_1 + (1-\alpha)r_0) = g(x)$$
  > Thus $$f(x) = g(x)$$
  > - $$x \succcurlyeq r_1 \succ r_0$$
  > From [1.1](#1.1) we know can say that $$r_1\sim \alpha x + (1-\alpha)r_0$$, where $$\alpha>0$$
  > Since $$f$$ is linear and order preserving $$f(r_1) = f(\alpha x + (1-\alpha)r_0) = \alpha f(x) + (1-\alpha)f(r_0)$$
  > Since $$g$$ is linear and order preserving $$g(r_1) = g(\alpha x + (1-\alpha)r_0) = \alpha g(x) + (1-\alpha)g(r_0)$$
  > $$\alpha f(x) + (1-\alpha)f(r_0) = \alpha g(x) + (1-\alpha)g(r_0) \implies f(x) = g(x)$$
  > - $$r_1 \succ r_0 \succcurlyeq x$$
  > From [1.1](#1.1) we know can say that $$r_0\sim \alpha r_1 + (1-\alpha)x$$, where $$\alpha<1$$
  > Since $$f$$ is linear and order preserving $$f(r_0) = f(\alpha r_1 + (1-\alpha)x) = \alpha f(r_1) + (1-\alpha)f(x)$$
  > Since $$g$$ is linear and order preserving $$g(r_0) = f(\alpha r_1 + (1-\alpha)x) = \alpha g(r_1) + (1-\alpha)g(x)$$
  > $$\alpha f(r_1) + (1-\alpha)f(x) = \alpha g(r_1) + (1-\alpha)g(x) \implies f(x) = g(x)$$
  >
  > Q.E.D
[](-----------------------------)

[](-----------------------------)
## Appendix
[](-----------------------------)
### Other Definitions (Point-set Topology) [^0]
- <a id="ball"></a> **Ball** : Let $$(X, d)$$ be a metric space, let us take $$x_0\in X$$ and $$r>0$$ then we can define $$B_{(X,d)}(x_0, r) := \{x\in X ~|~ d(x, x_0) < r\}$$

- <a id="bounded-set"></a> **Bounded Set** : Let $$(X, d)$$ be a metric space and let $$E\subseteq X$$, then $$Y$$ is bounded if and only if there is a [ball](#ball) that contains the set, i.e $$\exists B(x,r)\subseteq X : Y\subseteq B(x,r)$$

- <a id="interior-pt"></a> **Interior Point** : Let $$(X, d)$$ be a metric space and let $$E\subseteq X$$, then $$x_0\in X$$ is an interior point of $$E$$ if $$\exists r>0$$ such that the [ball](#ball), $$B(x_0, r) \subseteq E$$

- <a id="exterior-pt"></a> **Exterior Point** : Let $$(X, d)$$ be a metric space and let $$E\subseteq X$$, then $$x_0\in X$$ is an exterior point of $$E$$ if $$\exists r>0$$ such that the [ball](#ball), $$B(x_0, r) \cap E = \emptyset$$

- <a id="boundary-pt"></a> **Boundary Point** : Let $$(X, d)$$ be a metric space and let $$E\subseteq X$$, then $$x_0\in X$$ is an boundary point of $$E$$ if it is neither an [interior point](#interior-pt) nor an [exterior point](#exterior-pt); the set of boundary points is denoted $$\partial E$$

- <a id="open-set"></a> **Open Set** : Let $$(X, d)$$ be a metric space and let $$E\subseteq X$$, then $$E$$ is an open set if $$E \cap \partial E = \emptyset$$

- <a id="closed-set"></a> **Closed Set** : Let $$(X, d)$$ be a metric space and let $$E\subseteq X$$, then $$E$$ is a closed set if $$\partial E \subseteq E$$

- <a id="adherent"></a> **Adherent Point** : Let $$(X, d)$$ be a metric space, let $$E\subseteq X$$ and let $$x_0\in X$$, then we can say that $$x_0$$ is an adherent point of $$E$$ if $$\forall r>0 : B(x_0, r)\cap E \neq \emptyset$$

- <a id="limit-pt"></a> **Limit Point** : Let $$(X, d)$$ be a metric space, let $$E\subseteq X$$ and let $$x_0\in X$$, then we can say that $$x_0$$ is an limit point of $$E$$ if $$\forall r>0 : B(x_0, r)\setminus\{x_0\} \cap E \neq \emptyset$$[^1]

- <a id="closure"></a>  **Closure Set** : The set of all [adherent points](#adherent) of $$E\subseteq X$$ is called the closure set of $$E$$, denoted by $$\overline{E}$$

- <a id="compact-set"></a> **Compact Set** [Heine-Borel Theorem, not the actual definition] : Let $$(\mathbb{R}^n, d)$$ be a Euclidean space with Euclidean metric or Taxi-cab metric or Sup-norm metric. Let $$E\subseteq\mathbb{R}^n$$, then $$E$$ is compact if and only if it is [closed](#closed-set) and [bounded](#bounded-set) in $$\mathbb{R}^n$$

- <a id="disconnected-space"></a> **Disconnected Space** : Let $$(X, d)$$ be a metric space, then $$X$$ is a disconnected if and only if $$\exists A,B \subseteq X : A\neq \emptyset \land B\neq\emptyset \land A\cap B=\emptyset \land A\cup B = X$$ where both $$A, B$$ are [open sets](#open-set)

- <a id="connected-space"></a> **Connected Space** : Let $$(X, d)$$ be a metric space, then $$X$$ is a connected if and only if $$X\neq\emptyset$$ and $$X$$ is not [disconnected](#disconnected-space)

- <a id="connected-set"></a> **Connected Set** : Let $$(X, d)$$ be a metric space, then $$Y\subseteq X$$ is a connected set if and only if the metric space $$(Y, d|_{Y\times Y})$$ is [connected](#connected-space)

[](-----------------------------)
### Other Results
1. <a id="A.1"></a> $$\forall a,b\in\mathbb{R} : a<b \implies [a,b]$$ is [connected](#connected-set)
 > **Proof**
 > Let us take arbitrary elements $$a,b\in \mathbb{R}$$ such that $$a<b$$
 > Let us assume that $$[a,b]$$ is disconnected
 > Thus, $$\exists V, W \subseteq [a,b]$$ such that $$V, W$$ are non-empty, disjoint, open such that $$V\cup W = [a,b]$$
 > Let $$b\in W$$, then given $$a<b$$ we can say that $$V$$ is bounded above at $$b$$
 > $$V$$ is bounded above by $$b$$, thus $$\exists z \in [a,b]: z = \sup(V)$$
 > $$z\in V \lor z\in W$$
 > - $$z\in V$$
 > Since $$V$$ is an open all points in the set are interior points, i.e $$\forall x\in V : \exists r>0 : B(x,r)\subseteq V$$
 > Thus $$z\neq \sup(V)$$ as there exists a point $$z+r'\in V$$
 > - $$z\in W$$
 > Since $$W$$ is an open all points in the set are interior points, i.e $$\forall x\in W : \exists r>0 : B(x,r)\subseteq W$$
 > Thus $$z\neq \sup(V)$$ as there exists a point $$z-r'\in W$$ and $$z-r\not\in V$$
 > Hence $$[a,b]$$ must be connected
 >
 > Q.E.D
[](-----------------------------)
2. <a id="A.2"></a> For $$P,Q\subseteq [a,b] : P,Q$$ nonempty $$\land ~P\cup Q=[a,b] \land P~$$ [closed](#closed-set) $$~\land ~Q~$$ [closed](#closed-set) $$\implies P\cap Q\neq\emptyset$$
 > **Proof**
 > Let us assume that $$P\cap Q = \emptyset$$ and $$P\cup Q = [a,b]$$
 > We can then infer that $$Q = P^c$$ and $$P = Q^c$$
 > In that case, $$P$$ closed $$\implies Q$$ open
 > In that case, $$Q$$ closed $$\implies P$$ open
 > $$P\cup Q [a,b]$$
 > $$P\neq \emptyset \land Q\neq\emptyset \land P\cap Q=\emptyset \land P\cup Q = [a,b]$$ where both $$P, Q$$ are open sets
 > Thus $$[a,b]$$ must be disconnected
 > From [A.1](#A.1), we know that $$[a,b]$$ is connected
 > This gives us a contradiction, hence $$P\cap Q \neq \emptyset$$
 > Q.E.D
[](-----------------------------)
3. <a id="A.3"></a> In $$(X,d)$$ all [adherent points](#adherent) of $$A\subseteq X$$ are either [interior points](#interior-pt) or [boundary points](#boundary-pt) of $$A$$
  > **Proof**
  > Let us take an arbitrary set $$A$$
  > Let us assume, that there exists an adherent point $$x$$ that is neither an interior point, nor a boundary point.
  > Since $$x$$ is an adherent point, $$\forall r>0 : B(x, r) \cap A \neq\emptyset$$
  > Since $$x$$ is not a boundary point, it must be an interior or exterior point
  > We already know that $$x$$ is not an interior point
  > $$x$$ must be an exterior point
  > Thus, $$\exists r>0 : B(x_0, r) \cap A = \emptyset$$
  > This contradicticts the definition of an adherent point
  > Thus $$x$$ must be either an interior point or a boundary point
  > Q.E.D
[](-----------------------------)
4. <a id="A.4"></a> In $$(X,d)$$, $$A\subseteq X$$ is a [closed set](#closed-set) if and only if  $$A = \overline{A}$$
  > **Proof**
  > - $$\implies$$
  > Let us take an arbitrary closed set $$A$$
  > $$\partial A \subseteq A$$
  > $$\forall x\in A : x$$ is interior $$\lor ~x$$ is exterior $$\lor ~x$$ is a boundary point
  > $$x\in A \implies x$$ cannot be an exterior point since $$\forall r>0 : x\in B(x,r)$$ and thus $$x \in B(x,r) \cap A$$
  > Hence $$x$$ must be an interior or boundary point
  > From [A.4](#A.4), we know that all adherent points are interior or boundary points
  > Thus $$x$$ is an adherent point of $$A$$
  > Since all points in this closed set $$A$$ are its adherent points $$A\subseteq \overline{A}$$
  > Let us take a $$y\not\in A$$
  > Since $$A$$ is a closed set, $$y\not\in A \implies y\not\in \partial A$$
  > $$y\not\in A \implies y$$ not an interior point of $$A$$
  > Thus $$y$$ must be an exterior point of $$A$$
  > $$y$$ exterior point $$\implies y$$ is not an adherent point
  > Thus $$A = \overline{A}$$
  > Q.E.D
  > - $$\impliedby$$
  > Let us take an arbitrary set $$A$$ such that $$A=\overline{A}$$
  > $$x\in \overline{A} \iff x$$ is an adherent point of $$A$$
  > From [A.3](#A.3) we can say that $$x$$ is either an interior point or a boundary point of $$A$$
  > All points in $$A$$ are either boundary points of $$A$$ or interior points of $$A$$
  > $$\partial A \subseteq A$$, hence $$A$$ is closed
  > Q.E.D
[](-----------------------------)
5. <a id="A.5"></a> In $$(X,d)$$, if $$A\subseteq X$$ then all [limit points](#limit-pt) of $$A$$ are also [adherent points](#adherent-pt) of $$A$$
  > **Proof**
  > Let us take an arbitrary limit point $$x$$ of an arbitrary set $$A$$
  > Since $$x$$ is a limit point, it must be the case that $$\forall r>0 : B(x, r)\setminus\{x\} \cap A \neq \emptyset$$
  > $$B(x, r)\setminus\{x\}\subseteq B(x, r)$$
  > Hence we can say that $$\forall r>0 : B(x, r) \cap A \neq \emptyset$$
  > Thus $$x$$ is an adherent point
  > Q.E.D
[](-----------------------------)
6. <a id="A.6"></a> Every [adherent point](#adherent-pt) of $$A$$ that is not a [limit point](#limit-pt) of $$A$$ is in $$A$$
  > **Proof**
  > Let us take an adherent point of $$A$$, $$x$$
  > $$x$$ is not a limit point
  > Since $$x$$ is an adherent point, it must be the case that $$\forall r>0 : B(x, r)\cap A \neq \emptyset$$
  > Since $$x$$ is not a limit point,  it must be the case that $$\exists r>0 : B(x, r)\setminus\{x\} \cap A = \emptyset$$
  > Thus we can say that $$\exists r>0 : B(x,r)\cap A \neq \emptyset \land B(x,r)\setminus\{x\}\cap A = \emptyset$$
  > This implies that $$x\in A$$
  > Q.E.D
[](-----------------------------)
7. <a id="A.7"></a> In $$(X,d)$$, $$A\subseteq X$$ is a [closed set](#closed-set) if and only if  $$A$$ contains all its [limit points](#limit-pt)
  > **Proof**
  > From [A.4](#A.4), we know that $$A$$ is closed $$\iff A=\overline{A}$$
  > From [A.5](#A.5), we know that all limit points are adherent points thus any limit point of $$A$$, $$x\in \overline{A}$$
  > Hence any limit point of $$A$$, $$x\in A$$
  > From [A.6](#A.6), we know that any adherent point of $$A$$ that is not a limit point is in $$A$$ itself
  > That is to say that if a set contains all its limit points it will also contain all its adherent points
  > Thus we can say that $$A$$ is closed $$\iff A$$ contains all its limit points
  > Q.E.D






[](-----------------------------)
[^0]: All definitions borrowed from <u>Analysis II, Tao, 2016</u>
[^1]: Borrowed from [here](https://math.stackexchange.com/questions/1686220/difference-between-adherent-point-boundary-point-and-limit-point)



