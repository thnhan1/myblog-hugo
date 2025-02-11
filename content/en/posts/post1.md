+++
date = '2025-01-04T23:13:19+07:00'
draft = true
title = 'nvim config for golang dev'
tags = ['nvim', 'golang', 'dotfiles']
categories = ['nvim', 'golang', 'dotfiles']
+++

# nvim config file

```vim
" Specify a directory for plugins
call plug#begin('~/.vim/plugged')

" Plugin manager
Plug 'junegunn/vim-plug'

" Syntax highlighting
" Plug 'sheerun/vim-polyglot'
Plug 'nvim-treesitter/nvim-treesitter', {'do': ':TSUpdate'}
"File explorer tree
Plug 'preservim/nerdtree'

" Status line
Plug 'vim-airline/vim-airline'
Plug 'vim-airline/vim-airline-themes'

" Go development
Plug 'fatih/vim-go', { 'do': ':GoUpdateBinaries' }

" Autocompletion
Plug 'neoclide/coc.nvim', {'branch': 'release'}

" Documentation
Plug 'kkoomen/vim-doge', { 'do': ':call doge#install()' }

" Auto pairs for brackets and quotes
Plug 'jiangmiao/auto-pairs'

" Fuzzy file finder
Plug 'junegunn/fzf'
Plug 'junegunn/fzf.vim'

" Xcode theme
Plug 'nomis51/nvim-xcode-theme'

" File icons
Plug 'ryanoasis/vim-devicons'
Plug 'preservim/nerdtree', { 'on':  'NERDTreeToggle' }
Plug 'tiagofumo/vim-nerdtree-syntax-highlight'

" Initialize plugin system
call plug#end()

" Enable line numbers
set number 
" Enable relative line numbers
set relativenumber
set termguicolors
" Enable syntax highlighting
syntax enable
syntax on
let mapleader=","
" Set colorscheme

colorscheme xcode
" Set airline theme
let g:airline_theme='xcode'


let g:signify_sign_add    = '┃'
let g:signify_sign_change = '┃'
let g:signify_sign_delete = '•'

let g:signify_sign_show_count = 0 " Don’t show the number of deleted lines.

" NERDTree settings
map <C-n> :NERDTreeToggle<CR>
let NERDTreeShowHidden=1

" Enable file icons in NERDTree
let g:WebDevIconsUnicodeDecorateFolderNodes = 1

" CoC settings
let g:coc_global_extensions = ['coc-go', 'coc-json', 'coc-html', 'coc-css']

" Go settings
let g:go_fmt_command = "goimports"
let g:go_auto_type_info = 1

" Doge settings
let g:doge_doc_standard_python = 'google'

" Auto pairs settings (for automatically closing brackets and quotes)
let g:AutoPairsMapBS = 1
set t_Co=256
" Key mappings
nnoremap <C-p> :Files<CR> " Open file search
nnoremap <C-f> :Rg<CR> " Open search
nnoremap <C-t> :NERDTreeToggle<CR> " Toggle NERDTree
nnoremap <C-e> :CocCommand explorer<CR> " Open CoC explorer

" Keymap summary function
function! ShowKeymapSummary()
  echo "Keymap Summary:"
  echo "Ctrl + p: Open file search"
  echo "Ctrl + f: Open search"
  echo "Ctrl + t: Toggle NERDTree"
  echo "Ctrl + e: Open CoC explorer"
  echo "Ctrl + n: NERDTree toggle"
  echo "Ctrl + ]: Jump to the definition under the cursor"
  echo "Ctrl + d: Show documentation for the symbol under the cursor"
  echo "Ctrl + k: Show keymap summary"
  echo "Ctrl + w + t: Open a new tab"
  echo "Ctrl + w + h: Move to the left tab"
  echo "Ctrl + w + l: Move to the right tab"
endfunction

" Add keymap to show the summary
nnoremap <leader>ks :call ShowKeymapSummary()<CR>

" Additional keymaps for code navigation and documentation
nnoremap <C-]> :call CocAction('jumpDefinition')<CR> " Jump to definition
nnoremap <C-d> :call CocAction('doHover')<CR> " Show documentation

" FZF settings
let g:fzf_layout = { 'down': '~40%' }
nnoremap <C-p> :Files<CR> " Open file search
nnoremap <C-f> :Rg<CR> " Open search

" Keymaps for tab management
nnoremap <C-w>t :tabnew<CR> " Open a new tab
nnoremap <C-w>h :tabprevious<CR> " Move to the left tab
nnoremap <C-w>l :tabnext<CR> " Move to the right tab


lua << EOF
require'nvim-treesitter.configs'.setup {
  highlight = {
    enable = true,
    additional_vim_regex_highlighting = false,
  },
}
EOF
```

then `PlugInstall`