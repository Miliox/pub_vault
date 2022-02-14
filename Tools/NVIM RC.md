```vim
" Author: Emiliano Firmino
" Description: neovim configuration

" Space over tabs
set expandtab
set shiftround
set shiftwidth=4
set softtabstop=4
set tabstop=4

set clipboard=unnamed
set nowrap
set relativenumber number
set wildmenu
set wildmode=list:longest,full
set virtualedit=onemore

" Typos
cab W  w
cab Q  q
cab Wq wq
cab wQ wq
cab WQ wq
cab Qa qa
cab qA qa
cab QA qa
cab Wqa wqa
cab wQa wqa
cab wqA wqa
cab WQa wqa
cab wQA wqa
cab WqA wqa
cab WQA wqa

" Unconfortable shift press
nnoremap ; :
nnoremap <Tab> :

" Better hjkl for dvorka
nmap h <Left>
nmap t <Up>
nmap n <Down>
nmap s <Right>

nmap H <Home>
nmap T <PageUp>
nmap N <PageDown>
nmap S <End>

" Escape with ctrl-c
nmap <c-c> <esc>
imap <c-c> <esc>
vmap <c-c> <esc>
omap <c-c> <esc>

" Easier movement over code blocks
vnoremap < <gv
vnoremap > >gv
```