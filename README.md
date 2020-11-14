# VIM syntax file for THOR

A [VIM](https://www.vim.org/) syntax file for log files of [APT Scanner THOR](https://www.nextron-systems.com/thor/).

## Installation

Place the file in `$HOME/.vim/syntax/thor.vim`.

## Usage

For automatic usage depending on file extension (in the example below `*.thor`) place the following in your `vimrc`:

```
filetype plugin on
syntax on
au BufRead *.thor set filetype=thor
```

Note that VIM does not apply syntax highlighting to `*.txt` files.
For dynamically applying the syntax highlighting via shortcut (in the example below `F2`) add the following to your `vimrc`:

```
nnoremap <F2> :set filetype=thor<CR>
```

## Additional tips

For toggling between wrapped and unwrapped lines add the following to your `vimrc` (example `F6`):

```
nnoremap <F6> :set wrap!<CR>
```

In case of very long lines the highlighting fails because of VIMs default setting.
Change by adding `set synmaxcol=10000` to your `vimrc` or typing `:set synmaxcol=10000` in normal mode.
