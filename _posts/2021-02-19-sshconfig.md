---
layout: post
title: SSH config
permalink: sshconfig
---

*... in which we configure SSH.*

If you're working remotely on a HPC system (or other remote) work, chances are that you're using SSH a lot. This short blog post will detail a number of really convenient configurations you can easily make.

The best trick for working with SSH is using SSH keys to avoid entering your password all the time. This trixk is well covered on the internet. Instead I'll start by introducing the more obscure, but highly useful `~/.ssh/config` file. This file is unlikely to exists on your system (unlike the `.ssh` directory). The format of the file is self-evident, following an example:

```
Host jhpce01.jhsph.edu e
  HostName jhpce01.jhsph.edu
  User khansen
Host bitbucket.org bb
  Compression yes
  HostName bitbucket.org
  User hg
  ForwardX11 no
  ForwardX11Trusted no
Host *
  ForwardX11 yes
  ForwardX11Trusted yes
```

This sets up an ssh alias called `e` (last element of the `Host` line) which is a shortcut for the longer `khansen@jhspce01.jhsph.edu`. This alias can be re-used in `scp` making file copying a breeze, like

```
scp FILE e:
```

copies FILE to the root directory on the `e` server.

In the configuration file you can see how I disable X11 forwarding for the `bitbucket` host and I enable X11 forwarding by default (the `Host *`). This means I no longer have to think about whether to add `-X` to my `ssh` call.

