# Chapter 01

## Section 1.1

### Exercise 1

[*10*] The text showed how to interchange the values of variables $m$ and $n$, using
the replacement notation, by setting $t \leftarrow m, m \leftarrow n, n
\leftarrow t$. Show how the values of *four* variables $(a, b, c, d)$ can be
rearranged to $(b,c,d,a)$ by a sequence of replacements. In other words, the
new value of $a$ is to be the original value of $b$, etc. Try to use the
minimum number of replacements.

#### Solution

Similarly using a fifth variable $t$:

$t \leftarrow a, a \leftarrow b, b \leftarrow c, c \leftarrow d, d \leftarrow
t$.

### Exercise 2

[*15*] Prove that $m$ is always greater than $n$ at the beginning of step E1, except
possibly the first time this step occurs.

#### Solution

The remainder of the division $\frac{m}{n}$ must be less than $n$ (otherwise it would
carry over). In step E1, we compare the values of the denominator and remainder
from the previous step, therefore $m$ will always be greater than $n$, except
maybe at the very start which $m$ and $n$ could be any positive integer.

### Exercise 3

[*20*] Change Algorithm E (for the sake of efficiency) so that all trivial replacement
operations such as " $m \leftarrow n$ " are avoided. Write this new algorithm in
the style of Algorithm E, and call it Algorithm F.

#### Solution

**Algorithm F** (*Modified Euclid's algorithm*). Given two positive integers
$m$ and $n$, find their *greatest common divisor*, that is, the largest
positive integer that evenly divides both $m$ and $n$.

**F1.** [Find remainder.] Divide $m$ by $n$ and let $r$ be the remainder. (We
will have $0 \leq r \lt n$.)

**F2.** [Is it zero?] If $r = 0$, the algorithm terminates; $n$ is the answer.

**F3.** [Find remainder.] Divide $n$ by $r$ and let $m$ be the remainder. (We
will have $0 \leq m \lt r$.)

**F4.** [Is it zero?] If $m = 0$, the algorithm terminates; $r$ is the answer.

**F5.** [Find remainder.] Divide $r$ by $m$ and let $n$ be the remainder. (We
will have $0 \leq n \lt m$.)

**F6.** [Is it zero?] If $n = 0$, the algorithm terminates; $m$ is the answer.
Otherwise, go back to step F1. $\blacksquare$

### Exercise 4

[*16*] What is the greatest common divisor of 2166 and 6099?

#### Solution

Following Algorithm E, values of $m$, $n$ and $r$:

```math
(6099, 2166, 1767)

(2166, 1767, 399)

(1767, 399, 171)

(399, 171, 57)

(171, 57, 0)

57
```

### $\blacktriangleright$ Exercise 5

[*12*] Show that the "Procedure for Reading This Set of Books" that appears in the
preface actually fails to be a genuine algorithm on three of our five counts!
Also mention some differences in format between it and Algorithm E.

#### Solution

1. It is not finite; it could continue indefinitely.
2. It is not definite enough; each step is not defined precisely enough that a
   primitive computer could follow along.
3. It is not effective enough that someone could follow along on pencil and
   paper with rudimentary operations.

Although the general format of a list of steps is similar to Algorithm E, each
steps in the procedure are broad enough that there is no bracketed descriptor
for each step, nor is there any terminating step, nor is there a Q.E.D. symbol
terminating the algorithm.

### Exercise 6

[*20*] What is $T_{5}$, the average number of times step E1 is performed when $n = 5$?

#### Solution

```math
m = 1: (1, 5, 1), (5, 1, 0), T_{5,1} = 2

m = 2: (2, 5, 2), (5, 2, 1), (2, 1, 0), T_{5,2} = 3

m = 3: (3, 5, 3), (5, 3, 2), (3, 2, 1), (2, 1, 0), T_{5,3} = 4

m = 4: (4, 5, 4), (5, 4, 1), (4, 1, 0), T_{5,4} = 3

m = 5: (5, 5, 0), T_{5,5} = 1

T_{5} = 2.6
```

### $\blacktriangleright$ Exercise 7

[*M21*] Suppose that $m$ is known and $n$ is allowed to range over all positive
integers; let $U_{m}$ be the average number of times that step E1 is executed
in Algorithm E. Show that $U_{m}$ is well defined. Is $U_{m}$ in any way
related to $T_{m}$?

#### Solution

For $U_{m}$ to be well defined, it must have a solution for all $n \in \left\{0,
\dots, m\right\}$. For the first execution of E1, if $n \leq m$ the algorithm
begins processing the numbers smaller in the remainder of $n / m$. If $n \gt
m$, then the values of $m$ and $n$ switch positions, so $U_{m} = T_{m} + 1$.

### $\blacktriangleright$ Exercise 9

[*M30*] Suppose that $C_{1} = \left(Q_{1}, I_{1}, \Omega_{1}, f_{1}\right)$ and
$C_{2} = \left(Q_{2}, I_{2}, \Omega_{2}, f_{2}\right)$ are computational
methods. For example, C_{1} might stand for Algorithm E as in Eqs. (2), except
that $m$ and $n$ are restricted in magnitude, and $C_{2}$ might stand for a
computer program implementation of Algorithm E. (Thus $Q_{2}$ might be the set
of all states of the machine, i.e., all possible configurations of its memory
and registers; $f_{2}$ might be the definition of single machine actions; and
$I_{2}$ might be the initial state, including the program for determing the
greatest common divisor as well as the values of $m$ and $n$.)

Formulate a set-theoretic definition for the concept " $C_{2}$ is a
representation of $C_{1}$ " or " $C_{2}$ simulates $C_{1}$." This is to mean
intuitively that any computation sequence of $C_{1}$ is mimicked by $C_{2}$,
except that $C_{2}$ might take more steps in which to do the computation and it
might retain more information in its states. (We thereby obtain a rigorous
interpretation of the statement, "Program $X$ is an implementation of Algorithm
$Y$.")

#### Solution

$C_{2}$ would represent $C_{1}$ if there is sufficent mapping between $C_{1}$
and $C_{2}$, such that there are definite functions that map the input sets
$I_{1}$ to $I_{2}$, and that we can iterate a step in $f_{2}$ enough times so
that their results are equal. We would have to define these mapping functions
for each step of the algorithm, so that if we get some value that does not
nicely map one computational method to the other, it is undefined and makes the
statement invalid.
