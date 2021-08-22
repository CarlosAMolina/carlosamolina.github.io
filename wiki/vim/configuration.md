# Configuration

## Clipboard

This is one of the first steps to work with Vim, for example, to copy and paste between different Vim instances.

### Command

Checking for X11-clipboard support in terminalEdit.

```bash
vim --version | grep clipboard
```

If you see -clipboard or -xterm_clipboard, use te following commands.

```bash
sudo apt-get install vim-gtk
```

### Resources

<https://vim.fandom.com/wiki/Accessing_the_system_clipboard>

## Config file

### Modify config file

```bash
vim ~/.vimrc
```

Note. If the previous file does not exist, create it in order to avoid edit /etc/vim/vimrc as a super user.

### Configuration example

```bash
" Indentation
set expandtab           " Indent with spaces https://vim.fandom.com/wiki/Indenting_source_code
set shiftwidth=4        " Indent with 4 spaces https://vim.fandom.com/wiki/Indenting_source_code
set softtabstop=4       " Indent with 4 spaces https://vim.fandom.com/wiki/Indenting_source_code
" Paste
set paste               " Prevents Vim from auto-indenting the pasted code.
set clipboard=unnamed   " Using the clipboard as the default register.
                        " if vim -version | grep clibpboard == -clipboard and
                        " -xterm_clipboard -> apt-get install vim-gtk
" Screen information.
set laststatus=2        " Displaying status line always.
set nu                  " Show line numbers.
set rnu                 " Line numbers relative to the current line.
" Tmux
set bg=dark             " Avoid color errors with tmux.
```

### References

Set bg=dark

<https://unix.stackexchange.com/questions/348771/why-do-vim-colors-look-different-inside-and-outside-of-tmux>

