---
dg-publish: true
---
```tikz
\documentclass[4pt]{extarticle}
\usepackage[margin=1in]{geometry}
\usepackage{graphicx} % Required for inserting images
\usepackage{amsmath}
\usepackage{amsfonts}


\title{6200, lec1}
\author{rychen}
\date{August 2025}

\begin{document}

\maketitle

\section{DEF Learner and Adversary Setup}

We consider repeated interaction between a learner and an adversary. The learner has an action set $A = \{1, \ldots, k\}$, and the game proceeds over rounds $t = 1, \ldots, T$.

\subsection*{Round Structure}

At each round $t$:
\begin{enumerate}
    \item \textbf{Learner's choice.} With knowledge of past costs $\{C^1, \ldots, C^{t-1}\}$, the learner selects a probability distribution over actions $P^t = (P^t_1, \ldots, P^t_k) \in \Delta(A)$, where $P^t_i$ is the probability of playing action $i$. For example, a uniform distribution is $P^t = \{1/k, \ldots, 1/k\}$.
    \item \textbf{Adversary's choice.} With knowledge of $\{P^1, \ldots, P^t\}$, the adversary selects a cost vector $c^t = (c^t_1, \ldots, c^t_k) \in [0,1]^k$, where $c^t_i$ denotes the cost if the learner were to play action $i$ at round $t$.
    \item \textbf{Learner's incurred cost.} The learner then suffers the expected cost $c^t_L = \mathbb{E}_{i \sim P^t}[c^t_i] = \sum_{i=1}^k P^t_i c^t_i$.
\end{enumerate}

\subsection*{Game Record and Cumulative Costs}

\begin{itemize}
    \item The record of play after $t$ rounds is $\Pi^t = \{(P^s, c^s)\}_{s=1}^t$.
    \item The learner's cumulative cost after $T$ rounds is $C^T_L = \sum_{t=1}^T c^t_L$.
    \item The cumulative cost of always playing a fixed action $i \in A$ is $C^T_i = \sum_{t=1}^T c^t_i$.
\end{itemize}


\section{DEF Regret to the Best Fixed Action}

The learner's regret to action $i \in A$ after $T$ rounds is defined as
\[
\text{Reg}(\Pi^T, i) = C^T_L - C^T_i 
= \sum_{t=1}^T \big(c^t_L - c^t_i\big).
\]

\noindent We say the learner has regret to the best fixed action bounded by $\alpha$ if
\[
\max_{i \in A} \text{Reg}(\Pi^T, i) < \alpha.
\]

\subsection{Exp}
To the extent that the algorithm has higher cost than one of the
benchmark policies, we will say that the algorithm regrets not having played
that benchmark; our goal will be to design algorithms that do not have regret to any benchmark in some fixed classes.


\section{DEF  The Halving Algorithm}

For each action $i \in A$ and round $t \in T$, set initial weights $w_i^1 = 1$ when $t = 1$. Let $W^t = \sum_{i=1}^k w_i^t$ be the total weight of all actions at time $t$.

For $t = 1$ to $T$:
\begin{enumerate}
    \item \textbf{Play distribution.} Choose action distribution 
    \[
        P_i^t = \frac{w_i^t}{W^t}, \quad i \in A.
    \]
    \item \textbf{Observe costs.} Receive cost vector $c^t$ from the adversary.
    \item \textbf{Update weights.} For each $i \in A$, update
    \[
        w_i^{t+1} = w_i^t \big(1 - \mathbf{1}\{c_i^t > 0\}\big),
    \]
    and set total weight $W^{t+1} = \sum_{i=1}^k w_i^{t+1}$.
\end{enumerate}


\subsection{Exp}
When you turned the positive cost actions to weight zero, you learned what actions to not choose. When you chose the right action and enjoyed not cost, you are executing the right strategy. In either way, we are making progress.


\section{Theorem 1}

For any sequence of costs $\{c^1, \ldots, c^T\}$ such that there exists a perfect action $i^*$ with $c_{i^*}^t = 0$ for all $t$, the regret of the Halving algorithm to the best fixed action is at most
\[
\max_{i \in A} \text{Reg}(\Pi^T, i) = \text{Reg}(\Pi^T, i^*) \leq \ln(k).
\]

\subsection{Proof}

Note that for any record $\Pi$, the largest regret value is always attained for $i^*$, since
\[
\text{Reg}(\Pi^T, i^*) = C^T_L - 0 = C^T_L.
\]

At round $t$, define $C^t = \{i \in A : c_i^t > 0\}$ as the set of actions with positive cost. Let the cumulative weight of these actions be
\[
W(C^t) = \sum_{i \in C^t} w_i^t,
\]
which is the total weight of positive-cost actions at time $t$.

Since costs are in $[0,1]$, the learner’s expected cost satisfies
\[
c^t_L \leq \frac{W(C^t)}{W^t}.
\]

By the weight update rule, we have
\[
W^{t+1} = W^t - W(C^t),
\]
so
\[
c^t_L = \frac{W^t - W^{t+1}}{W^t} = 1 - \frac{W^{t+1}}{W^t}.
\]

Because a perfect action $i^*$ exists, its weight never goes to zero, so $W^{T+1} \geq 1$. Thus,
\[
1 \leq W^{T+1} = W^1 \cdot \prod_{t=1}^T \frac{W^{t+1}}{W^t}.
\]

Initially $W^1 = k$, hence
\[
1 \leq k \prod_{t=1}^T \frac{W^{t+1}}{W^t}
= k \prod_{t=1}^T (1 - c^t_L).
\]

Using $1 - x \leq e^{-x}$, we obtain
\[
1 \leq k \prod_{t=1}^T e^{-c^t_L} = k \exp\!\left(-\sum_{t=1}^T c^t_L\right) = k \exp(-C^T_L).
\]

Taking logarithms gives
\[
C^T_L \leq \ln(k).
\]

Hence, the regret of the Halving algorithm to the best fixed action is bounded by $\ln(k)$.





\end{document}

```