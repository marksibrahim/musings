---
layout:     post
title:      Binary Search &#58; find the one in a million with only 20 questions 
date:       2015-10-20 12:32:18
summary:    even with one million sorted items, you need only 20 questions to find the one.
categories: jekyll pixyll
---

### What is Binary Search?

It's a clever way to find an item. 

An old-fashioned phone book is a great example. You'll find pages and pages of names like this: 

* <span class="mid-gray">  Abe Adams: 938-293-2938 </span>
* <span class="mid-gray">  Bob Mendez: 392-390-2817 </span>
* <span class="mid-gray">  ...</span>
* <span class="mid-gray"> Zane Zimmerman: 642-392-2080 </span>

Instead of naively flipping through each page (or looping through entries in an array data structure), looking through each name--aka *sequential search*-- you can be more clever: open the phone book to the middle. 

* Is the person your searching for to the left or right? 
* Go to the middle of the left (or right sections) and repeat. 

You're guaranteed to find the person only a few flips.

> Miraculously, even with 1,000,000 people listed in the phone book, twenty page flips is all you need to find the one.

Let's see the algorithm in Python!

### Build a Phone Book
We'll use two lists to store the phone book entries:

{% highlight python %}

people = ['Abe Adams', 'Bob Mendez', ...]
phone_numbers = [9382932938, 3923902817, ...]

{% endhighlight %}

### Now onto Binary Search

We'll create a search function to implement binary search, using recursion!
**search()** to implement **binary search**:
{% highlight python %}
def search(people, person, lower, upper):
"""
returns the index of the person we're searching for
using binary search
"""
    if lower == upper:
        return upper 
    else: 
        #always return an integer to use as an index
        middle = (lower + upper) / 2
        if person > people[middle]:
            return search(people, person , middle+1, upper)
        else:
            return search(people, person, lower, middle)
{% endhighlight %}

Each time the function is executed, we're flipping to the middle of the left or 
right sections of the phone book.
We collect the phone number of the person using the index in our **phone_numbers** blist.

Compared to a for loop, binary search is much more efficient.
In terms of complexity binary search is in **O(log n)**---in a worst and average case.


The phone book example is a nice illustration of binary search, but isn't the 
best solution to the problem. Instead, it's much more simple and efficient 
to build a dictionary (hash table) with names as keys and phone numbers as the 
value---the order of complexity is constant. So whether there are a 10 million or 
10 people, the time it takes to look up a person is the same! 
