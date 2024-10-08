# Asymptotic Equivalences

In the lectures, we said that logarithms with different bases don't affect the
asymptotic complexity of an algorithm. Prove that $O(\log_{2} n)$ is the same as
$O(\log_{5} n)$. Use the mathematical definition of $O$ -- do a formal proof,
not just the intuition.

I have started with the formal definition of $O$ below. Add your answer to this
markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

$T(n) \in O(f(n)) \iff \exists c, n_0: T(n) \leq c \cdot f(n) \forall n \geq n_0$

## Plagarism Statement

All exercises must contain the following statement:
“I certify that I have listed all sources used to complete this exercise, including the use
of any Large Language Models. All of the work is my own, except where stated
otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is
suspected, charges may be filed against me without prior notice.”

## Note
I am attempting this from scratch, I did however, check it against last semesters answer before submitting. I am trying to work on conciseness.

## Answer
Start with a substitution (just have to pick either $\log_{2} n$ or $\log_{5} n$ but it doesn't matter which one), this will look like:

$T(n) \in O(\log_{2}(n))$ with the latter half of the definition being $T(n) \leq c*\log_{2}(n)$

Then we use the change of base formula $\log_{a}(b)= \frac{(\log_{c}(b))}{(log_{c}(a))}$ (reminded of this by looking at past repository)

This changes the latter portion to $T(n) \leq c*\frac{(\log_{5}(n))}{(log_{5}(2))}$

Which is the same as $T(n) \leq c*\frac{(1)}{(log_{5}(2))}$ $\log_{5}(n)$

Simplifies down to $T(n) \leq c*\log_{5}(n)$ because the demoninator was a constant.

$T(n) \leq c*\log_{5}(n)$ is exactly what we wer looking to find, but we also need to show that this wasn't a one way fluke, so we go back and start with $\log_{5}$.

Starting again with $T(n) \leq c*\log_{5}(n)$

$=>T(n) \leq c*\frac{(\log_{2}(n))}{(log_{2}(5))}$

$=>T(n) \leq c*\log_{2}(n)$

This shows that $O(\log_{2} n)$ is the same as $O(\log_{5} n)$ through transformation.

