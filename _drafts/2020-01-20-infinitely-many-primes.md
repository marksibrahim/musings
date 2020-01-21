---
layout:     post
title:      Why there are Infinitely Many Prime Numbers
date:       2020-01-13 12:32:18
summary:    Explaining an elegant one line proof
---

<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>

Prime numbers, such as $2, 5 7,$ and $47$ are special numbers [^1].
Unlike the number 4 (which equals $2*2$) or $33$ ( which equals $3 * 11$), prime numbers can't be written as the product of other numbers. How many of these special numbers are there?

A recent
[one-line proof](https://fermatslibrary.com/p/d09a9e47)
by Sam Northshield shows there are infinitely many primes [^2]:

$$ 0 < \prod_p \sin(\pi / p) = \prod_p \sin(\frac{\pi * (1 + 2 * \prod_{p\prime} p\prime)}{p}) = 0. $$

What does sin have to do with prime numbers? Why $\pi$? Why is the left less than the right?
In this post, we'll untangle this elegant, one-line proof to reveal the answers.

[^1]: prime numbers are also special in an every day sense. Finding these special numbers is what makes sending credit card info. on the internet secure
[^2]: Many other proofs exist showing there are infinitely many primes (see [prime factorization](https://learncryptography.com/mathematics/prime-factorization/)).

## Mapping our Path

Let's imagine there's a fixed number of primes. What then?

Ignoring the terms in between we get

$$ 0 < \text{something} = 0. $$

This means "something" is simultaneously equal to zero, but also less than zero. That's impossible!

So if we imagine there are finitely many primes, we get a contradiction, so it can't be the case. There must be infinitely many primes.

Now let's untangle the "something" in between.

## A Detour to Sine
sine curve plot and zeros.

$$ \sin(n) = sin( n + 2 \pi k)$$

for any $k$ in $0, 1, 2, \dots $.

## Proving There are Infinitely Many Primes
### Sine Product is Greater than Zero
$$ 0 < \prod_p \sin (\pi / p) $$

![]({{ site.url }}/images/primes/positive_sin.png)
![]({{ site.url }}/images/primes/positive_sin_expanded.png)
![]({{ site.url }}/images/primes/pi_positive.png)

### Rewrite Sine Product
 $$ \sin(\pi / p) = \sin(\pi / p + 2 \prod_{p\prime} p\prime/ p) $$

### Sine Product Equals 0
$$ \frac{(1 + 2 \prod_{p\prime} p\prime)}{p} $$ is an integer for some prime $p$.

Therefore, one of the terms in the product is 0, implying the whole product must be zero.

This is a contradiction!