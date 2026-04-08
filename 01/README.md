# Chapter 01

## Section 1.1

### Exercise 1 [*10*]

The text showed how to interchange the values of variables $m$ and $n$, using
the replacement notation, by setting $t \leftarrow m, m \leftarrow n, n
\leftarrow t$. Show how the values of *four* variables $(a, b, c, d)$ can be
rearranged to $(b,c,d,a)$ by a sequence of replacements. In other words, the
new value of $a$ is to be the original value of $b$, etc. Try to use the
minimum number of replacements.

#### Solution

Similarly using a fifth variable $t$:

$t \leftarrow a, a \leftarrow b, b \leftarrow c, c \leftarrow d, d \leftarrow
t$.

### Exercise 2 [*15*]

Prove that *m* is always greater than *n* at the beginning of step E1, except
possibly the first time this step occurs.

#### Solution

The remainder of the division $m/n$ must be less than $n$ (otherwise it would
carry over). In step E1, we compare the values of the denominator and remainder
from the previous step, therefore $m$ will always be greater than $n$, except
maybe at the very start which $m$ and $n$ could be any positive integer.

### Exercise 3 [*20*]

Change Algorithm E (for the sake of efficiency) so that all trivial replacement
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

### Exercise 4 [*16*]

What is the greatest common divisor of 2166 and 6099?

#### Solution

Following Algorithm E, values of $m$, $n$ and $r$:

$$
(6099, 2166, 1767)
(2166, 1767, 399)
(1767, 399, 171)
(399, 171, 57)
(171, 57, 0)
57
$$

### $\blacktriangleright$ Exercise 5 [*12*]

Show that the "Procedure for Reading This Set of Books" that appears in the
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

### Exercise 6. [*20*]

What is $T_{5}$, the average number of times step E1 is performed when $n = 5$?

#### Solution

Following $T_{n} = \frac{12 \ln 2}{\pi^{2}} \cdot \ln n$,
$T_{5} = \frac{12 \ln 2}{\pi^{2}} \cdot \ln 5 \approx 1.356$.
