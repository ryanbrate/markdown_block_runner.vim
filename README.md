# vimwiki\_block\_runner.vim

A plugin to evaluate a code block defined within a markdown file, appending the printed output immediately after the codeblock 

## Example

With cursor (anywhere) within the code block, run *:call Execute_Block()*

```
\```python


\```
--> The block output is appended immediately after the block
```

## Installation

E.g., using [vim-plug](https://github.com/junegunn/vim-plug)

```
Plug 'ryanbrate/functional.vim'
Plug 'ryanbrate/markdown_block_runner.vim'
```

## set vimrc variables

1. Define 'block labels':'block run commands' pairs in g:mdbr\_commands.

E.g.
```
let g:mdbr_commands = {
    \'python':'python3 %s',
    \}
```

Where *%s* denotes the code block to be executed

2. Shortcut mapping to execute a block (optional)

```
augroup FileType markdown
    au! 
    au Filetype markdown nnoremap <buffer> <Leader>wb call Execute_Block()
augroup END
```
