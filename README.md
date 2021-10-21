# Vim config



## Vim setup for C/C++

Download and install Vim:

```bash
sudo apt install vim 
```

Create vim config file:

```bash
vim .vimrc
```



## Download and install plugin manager vim-plug

Download and install curl:

```bash
sudo apt install curl
```

Follow instructions here https://github.com/junegunn/vim-plug. 

Don't forget to run the commands in Vim config file:

```bash
:source %
```

And install Vim plugins:

```bash
:PlugInstall
```



## Download and install npm

```bash
sudo apt install npm
sudo npm install -g n
sudo n stable
```

## Install coc.nvim

Follow the instructions here https://github.com/neoclide/coc.nvim:

Download and install nodejs:

```bash
curl -sL install-node.now.sh/lts | bash
```

Add plugin to .vimrc:

```bash
Plug 'neoclide/coc.nvim', {'branch': 'release'}
```

Don't forget to execute `:PlugInstall` in Vim.

## Doqnload and install clangd server

Follow the instructions here https://clangd.llvm.org/installation:

```bash
sudo apt-get install clangd-12
```

Make a default server:

```bash
sudo update-alternatives --install /usr/bin/clangd clangd /usr/bin/clangd-12 100
```

Execute in Vim:

```bash
:CocInstall coc-clangd
```

Add syntax highlighting:

```bash
Plug 'jackguo380/vim-lsp-cxx-highlight'
```

Add color support:

```bash
"Use 24-bit (true-color) mode in Vim/Neovim when outside tmux.
"If you're using tmux version 2.2 or later, you can remove the outermost $TMUX check and use tmux's 24-bit color support
"(see < http://sunaku.github.io/tmux-24bit-color.html#usage > for more information.)
if (empty($TMUX))
  if (has("nvim"))
    "For Neovim 0.1.3 and 0.1.4 < https://github.com/neovim/neovim/pull/2198 >
    let $NVIM_TUI_ENABLE_TRUE_COLOR=1
  endif
  "For Neovim > 0.1.5 and Vim > patch 7.4.1799 < https://github.com/vim/vim/commit/61be73bb0f965a895bfb064ea3e55476ac175162 >
  "Based on Vim patch 7.4.1770 (`guicolors` option) < https://github.com/vim/vim/commit/8a633e3427b47286869aa4b96f2bfc1fe65b25cd >
  " < https://github.com/neovim/neovim/wiki/Following-HEAD#20160511 >
  if (has("termguicolors"))
    set termguicolors
  endif
endif
```

