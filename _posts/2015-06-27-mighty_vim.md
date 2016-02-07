---
layout:     post
title:      Climbing the Almighty Vim Ladder
date:       2016-02-07 12:32:18
summary:    new commands to go higher and higher
categories: jekyll pixyll
---

### Search and Replace Visually
When you need to search for and replace in only part of a file:

1. visually select the block 
2. type <b>: </b>
    * vim inserts '<,'> to denote your selection
3. search as usual by typing <b>s/oldword/newword/g</b>
    * 'g' ensures all occurrence, not just the first are changed

To search without visually selecting:

{% highlight python %}
:%s/dog/cat/g
{% endhighlight %}

* appending c, prompts for confirmation before replacing

### The Power of Global Commands

Syntax: 
{% highlight python %}
:[range]g/<pattern>/command
{% endhighlight %}

How do you use this? Say you'd like to delete all blank lines...
{% highlight python %}
:g/^$/d
{% endhighlight %}

Or simply display all line with Joe or Fred: 
{% highlight python %}
:g/joe.fred/
{% endhighlight %}

Or to yank all lines with the word "fred" alter command to <b>y A</b>

Delete everything in between: 
{% highlight python %}
:g/<pattern1>/,/<pattern2>/d
{% endhighlight %}

### Add or delete on many lines, at once!

Say you're working with: 
{% highlight python %}
2012: 5.68,
2013: 6.02,
2014: 6.38,
{% endhighlight %}

To surround all the dates with quotes: 

1. visually select 
2. type <b>I (or A)</b> (must be capital) 
3. then type " (or any word you desire)
4. escape

et voila: 

{% highlight python %}
"2012": 5.68,
"2013": 6.02,
"2014": 6.38,
{% endhighlight %}
### Tags, Parenthesis, and all that

With Tim Pope's <a href="https://github.com/tpope/vim-surround">Surround Plugin</a>
{% highlight html %}
<div>hi there</div>
{% endhighlight %}
becomes
{% highlight html %}
<p>hi there</p>
{% endhighlight %}
through <b>cst\<p\></b>.  <span class="mid-gray">In English:"change surrounding tag to \<p\>"</span>

Similarly, <b> cs(" </b> changes () to "" 

To surround a word with a \<span\> tag: <b>ysiw\<span\> </b>

And best of all, for an entire line, select visually then <b>S</b> to surround with tag of choice.

### Small Goodies
* <b> gv </b> reselects last visual area
* <b> g; </b> jump to last edit
* <b> s </b> deletes character and activates insert mode
