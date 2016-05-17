---
layout:     post
title:      Python's Itertools
date:       2016-04-04 12:32:18
summary:    generator power
categories: jekyll pixyll
description: python itertools module for faster programs 
---

Itertools are a mighty powerful way to lazily, efficiently work 
any iterable data structure like lists or strings.
For example, *imap* and *ifilter* like their plain counter parts
*map* and *filter* operate on a list, but **lazily** by returning iterator


## Groupby()

Not quite the SQL groupby() you may be used to. 
Instead groupby accepts an iterable data structure and a mapping function.
The goal is to return **consecutive items in group**. Here's an example,

{% highlight python %}
from itertools import groupby
writers = [("Tolstoy", "Russia"), ("Dostoyevsky", "Russia"), 
           ("Hemingway", "America"), ("Sartre", "France"), 
           ("Turgenev", "Russia")]

for writer, country in groupby(writers, lambda w: w[1]):
    print(w, c)
{% endhighlight %}

returns

{% highlight python %}
>>> ('Russia', <itertools._grouper object at 0x107165e90>)
>>> ('America', <itertools._grouper object at 0x107165ed0>)
>>> ('France', <itertools._grouper object at 0x107165e90>)
>>> ('Russia', <itertools._grouper object at 0x107165ed0>)
{% endhighlight %}

The second element of each tuple is an iterable, grouping writers
of the same country that appearing one after another.
Note "Russia" appears twice, because "Turgenev" while Russian doesn't appear 
after or before another Russian writer.

You can store each group in a list for example and use the consecutive grouping 
for other processing.

This [post](http://naiquevin.github.io/a-look-at-some-of-pythons-useful-itertools.html) is a wonderful reference.
