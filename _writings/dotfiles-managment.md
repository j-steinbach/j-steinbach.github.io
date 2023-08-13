---
title: Dotfiles managment
---

The best guide for this is _imo_ https://dotfiles.github.io/utilities/. The [Arch Wiki](https://wiki.archlinux.org/title/Dotfiles) also has a list.

---

## What I want

- have a version controlled folder (Git!!)
- be able to deploy my dotfiles to my `.config` directory
- don't do anything stupid I can't fix manually
- support (and identify) files added from random executables (ie. not me; I want to see if my changes get overwritten from somewhere else)

### Extrawurst

What would be actually cool (>> [[literate-markdown]]?) is to define global variables for fonts, fontsize, ... and be able to use them in all my editors. But a find/replace should also do the trick :) Or running `sed` before deploying with something like `dotfiles-variable-fontsize`. 

- Update: Apparently _dotter_ does that through its [templates](https://github.com/SuperCuber/dotter/wiki/Templating-and-Caching). And _yadm_ might also be able to do this.

## Solutions

- https://github.com/anishathalye/dotbot
    - used it before, simple and stays away
- https://www.chezmoi.io/
    - not sure, do I want/need a multi-machine deploy? 
    - I do have two machines though, and it might be good for NixOS (I dislike baking stuff into the Nix config via HomeManager)
- https://github.com/thoughtbot/rcm
    - the tutorial seems scary
- https://www.gnu.org/software/stow/
    - this just manages symlinks?
    - nah.
- https://github.com/RichiH/vcsh
    - seems scary :o
- https://github.com/technicalpickles/homesick
    - maybe? but I dislike the 'castle' analogy
    - not sure how this is better than dotbot?
- https://github.com/SuperCuber/dotter
    - also seems nice; a mix of dotbot and chezmoi?
- https://github.com/TheLocehiliosan/yadm && https://yadm.io/#
    - similar to dotter?

I'll just continue using _dotbot_ and then _dotter_ and _chezmoi_ in case I lack something.

## Other tips

Download the binary of the script (same when doing some [[literate-markdown|tangling]]) into the root of the repo, so that we always have it accessible. ~Probably use a _git submodule_?