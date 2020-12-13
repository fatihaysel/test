---
title: "Git Essentials"
tags: "Git"
---

# Git Auto-Complete

### This guideline for **_Mac & Linux_** users.

If you are using **_Windows_** you have already have auto-completion.

## Let's Start With Dependencies

The Git community share scripst on Github. We need open this repository and find [auto-completion scripts](https://github.com/git/git/tree/master/contrib/completion) for _bash_ or _zsh_.

![Git repo image](https://res.cloudinary.com/practicaldev/image/fetch/s--5ZDerChi--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/rmhmbalsdnnioli84awp.jpeg)

1.  Create `.zsh` folder on your top directory.
2.  Then copy `git-completion.zsh` and `git-completion.bash`. We use _Curl_ to download.
3.  Configuration `.zshrc` file at top directory.

## Downloading Scripts

```bash
    # Go to top directory
    # Create .zsh folder
    # Go inside .zsh folder
    cd
    mkdir -p .zsh
    cd .zsh
    
    # Download scripts
    curl -o git-completion.bash https://raw.githubusercontent.com/git/git/master/contrib/completion/git-completion.bash
    curl -o _git https://raw.githubusercontent.com/git/git/master/contrib/completion/git-completion.zsh
    
```

## Configuring the Shell

To activate the auto-completion, we need the configure `.zshrc` file. Open `.zshrc` file and copy following codes.

```bash
    # Copy this code.
zstyle ':completion:*:*:git:*' script ~/.zsh/git-completion.bash
fpath=(~/.zsh $fpath)

autoload -Uz compinit && compinit
```

Now go inside `.zshrc` file for add code lines.

```bash
    # Go to top directory
    # check all files for checking .zshrc file
    # if does not exist create one . If you have .zshrc file skip touch .zshrc part.
    # Then go insede using vim, nano, etc.
    cd
    ls -la
    touch .zshrc
    nano .zshrc
```

Now you opened `.zshrc` file paste the code lines here. Then save it with `ˆX` then press `enter` to save.

> On your first run clear auto-completion cache.

```bash
    rm .zcompdump
```

-   Now, open the terminal again and try it.
-   Write `git he` then press TAB.
