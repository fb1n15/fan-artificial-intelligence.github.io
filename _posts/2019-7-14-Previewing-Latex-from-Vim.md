dependencies: [Latex-Suite (Vim Latex)](http://vim-latex.sourceforge.net/index.php?subject=manual&title=Tutorial#tutorial), and [Skim PDF reader](https://skim-app.sourceforge.io/)

According to the documentation, compiling via latex-suite is by pressing `\ll`. However, it does not always work for my latex files. This is how I circumvent this problem. I remap key `<F6>` to save the file and compiling it:

```
nnoremap <F6> :w <bar> silent !pdflatex -synctex=1 -interaction=nonstopmode %<CR> 
```


Before we viewing the pdf file, we need to write the following commands to `~/.vimrc`

```
let g:livepreview_previewer = 'open -a Skim -synctex=1'
let g:Tex_CompileRule_pdf = 'pdflatex --synctex=-1 -src-specials -interaction=nonstopmode -file-line-error-style $*'
```

Then, you can view the pdf file by pressing `\lv`, or forward search the place (i.e., jump to the place in pdf as the place you are editting) by pressing `\ls`. You can also do inverse search by clicking the pdf file with some keys pressed. You can find the key combinations in the perference of Skim, my key combination for inverse search is `command+shift+click`. 
