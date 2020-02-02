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


## Proving There are Infinitely Many Primes

### Step 1: $$ 0 <$$ "Something"

First, let's understand what these symbols mean:

![]({{ site.url }}/images/primes/positive-sin.png)

Careful, pi and product look very similar! How do we know this is true?

Where do the values of the products lie?
![]({{ site.url }}/images/primes/sin-product.png)

It turns out sin at all these values is positive
![]({{ site.url }}/images/primes/sin-plot.png)

So, we we've shown "something" is a bunch of positive numbers multiplied by one another.
Therefore, "something" > 0



### Step 2: Rewrite "Something"
We want to rewrite "something" in a new form to help us it's equal to zero. 

$$ \sin(\pi / p) = \sin(\pi / p + 2 \pi \prod_{p\prime} p\prime/ p) $$

![]({{ site.url }}/images/primes/long-sin-plot.png)

What does this repition imply? 
$$ \sin(n) = sin( n + 2 \pi k)$$

for any $k$ in $0, 1, 2, \dots $.

Now, let's think about one case for $p = 5$. Remember we know

![]({{ site.url }}/images/primes/sin-2pik.png)

Now all we need to show to convince ourselves we can rewrite "something" as desired is to find the $#$:
![]({{ site.url }}/images/primes/sin-2pik.png)


Luckly, this is true not just for $p=5$, but for any $p$, we can find it's corresponding $\prime p$ and cancel. 
Implying, for any $p$

$$ \sin(\pi / p) = \sin(\pi / p + 2 \pi \prod_{p\prime} p\prime/ p) $$

### Step 3: "Something" equals 0

Finally, to show "something" is also zero, let's remeber another fact about sin.
$$ \frac{(1 + 2 \prod_{p\prime} p\prime)}{p} $$ is an integer for some prime $p$.

![]({{ site.url }}/images/primes/zero-sin-plot.png)
![]({{ site.url }}/images/primes/rewrite-sin-for-zero.png)
![]({{ site.url }}/images/primes/numerator.png)
![]({{ site.url }}/images/primes/last-step.png)
Therefore, one of the terms in the product is 0, implying the whole product must be zero.
This is a contradiction!