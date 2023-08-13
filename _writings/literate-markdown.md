---
title: Literate Markdown
---


What I want
- write regular markdown with `src` blocks
    - don't have any extra `.lmt` or so files
- be able to tangle it without editor lock-in (Emacs, cough)
- don't deal with any other annoyances

## Possible solutions

- https://github.com/joakimmj/md-tangle
    - not sure this can do macro/reference expansion
- https://github.com/driusan/lmt
    - I used this before, to some success
- https://github.com/MartyGentillon/lmt-ruby
    - creates its own file format?
    - uses non-standard unicode which needs to be then extended?
- https://github.com/rebcabin/tangledown
    - tightly coupled with jupyter notebooks?

I also found one for Emacs/Orgmode, in case Emacs doesn't run (like every second week..)

- https://github.com/vlead/literate-tools

## Or just don't? 

> How about writing regular config files for a chance? And put the extra stuff into comments?

True.. my only usecase is `.dotfiles`. And switching between Emacs and Nvim has led me to duplicate stuff quite often. But the few times I came across literate dotfiles (mostly for Orgmode), they were just helpful. On the other hand -- nowadays I just search on Github for the problem I have and then move on. Or put comments anyhow. Or just get lost and confused if I need to fix that one line of code in that one random document.

So I guess I don't need this right feature right now. I'll do regular _dotfiles_ and then version-control and deploy them.

Only reason to still use this might be _includes_, when a program can only be configured in one giant file.

## Maybe there is a middle ground?

Don't tangle by default and just do a versioned folder with all the important dotfiles. And in complex cases feed a tangled markdown file into it.

(in complex cases: literate markdown) >> versioned _dotfiles_ folder >> deploy to `.config`

See also [[dotfiles-managmen
t]]

## What others do/did

- https://cam-barts.github.io/posts/Tangle-Write-Literate-Configs/
    - uses _md-tangle_ with Obsidian. Definitely interesting, as I also use a [[ZK]]