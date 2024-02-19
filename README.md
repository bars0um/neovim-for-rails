All credit due to https://github.com/Sh1d0w/nvim-ide

This is a somewhat modified combination of plugins for Neovim to assist Rails developers based on the Sh1d0w/nvim-ide repo. 

I've made minor modifications to cater for some issues here and there. 

Tmux is your friend if you need to run stuff from outside the container and see logs and stuff while you edit the files you are working on. 
I'm sure there are other ways but I found that to be ok.

The configuration allows you to run a docker container and pass it a directory/file to edit.

Add the following in your .bashrc so you can simply run ```ed myfile.rb```
```
alias ed='f(){ docker run -it --rm -v $(cd $(dirname $1); pwd)/$(basename $1):/home/developer/workspace bars0um/alpine-n
vim; unset -f f; }; f'
alias ef='f(){ docker run -it --rm -v $(cd $(dirname $1); pwd)/$(basename $1):/home/developer/workspace/$(basename $1) b
ars0um/alpine-nvim; unset -f f; }; f'
```

Some useful shortcuts:

```\ -``` toggles NerdTree, I would not keep that open as it is easy to end up fzf'ing in its buffer by mistake

```<space> p``` fzf files

```<space> b``` fzf open buffers

```<space> g``` grep through files



