---
title: "Two Beautiful Results concerning Discrete Harmonic Functions"
authors: 
    - admin
date: '2020-11-09'
subtitle: 'During the time of shelter-in-place lockdown due to global pandemic of COVID-19'
summary: 'Snippets from a riveting course on Martingale'
featured: yes
---

We start with a nice problem that appeared on **Regional Mathematics Olympiad, India, 1991** :


**Problem 1**: *The $64$ squares of an $8 \times 8$ chessboard are filled with positive integers in such a way that each integer is the average of the integers on the neighbouring squares. Show that in fact all the $64$ entries are equal.*

The solution to this is easy and well-known. Consider the square $v$ with the smallest number (which exists, thanks to Well-Ordering Principle) $i$ on it, and since this is an average of the numbers on its neighbors, the squares in $N(v)$ also have $i$ on it. This way, we can reach all the squares on the chessboard, all of whom have $i$ on it, and this completes the proof. $\hfill$ $\blacksquare$

Next, we see a simple generalization of this problem :

**Problem 2**: *Let* $f:\mathbb{Z}^2 \to R$ *be a function satisfying* $f(x)=\frac{1}{4}\sum_{y \sim x} f(y)$, *where $y \sim x$ means there is an edge between $x$ and $y$ . Prove that, if $f$ is bounded, then $f$ is constant on $\mathbb{Z}^2$*.

Before looking into the solution of this problem, we take the time to notice that **Problem 2** is a generalization on **Problem 1** in two ways: firstly, we have moved to a unbounded set-up $\mathbb{Z}^2$ from the initial set-up of a finite chessboard; and secondly, we are  allowing the function to take any real values, not just positive integers. These two generalizations simply implies that we cannot look for the node with the smallest number in it, as we did with the **Problem 1**. Nevertheless, the solution to the first problem was simple. How hard can the solution to this standard generalization be?

Turns out, the multitude of solutions that exist to the **Problem 2**, is not at all elementary, and definitely out-of-scope of a high-school student, sharply in contrast to the **Problem 1**. This is a popular problem (we will come to this later), and some of its solutions are by virtue of Complex Analysis and Functional Analysis. But perhaps, the most popular solution to this problem is also the most beautiful one, for it draws from the elegant realm of Probability and Stochastic Processes (which, although a standard technique in Stochastic Calculus, strikes me everytime I encounter, for nothing "random" is mentioned in such problems for you to apply Probabilistic machinery). With this preface, let's delve into the solution:

**Solution to Problem 2** :

Consider a Simple Symmetric Random Walk $( X_n)\_{n \geq 1}$  on  $\mathbb{Z}^2$, starting from any fixed point $x \in \mathbb{Z}^2$.  Consider the stochastic process $(f(X_n))\_{n \geq 1}$. We claim that $(f(X_n))\_{n \geq 1}$ is a Martingale with respect to the increasing filtration $\mathbf{F}_n$, where $\mathbf{F}\_n=\sigma(X_t : t\leq n )$. 

First we prove the claim. Clearly, there are only finitely many choices for $X_n$, and thus finitely many choices for $f(X_n)$, and thus $f(X_n)$ is integrable. Finally, 


$$\begin{align}
\mathbb{E}\_x(f(X\_{n+1}) | \mathbf{F}\_n  )  & = \mathbb{E}\_x (f(X\_{n+1}) | X\_n ) \qquad \text{(Using Markov Property of SRW)}\\\\\\
                                            & = \dfrac{1}{4}  \sum_{y \sim X\_n} f(y) \qquad \text{(As the RW is Symmetric, it can jump to any of the $4$ equiprobable neighbors)}\\\\\\
                                            & = f(X\_n) \qquad \text{(by definition of $f$)}\\\\\\
\end{align}$$

This proves the claim.

Now note that $f$ is bounded, say by $M$. This implies that we can , without loss of generality, assume that the martingale $(f(X_n))\_{n \geq 1}$ is non-negative (otherwise just take a new martingale $g(X_n)=f(X_n)+M$ , and continue the proof ).  Then by Martingale Convegence Theorem (which states that *Any Non-negative Martingale converges to an integrable random variable almost surely*), we have that there exists an integrable random variable $M\_{\infty}$ such that $f(X_n) \to M\_{\infty}$ almost surely. 

Now, time for our coup de grâce. Let $f$ be non-constant. Since the simple symmetric random walk on $\mathbb{Z}^2$ is Irreducible and Recurrent, $(X_n)\_{n \geq 1}$ visits all the lattices infintely often with probability 1. That is, with probability 1, $(f(X_n))\_{n \geq 1}$ takes all the distinct values of Range$(f)$ infinitely many times. Clearly this is a contradiction, for $(f(X_n))\_{n \geq 1}$ cannot take distinct values infinitely many times and still converge to $M\_{\infty}$. $\qquad \qquad$ $\blacksquare$


The function $f:\mathbb{Z}^2 \to R$ in **Problem 2** satisfying $f(x)=\frac{1}{4}\sum_{y \sim x} f(y)$, is called a **Discrete Harmonic Function** . One can see the intuition behind such a nomenclature from the following handwaving arguments:

Let $e_1=(1,0)$, $e_2=(0,1)$, $e_3=(-1,0)$, $e_4=(0,-1)$. Then,

$$\begin{align}
& f(x)=\frac{1}{4}\sum_{y \sim x} f(y)=f(x)=\frac{1}{4}\sum_i f(x+e\_i)\\\\\\
\implies & \frac{1}{4}\sum_i ( f(x+e\_i) - f(x) ) =0\\\\\\
\end{align}$$

If we could do Taylor Series expansion of $f$ at $x+e_i$ centred around $x$ , then :
$$ f(x+e_i)= f(x)+ e\_i^T D(f)+ e\_i^T D^2(f(x+t\_i e\_i))e_i $$, where $t_i \in (0,1)$. 

Summing over $i=1(1)4$, and noting that $\sum_i e_i=(0,0)$, we have:
$$ 0=\sum_i (f(x+e\_i)- f(x))= \sum_i e\_i^T D^2(f(x+t\_i e\_i))e\_i = \sum_i \dfrac{\del^2 f(x+t\_i e\_i)}{\del x\_i^2}$$

where the last expression on the equality is reminiscent of $\Delta f$ .

In fact, the **Problem 2** is widely popular because this is simply the Discrete versions of the famous *Liouville's Theorem* :

**Liouville's Theorem**: *A bounded harmonic function on $\mathbb{R}^n$ is constant.*

# Discrete Dirichlet's Problem

A pertinent and famous question involving Harmonic Functions is the **Dirichlet Problem**, which, given a function $\phi$ and a closed convex set $D$ , aims to find $f$, such that $f$ is harmonic on the interior of $D$ and $f|\_{\del D}=\phi$. This problem arises from physics, mainly from Thermodynamics and heat equations. Again, this is essentially a problem of analytic flavour, and one can think that any solution might involve muddling through the quagmire of PDEs, but mathematician Itô provided a solution involvinng *Brownian Motion*. Of course, this solution is not at all elementary, but -keeping in sync with the flavour of this post-if we investigate the *Discrete Dirichlet's Problem*, we get a nice elegant solution using Martingales . 
