解决vim+Zathura+vimtex插件 无法反向索引的问题
https://github.com/lervag/vimtex/issues/1921 \
https://github.com/lervag/vimtex/issues/206 \


```
"{{ vimtex

"用于反向索引
Plugin 'lervag/vimtex'
if empty(v:servername) && exists('*remote_startserver')
  call remote_startserver('VIM')
endif

let g:tex_flavor = 'latex'

" use vimtex as default compiler
let g:vimtex_compiler_latexmk_engines={'_':'-xelatex'}
let g:vimtex_compiler_latexrun_engines={'_':'xelatex'}

" use zathura as the default pdf reviewer
let g:vimtex_view_general_viewer = 'zathura'
let g:vimtex_view_method='zathura'

" show the compiler hint(change to 1)using :copen to open complier hint
let g:vimtex_quickfix_mode = 0

" hide the last two lines
set conceallevel=1

let g:tex_conceal='abdmg'
"}}


```

