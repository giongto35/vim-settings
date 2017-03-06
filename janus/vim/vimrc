execute pathogen#infect()
set nocompatible              " be iMproved, required
filetype off                  " required

set rtp+=~/.vim/bundle/Vundle.vim
set mouse=a
call vundle#begin()
Plugin 'VundleVim/Vundle.vim'
Plugin 'nsf/gocode', {'rtp': 'vim/'}
Bundle 'Blackrush/vim-gocode'
Plugin 'qpkorr/vim-bufkill'
" Python
Plugin 'Vimjas/vim-python-pep8-indent'
Plugin 'Chiel92/vim-autoformat'
Bundle 'Valloric/YouCompleteMe'
Plugin 'scrooloose/syntastic'
Plugin 'nvie/vim-flake8'
Bundle 'jistr/vim-nerdtree-tabs'
Plugin 'mileszs/ack.vim'

call vundle#end()            " required
filetype plugin indent on    " required

""
"" Janus setup
""

" Define paths
if has('win32') || has('win64') || has('win32unix')
  let g:janus_path = expand("~/.vim/janus/vim")
  let g:janus_vim_path = expand("~/.vim/janus/vim")
else
  let g:janus_path = escape(fnamemodify(resolve(expand("<sfile>:p")), ":h"), ' ')
  let g:janus_vim_path = escape(fnamemodify(resolve(expand("<sfile>:p" . "vim")), ":h"), ' ')
endif
let g:janus_custom_path = expand("~/.janus")

" Source janus's core
exe 'source ' . g:janus_vim_path . '/core/before/plugin/janus.vim'

" You should note that groups will be processed by Pathogen in reverse
" order they were added.
call janus#add_group("tools")
call janus#add_group("langs")
call janus#add_group("colors")

""
"" Customisations
""

if filereadable(expand("~/.vimrc.before"))
  source ~/.vimrc.before
endif


" Disable plugins prior to loading pathogen
exe 'source ' . g:janus_vim_path . '/core/plugins.vim'

""
"" Pathogen setup
""

" Load all groups, custom dir, and janus core
call janus#load_pathogen()

" .vimrc.after is loaded after the plugins have loaded
autocmd BufRead,BufNewFile *.xaml :set filetype=xml

let g:jsx_ext_required = 0

noremap <TAB>   <C-W>w

Plugin 'pangloss/vim-javascript'
Plugin 'mxw/vim-jsx'
Plugin 'tmhedberg/SimpylFold'
let g:SimpylFold_docstring_preview=1

set clipboard=unnamedplus
" Enable folding
set foldmethod=indent
set foldlevel=99

vnoremap . :norm.<CR>
nnoremap <space> i<space><esc>
" Python setting
au BufNewFile,BufRead *.py
    \ set tabstop=2 |
    \ set softtabstop=4 |
    \ set shiftwidth=4 |
    \ set textwidth=79 |
    \ set expandtab |
    \ set autoindent |
    \ set fileformat=unix |
Plugin 'vim-scripts/indentpython.vim'
Plugin 'jnurmine/Zenburn'
Plugin 'altercation/vim-colors-solarized'
Plugin 'Lokaltog/powerline', {'rtp': 'powerline/bindings/vim/'}

if has('gui_running')
  set background=dark
  colorscheme solarized
else
  colorscheme zenburn
endif
call togglebg#map("<F5>")

let python_highlight_all=1
syntax on

nmap <S-Enter> O<Esc>
nmap <CR> o<Esc>
nmap <S-H> :tabprev<CR>
nmap <S-L> :tabnext<CR>
let g:ycm_autoclose_preview_window_after_completion=1
map <leader>g  :YcmCompleter GoToDefinitionElseDeclaration<CR>
map <Leader>n <plug>NERDTreeTabsToggle<CR>
map <S-h> :tabp<cr>
map <S-l> :tabn<cr>
