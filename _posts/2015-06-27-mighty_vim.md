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
2. type ":" 
    * vim inserts '<,'> to denote your selection
3. search as usual by typing "s/oldword/newword/g"
    * 'g' ensures all occurrence, not just the first are changed


