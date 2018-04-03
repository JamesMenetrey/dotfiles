# Dotfiles

## For macOS

### Requirements

Homebrew installed:

    /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

Git installed:

    brew install git zsh

Set zsh as your login shell:

    chsh -s $(which zsh)

### Install

Clone onto your laptop:

    cd ~ && git clone git@github.com:ZenLulz/dotfiles.git .dotfiles

Install [rcm](https://github.com/thoughtbot/rcm) and others dependencies
like `vim` and more:

    sh ~/.dotfiles/brewfile

Install:

    rcup -d .dotfiles -x README.md -x brewfile 

This will create symlinks for config files in your home directory. The `-x`
options, which exclude the `README.md` and `brewfile` files. 
You can safely run `rcup` multiple times to update:

    rcup

If you use iTerm, I recommand solarized color scheme (same used in my Vim
config): https://gist.github.com/ZenLulz/c812f70fc86ebdbb189d9fb82f98197e.

## Maintenance

### Trying a dry run

Dry run with lsrc(1). Look for anything unexpected in here, such as _~/.install_ or _~/.Makefile_, or an empty list of dotfiles.

    lsrc

### Adding a new file

When necessary, add new rc files to the dotfiles directory with mkrc(1).

    mkrc ~/.tigrc

In the other direction, you can use rcup(1) to create the symlinks from _~/.dotfiles_ to your home directory.

    rcup tigrc

## License

MIT (see LICENSE file)

Inspired by thoughtbot dotfiles licensed under MIT with thoughbot copyright:
https://github.com/thoughtbot/dotfiles
