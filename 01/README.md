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

The remainder of the division $m/n$ must be less than *n* (otherwise it would
carry over). In step E1, we compare the values of the denominator and remainder
from the previous step, therefore $m$ will always be greater than $n$, except
maybe at the very start which $m$ and $n$ could be any positive integer.

### Exercise 3 [*20*]

Change Algorithm E (for the sake of efficiency) so that all trivial replacement
operations such as "$m \leftarrow n$" are avoided. Write this new algorithm in
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
