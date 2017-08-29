---
layout:     post
title:      Making Syntastic and Solarized play nicely in Vim
date:       2015-11-20 12:32:18
summary:    How to fix the obstrusive Syntastic gray bar in solarized
---

Syntastic is a great linter plugin for Vim, catching syntax errors while you write code in nearly any language (even Latex).
Since I spend most of my days editing in Vim, the obtrusive gray bar became intolerable.
Here's another user's screenshot from the
[github issue](https://github.com/altercation/solarized/issues/252):
![gray bar](https://camo.githubusercontent.com/cd7137cc22c897d136ab9ab1b91905748c1b4a09/687474703a2f2f662e636c2e6c792f6974656d732f33553074324c3035324c325631463256314230672f53637265656e25323053686f74253230323031332d30342d3032253230617425323031352e33352e35362e706e67)

Adjusting the color was more involved that I imagined...


### It's not Syntastic; it's the colorscheme

This was the key insight. 
All you need is to tweak a single line in the solarized colorscheme (solarized.vim file):
[see here](https://github.com/jumski/vim-colors-solarized/commit/54864d547cb54177e3a00d1166637c1fddddfad5)

et voila!
