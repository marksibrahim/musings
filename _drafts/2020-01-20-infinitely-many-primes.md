---
layout:     post
title:      Why there are Infinitely Many Prime Numbers
date:       2020-01-13 12:32:18
summary:    Explaining an elegant one line proof
---

<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>

<style>
img
{width: 60%;}
</style>

Prime numbers, like $2, 5 7,$ and $47$ are special [^1].
Unlike say 4 = 2 * 2 or 33 = 3 * 11, 
, prime numbers can't be written as the product of other numbers.They're the fundamental block we express other numbers through: every natural number is the product of primes [^2]. How many of these special prime numbers are there?

Infinitely many! 
A recent
[one-line proof](https://fermatslibrary.com/p/d09a9e47)
by Sam Northshield shows why there are infinitely many primes [^3]:

$$ 0 < \prod_p \sin(\pi / p) = \prod_p \sin(\frac{\pi * (1 + 2 * \prod_{p\prime} p\prime)}{p}) = 0. $$


You may wonder: what does sin have to do with prime numbers? 
Why $\pi$? Why is the left less than the right?

In this post, we'll untangle this elegant, one-line proof to reveal the answers.

[^1]: prime numbers are also special in an every day sense. Finding these special numbers is what makes sending credit card info. on the internet secure
[^2]: natural numbers are 1, 2, 3, 4, .... excluding fractions or irrational numbers such as pi.
[^3]: Many other proofs exist showing there are infinitely many primes (see [prime factorization](https://learncryptography.com/mathematics/prime-factorization/)).

### Imagine

Let's imagine there's a fixed number of primes. What then? 

Ignoring the in between, the proof says

$$ 0 < \text{something} = 0. $$

This means "something" is simultaneously equal to zero and strictly less than zero. Impossible! There must be infinitely many primes.

Now let's untangle the "something" in between.


### Step 1: $$ 0 <$$ "Something"

First, let's understand what these symbols mean:

![positive-sin]({{ site.url }}/images/primes/positive-sin.png#small-image)

* Careful, *pi* = 3.14... and *product* look very similar. 

How do we know this is true?

Let's see what these values equal
![sin-product]({{ site.url }}/images/primes/sin-product.png)

Not matter which prime $p$ we choose, 
$ sin(\pi / p) > 0$. 
![]({{ site.url }}/images/primes/sin-plot.png)

This means "something" is the product of positive numbers: 
"something" 
$ = sin(\pi / p) = + + ...+$. 

"Something" must be greater than 0.



### Step 2: Rewrite "Something"
We want to rewrite "something" in a new form  to see it's also equal to zero.
The proof says

$$ \sin(\pi / p) = \sin(\pi / p + 2 \pi \prod_{p\prime} p\prime/ p) $$

The product inside sin means

![]({{ site.url }}/images/primes/product-primes2.png)

Why is this true? Let's look at a graph of sin

![]({{ site.url }}/images/primes/long-sin-plot.png)

What does this repitition imply?
$ \sin(n) = sin( n + 2 \pi k)$
for any $k$ in $0, 1, 2, \dots $.

Now, let's think about one case for $p = 5$. Remember we know

![]({{ site.url }}/images/primes/sin-rewritten.png)

no matter which orange # we choose.

Now let's use this relationship to rewrite something by finding the right #:

![]({{ site.url }}/images/primes/sin-2pik.png)


Luckly, this is true not just for $p=5$, but for any $p$. Every natural number is the product of primes. We can always find a corresponding $p \prime$ to cancel any $p$. 
Implying, for any $p$

$$ \sin(\pi / p) = \sin(\pi / p + 2 \pi \prod_{p\prime} p\prime/ p) $$

### Step 3: "Something" equals 0

Finally, to show "something" is also zero, let's look at where sin is zero:

![]({{ site.url }}/images/primes/zero-sin-plot.png)

$sin(k \pi) = 0$ for any $k = 0, 1, 2, ...$.

Let's rewrite the terms inside sin in a friendlier form:
![]({{ site.url }}/images/primes/rewrite-sin-for-zero.png)
by combining the terms under a common denominator. 

Now notice
![]({{ site.url }}/images/primes/numerator.png)
because every number can be written as the product of primes. Let's call one of those primes $p^*$.
Then, 
![]({{ site.url }}/images/primes/last-step.png)

That's it! For $p = p^*$, $sin(\pi / p) = 0$. Implying,



$$ \prod_p \sin(\pi / p) = \sin(\pi / 2) \sin(\pi / 3) * 0 * .... = 0.$$


## The Punch Line

We first supposed there weren't infinitely many primes---only finitely many. Then we saw where that took us.
In step 1, we showed
$$ \prod_p \sin(\pi / p) = 0.$$

After rewriting, we showed $ \prod_p \sin(\pi / p) $ must also be greater than 0. That can't be. 

We confidently conclude our original assumption is wrong. There must be infinitely many primes.
