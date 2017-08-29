---
layout:     post
title:      What to pack?
date:       2015-05-25 12:32:18
summary:    an enticing app, a script snack to go with your apple lap (top)...
---

### The Essentials
* VIM (+ vimium) in iTerm
    * Brew: to manage packages
* Python
* Latex 

I run Python 2 and 3 side-by-side using:
{% highlight bash %}
$ brew install python3
{% endhighlight %}

manage packages using **pip2** and **pip3** inside
virtual environments...

#### Virtual Environments

There are two ways to use these: globally
and inside a project's directory.

Inside a project: 
{% highlight bash %}
$ virtualenv --python=python3 name_o_env
#to activae
$ source name_o_env/bin/activate
$deactivate #to exist venv
{% endhighlight %}

Global environments are possible with a 
virtualenvwrapper:
{% highlight bash %}
$ mkvirtualenv name_o_env
$ workon env
$ deactivate
{% endhighlight %}

To see all the global environments type
**lsvirtualenv**.


The neat part of all this is you can record all the packages in your environment (ones presumably needed to run your code) via
{% highlight bash %}
$ pip freeze > requirements.txt
{% endhighlight %}

### The Utilities
* Spectacle
* Dropbox
* Caffeine 
* Karabiner

### The Accessories
* Mailbox (unsupported in 2016)
* Pocket
* Alfred

Updates: I have been trying Google Inbox as a replacement for Mailbox.

