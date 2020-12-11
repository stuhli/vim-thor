# VIM syntax file for THOR

A [VIM](https://www.vim.org/) syntax file for log files of [APT Scanner THOR](https://www.nextron-systems.com/thor/).

![Example 1](docs/example_1.png)

## Installation

Place the file `thor.vim` in `$HOME/.vim/syntax/thor.vim`.

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

### Readability

For toggling between wrapped and unwrapped lines add the following to your `vimrc` (example `F6`):

```
nnoremap <F6> :set wrap!<CR>
```

But readability is even better if you are able to split lines.
The following code snippet in your `vimrc` splits the actual line by a push of a button (example `F7`) and jumps to the beginning of the entry.
In order to avoid accidental changes, the file is previously set in a read-only mode.

```
nnoremap <F7> :set ro <bar> :s/\S\+:\ /\r\0/g <bar> noh <bar> ?^THOR:\ <CR> :noh <CR> k
```

The result looks like this:

![Example 2](docs/example_2.png)

If you still want to save the changed file, you can do this with `:w!` anyway.

### Highlighting not applied to the end of the line

In case of very long lines the highlighting fails because of VIMs default setting.
Change by adding `set synmaxcol=10000` to your `vimrc` or typing `:set synmaxcol=10000` in normal mode.
