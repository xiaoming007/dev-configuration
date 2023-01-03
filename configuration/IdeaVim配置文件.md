# IdeaVim
当前所使用ideavim插件的配置如下  
```
""" Common settings -------------------------
" 设置leader键"
let mapleader=" "
"设置vv 为esc键
inoremap vv <esc>

set showmode
" 屏幕滚动时在光标上下方保留5行预览代码
set so=5
" 取消高亮
" 设置寻找高亮
set hlsearch
set incsearch
" 设置字不超过窗口
set wrap
" 突出水平显示
set cursorline
" 下一行和上一行的格式相同
set autoindent
set cindent
" 设置窗口分屏方向
set splitright
set splitbelow
" 不区分大小写
set ignorecase
" 取消高亮
nnoremap <leader>sc :nohlsearch<Cr>
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
""""""""""""""""""""""""""""UI"""""""""""""""""""""""""""""""
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" change colorscheme
nnoremap <leader>fc :action QuickChangeScheme<CR>
" 改变视图
nnoremap <leader>cv :action ChangeView<CR>
set nu
" 防止按leader键乱移动
nnoremap <SPACE> <nop>
set number
"set relativenumber
""" Idea specific settings ------------------
"set ideajoin
"set ideastatusicon=gray

"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
""""""""""""""""""""""""Plugins""""""""""""""""""""""""""""""
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
set surround
set multiple-cursors
set commentary "能用gcc gc+motion来注释代码
"set argtextobj
set easymotion
set textobj-entire
set ReplaceWithRegister
set exchange
set NERDTree
set highlightedyank
""" Strict mode for development ---------------
set ideastrictmode
set keep-english-in-normal-and-restore-in-insert
""" Plugin settings -------------------------
let g:argtextobj_pairs="[:],(:),<:>"

" <C-n> seems to me as a better solution than <M-n>,
" but we should finally support vim-visual-multi because vim-multiple-cursors is deprecated now
map <C-n> <Plug>NextWholeOccurrence

" ===
" === NERDTree
" ===
""""Usage""""
" o <key> open menu in NERDTree
" O <key> Recursively open the selected directory
" i <key> Open selected file in a split window (horizontal)
" gi <key> Same as i, but leave the cursor on the NERDTree
" s <key> Open selected file in a new vsplit
" gs <key> Same as s, but leave the cursor on the NERDTree
" m <key> open menu in NERDTree
" A <key> Zoom (maximize/minimize) the NERDTree window"
" K <key> Jump up inside directories at the current tree depth
" J <key> Jump down inside directories at the current tree depth
" x <key> Close the current nodes parent (not close flie)
" X <key> Recursively close all children of the current node (not close flie)
""""End""""
" open NERDTree
nnoremap <leader>e :NERDTree<CR>
" ===
" === AceJump
" ===
" Press `f` to activate AceJump
map f :action AceAction<CR>
" Press `F` to activate Target Mode
map F :action AceTargetAction<CR>



" 取消vim s键原生映射
nnoremap s <Nop>
vnoremap s <Nop>
" 快速关闭buffers
nnoremap X :q<cr>
" 使用tab键快速切换buffers
nnoremap <TAB> gt
nnoremap <S-TAB> gT
vnoremap <TAB> gt
vnoremap <S-TAB> gT
" 左右移动视野
nnoremap zh 50zh
nnoremap zl 50zl
" 像vscode一样行移动
vnoremap J :action MoveLineDown<CR>
vnoremap K :action MoveLineUp<CR>
" 多行缩进在visual mode
vnoremap > >gv
vnoremap < <gv
" 复制粘贴剪贴板
nnoremap <leader>y "+y
nnoremap <leader>p "+p
nnoremap <leader>P "+P
vnoremap <leader>y "+y
vnoremap <leader>p "+p
vnoremap <leader>P "+p
" 快速复制到行尾
vnoremap Y y$
nnoremap Y y$
" 插入模式快速移动
inoremap <C-a> <Home>
inoremap <C-e> <End>
" 其他模式快速移动
nnoremap H ^
nnoremap L $
vnoremap H ^
vnoremap L $
" 后退功能
nnoremap <leader>gb :action Back<CR>
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
""""""""""""""""""""""""Debug""""""""""""""""""""""""""""""""
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" 打上断点或取消断点
nnoremap <leader>dt :action ToggleLineBreakpoint<CR>
" 取消所有的断点
nnoremap <leader>dT :action Debugger.RemoveAllBreakpointsInFile<CR>
" debug上次运行的类
nnoremap <leader>dd :action Debug<CR>
" debug当前(now)类
nnoremap <leader>dc :action DebugClass<CR>
" debug神器
" StepInto (F7)
nnoremap <leader>di :action ForceStepInto<CR>
" ForceStepInto(CMD + SHIFT + F7)
nnoremap <leader>dI :action ForceStepInto
" StepOver (F8)
nnoremap <leader>do :action StepOver<CR>
" Resume (跳到下个断点运行)
nnoremap <leader>dr :action Resume<CR>
" StepOut (SHIFT+F8)
nnoremap <leader>du :action StepOut<CR>
" debug强制运行到光标处
nnoremap <leader>dC :action ForceRunToCursor<CR>
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
""""""""""""""""""""""""""""Create"""""""""""""""""""""""""""
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" 新建类
nnoremap <leader>nc :action NewClass<CR>
" 新建项目
nnoremap <leader>np :action NewProject<CR>
" 新建文件 (嘻嘻,啥都可以直接用快捷键建立,一个字爽)
nnoremap <leader>ne :action NewElement<CR>
" 删除当前文件 (快速删除)
nnoremap <leader>nd :action SafeDelete<CR>
" 复制文件元素
nnoremap <leader>ny :action CopyElement<CR>
" 代码环绕(快速添加if 或者while)
nnoremap <leader>ns :action SurroundWith<CR>
vnoremap <leader>ns :action SurroundWith<CR>
" 将选中的代码生成方法
nnoremap <Leader>nf :action ExtractMethod<CR>



""" My Mappings -----------------------------

"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
""""""""""""""""""""""""""""跳转"""""""""""""""""""""""""""
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
"跳转到Action
nnoremap <Leader>ga :action GotoAction<CR>

"跳转到实体类
nnoremap <Leader>gc :action GotoClass<CR>
"跳转到声明
nnoremap <Leader>gd :action GotoDeclaration<CR>

"跳转到文件
nnoremap <Leader>gf :action GotoFile<CR>
"跳转到实现类
nnoremap <Leader>gi :action GotoImplementation<CR>

"跳转到错误
map <leader>ge <Action>(GotoNextError)

" project search 相当于IDEA的两次shift按钮
nnoremap <Leader>se :action SearchEverywhere<CR>
nnoremap <Leader>fp :action FindInPath<CR>
"查找用法
nnoremap <Leader>fu :action FindUsages<CR>


"显示当前文件路径
nnoremap <Leader>sp :action ShowFilePath<CR>

"修改所有的关联名字
nnoremap <Leader>re :action RenameElement<CR>

"修改当前文件的文件名
nnoremap <Leader>rf :action RenameFile<CR>
"显示使用
nnoremap <Leader>su :action ShowUsages<CR>
"清理不用的import
nnoremap <Leader>oi :action OptimizeImports<CR>



"关闭活动显示板
nnoremap <Leader>tc :action CloseActiveTab<CR>
"clean project
nnoremap <Leader>cp :action CleanGradleProject<CR>

map <leader>rd <Action>(Debug)
map <leader>st <Action>(StopBackgroundProcesses)
map <leader>rp <Action>(Run)
map <leader>z <Action>(ToggleDistractionFreeMode)
map <leader>rc <Action>(ReformatCode)

map <leader>sp <Action>(SelectInProjectView)
map <leader>a <Action>(Annotate)
map <leader>h <Action>(Vcs.ShowTabbedFileHistory)

" built in search looks better
" (查找字符串)
nnoremap / :action Find<CR>

"翻译单词
nnoremap <Leader>tw :action Translate<CR>
```
