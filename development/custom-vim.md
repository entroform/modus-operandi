```bash
#!/bin/bash
# Remove previous bundle installations.
sudo rm -r ~/.vim/bundle;
mkdir ~/.vim/bundle
# Git clone vundle.
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
# Install vim and vundle configurations.
cat ./.vimrc-vundle > ~/.vimrc
cat ./.vimrc >> ~/.vimrc
# Initialize vundle plugins.
vim +PluginInstall +qall
echo ".vimrc and vundle is installed."
```

```
" 2016-11-22
" required
set nocompatible

" required
filetype off

" set the runtime path to include Vundle and initialize
set rtp+=$HOME/.vim/bundle/Vundle.vim

call vundle#begin()

" let Vundle manage Vundle
Plugin 'VundleVim/Vundle.vim'

" vim-markdown
Plugin 'mattn/emmet-vim'
Plugin 'klen/python-mode'
Plugin 'scrooloose/syntastic'
Plugin 'godlygeek/tabular'
Plugin 'bling/vim-airline'
Plugin 'kchmck/vim-coffee-script'
Plugin 'elzr/vim-json'
Plugin 'plasticboy/vim-markdown'
Plugin 'tpope/vim-surround'

" All of your Plugins must be added before the following line
call vundle#end()

" required
filetype plugin indent on

" Brief help
" :PluginList       - lists configured plugins
" :PluginInstall    - installs plugins; append `!` to update or just :PluginUpdate
" :PluginSearch foo - searches for foo; append `!` to refresh local cache
" :PluginClean      - confirms removal of unused plugins; append `!` to auto-approve removal
" see :h vundle for more details or wiki for FAQ
" Put your non-Plugin stuff after this line
```