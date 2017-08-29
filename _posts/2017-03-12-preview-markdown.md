---
layout:     post
title:      Preview Markdown
date:       2017-03-12 12:32:18
summary:    How to preview a readme before pushing to GitHub
---

Have you ever wanted to preview `README` before pushing it to GitHub?
Here's a way.


### Setup
1. Download [GitHub Markdown CSS](https://raw.githubusercontent.com/marksibrahim/dotfiles/master/github_md.css) to your home directory
2. Add `preview_md()` function to your `.bash_profile`

```bash
    # add to ~/.bash_profile or ~/.bash_rc
    preview_md() {
        # $1 is argument specifying file to preview
            pandoc -o md_preview.html \
            --from markdown_github \
            --to html -c ~/github_md.css $1 
            && open md_preview.html \
            && sleep 2 && rm -f md_preview.html
            }
```

* Make sure `Pandoc` is installed on your machine. On Mac:
`$ brew install pandoc` will do the trick!

### Preview
Preview a markdown file: `$ preview_md file_name.md`

```bash
$ preview_md README.md
```

* preview markdown in [GitHub style](https://guides.github.com/features/mastering-markdown/)
* keeps your directory clean (deletes preview file automatically)
* renders in your browser (no programs to install)


Happy documenting!
