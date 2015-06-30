---
layout:     post
title:      Climbing the Almighty Vim Ladder
date:       2015-06-27 12:32:18
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

### Small Goodies
* <b> gv </b> reselects last visual area
* <b> g; </b> jump to last edit
* <b> s </b> deletes character and activates insert mode
