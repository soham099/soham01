---
title: "Two Beautiful Results concerning Discrete Harmonic Functions"
header-includes:
    - \usepackage{mathrsfs}
    - \newcommand{\prob}{\mathbb{P}}
    - \newcommand{\E}{\mathbb{E}}
    - \newcommand{\V}{\mathbb{V}}
    - \newcommand{\Sample}{\mathcal{S}}
    - \newcommand{\R}{\mathbb{R}}
    - \newcommand{\Co}{\mathbb{C}}
    - \newcommand{\N}{\mathbb{N}}
    - \newcommand{\Cov}{\mathbb{C}\text{ov}}
    - \newcommand{\I}{\mathbb{I}}
    - \newcommand{\n}{\mathcal{N}}
    - \newcommand{\Lf}{\mathcal{L}}
    - \newcommand{\Q}{\mathbb{Q}}
    - \newcommand{\Z}{\mathbb{Z}}
    - \newcommand{\F}{\mathscr{F}}
    - \newcommand{\Sg}{\mathfrak{S}}
    - \newcommand{\Bo}{\mathcal{B}}
    - \newcommand{\transpose}{\mathsf{T}}
    - \newcommand{\indep}{\perp \!\!\! \perp}

authors: 
    - admin
date: '2020-11-09'
subtitle: 'During the time of shelter-in-place lockdown due to global pandemic of COVID-19'
summary: 'Snippets from a riveting course on Martingale'
featured: yes
---

We start with a nice problem that appeared on **Regional Mathematics Olympiad, India, 1991** :


**Problem 1**: *The $64$ squares of an $8 \times 8$ chessboard are filled with positive integers in such a way that each integer is the average of the integers on the neighbouring squares. Show that in fact all the $64$ entries are equal.*

The solution to this is easy and well-known. Consider the square $v$ with the smallest number (which exists, thanks to Well-Ordering Principle) $i$ on it, and since this is an average of the numbers on its neighbors, the squares in $N(v)$ also have $i$ on it. This way, we can reach all the squares on the chessboard, all of whom have $i$ on it, and this completes the proof. \hfill $\blacksquare$

Next, we see a simple generalization of this problem :

**Problem 2**: *Let* $f:\Z^2 \to R$ *be a function satisfying* $f(x)=\frac{1}{4}\sum_{y \sim x} f(y)$, *where $y \sim x$ means there is an edge between $x$ and $y$ . Prove that, if $f$ is bounded, then $f$ is constant on $\Z^2$*.

Before looking into the solution of this problem, we take the time to notice that **Problem 2** is a generalization on **Problem 1** in two ways: firstly, we have moved to a unbounded set-up $Z^2$ from the initial set-up of a finite chessboard; and secondly, we are  allowing the function to take any real values, not just positive integers. These two generalizations simply implies that we cannot look for the node with the smallest number in it, as we did with the **Problem 1**. Nevertheless, the solution to the first problem was simple. How hard can the solution to this standard generalization be?

Turns out, the multitude of solutions that exist to the **Problem 2**, is not at all elementary, and definitely out-of-scope of a high-school student, sharply in contrast to the **Problem 1**. This is a popular problem (we will come to this later), and some of its solutions are by virtue of Complex Analysis and Functional Analysis. But perhaps, the most popular solution to this problem is also the most beautiful one, for it draws from the elegant realm of Probability and Stochastic Processes (which, although a standard technique in Stochastic Calculus, strikes me everytime I encounter, for nothing "random" is mentioned in such problems for you to apply Probabilistic machinery). With this preface, let's delve into the solution:

**Solution to Problem 2** :

Consider a Simple Symmetric Random Walk $\{X_n\}_{n \geq 1}$ on $\Z^2$, starting from any fixed point $x \in \Z^2$.  Consider the stochastic process $\{f(X_n)\}_{n \geq 1}$. We claim that $\{f(X_n)\}$ is a Martingale with respect to the increasing filtration $\F_n$, where $\F_n=\sigma(X_t : t\leq n )$. The probability measure is that induced by $X_n$ . For simplicity we will denote any probability measure by $\prob$.

First we prove the claim. Clearly, there are only finitely many choices for $X_n$, and thus finitely many choices for $f(X_n)$, and thus $f(X_n)$ is integrable. Finally, 

$$\begin{align}
\E_x\left(f(X_{n+1}) | \F_n  \right)&= \E_x \left(f(X_{n+1}) | X_n \right) \quad \text{(Using Markov Property of SRW)} \\
&= \frac{1}{4}  \sum_{y \sim X_n} f(y) \quad \text{(As the RW is Symmetric, it can jump to any of the $4$ equiprobable neighbors)}\\
&= f(X_n) \quad \text{(by definition of $f$)}\\
\end{align}$$

This proves the claim.

Now note that $f$ is bounded. This implies that the martingale $f(X_n)$ is Uniformly Bounded, and thus, Uniformly Integrable. This paves the way for **Levy's Upward Theorem**, which is as follows:

**Levy's Upward Theorem** :
*If $(X_n, \F_n)$ are Uniformly Integrable Martingales, then there exists an integrable Random Variable $X$ such that $X_n \to X$ almost surely and in $L^1$, and further $X_n=\E(X | \F_n)$*

Using this , we get an integrable random variable $M_{\infty}$ such that $f(X_n) \to M_{\infty}$ almost surely. 

Now, time for our coup de grâce. Let $f$ be non-constant. Since the simple symmetric random walk on $\Z^2$ is Irreducible and Recurrent, $\{X_n\}$ visits all the lattices infintely often with probability 1. That is, with probability 1, $\{f(X_n)\}$ takes all the distinct values of Range$(f)$ infinitely many times. Clearly this is a contradiction, for $\{f(X_n)\}$ cannot take distinct values infinitely many times and still converge to $M_{\infty}$. \hfill $\blacksquare$


