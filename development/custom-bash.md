# Custom Bash Config

Add the following to your `.bash_profile` or `.bashrc`.

```bash
# aliases

alias ch='history -c'
alias cls='clear'
alias desktop='cd ~/Desktop'
alias ll='ls -alGF'
alias ~='cd ~'
alias ..='cd ..'

# Colorizes username and computer name.
export PS1="\[\033[36m\]\u\[\033[m\]@\[\033[32m\]\h:\[\033[33;1m\]\w\[\033[m\]\$"

# Enables command line coloring.
export CLICOLOR=1
export LSCOLORS=ExFxBxDxCxegedabagacad
```

## Explanation

### .bash_profile and .bashrc

`.bash_profile` is executed for login shells.
For example: when you login (type in username and password) via console or via ssh.
This is executed before the initial command prompt.

`.bashrc` is executed for interactive non-login shells.
This is executed before the window command prompt or when you start a new bash instance.

On OS X, Terminal by default runs a login shell every time.

## Links

- http://domenic.phiolo.org/changing-your-command-line-colors/