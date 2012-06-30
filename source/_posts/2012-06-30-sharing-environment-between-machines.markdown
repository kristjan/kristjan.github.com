---
layout: post
title: "Sharing environment between machines"
date: 2012-06-30 12:49
comments: true
categories: [environment, GitHub, Dropbox]
---
To facilitate setup of new machines, I keep configuration on GitHub at
[kristjan/.dotfiles](https://github.com/kristjan/.dotfiles) and
[kristjan/.vim](https://github.com/kristjan/.vim). This way, all I have to do to
set up my environment is install Git and clone those repos. `.dotfiles` comes
with an install script that just symlinks each dotfile from `~/.dotfiles/$FILE`
to `~/$FILE`.

A problem, though, is that some tools&mdash;like things that talk to
GitHub&mdash;need a private token or other data to exist somewhere in my
configuration. I can't go putting those in a public repo, so until now I've had
to either look them up or copy them from an old machine. This time, the old
machine is my old laptop sitting at home and available via SSH thanks to Back to
my Mac. Rather than remember the ID BTMM assigns me as part of its lengthy
hostname, I have another environment variable that also doesn't belong in a
repo. These things were sitting in my configs where I had to `git patch` around
them and ran the risk of at some point accidentally pushing them out.

The solution I've landed on is to store these in Dropbox and load them before
the rest of my configs and helpers. The top of my `.bashrc` looks like this:

```
HELPERS="
  Dropbox/.env
  .aliases
  .functions
  .nvm/nvm.sh
"

for helper in $HELPERS; do
  if [ -f $HOME/$helper ]; then
    . $HOME/$helper
  fi
done
```

And `Dropbox/.env` contains:


```
export GITHUB_TOKEN=<token>
export BOBBLE_HOST=bobble.<id>.members.btmm.icloud.com
```

Now my configs are public and easy to trade with people (which I do regularly to
learn new tricks), but private or irrelevant data is safely where only I can see
it (assuming the integrity of Dropbox). During setup, I just install Dropbox
before I clone my dotfiles, and everything is slightly more magical.
