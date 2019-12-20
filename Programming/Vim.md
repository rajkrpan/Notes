# Things to learn
  - How to get file path using fuzzy search
  - how to make Netrw not list ignore files
  - how to make fzf serach in MS directory
  - how to make fzf search faster using other searchtype
  - 

# Editing
## General 
  - \t -> tab
  - :retab -> change all tabs to space 
  - set tabstop=2 -> set 2 space for a tab

## Autocompletion
- CTRL X + f -> File name/path
- CTRL n/p   -> To move up and down

## Search/Replace
- :vimgrep /Text/ **/*.java -> Find Text in all (java) files recursively

# Moving around
## Moving in Vim command line
- CTRL + f   -> To edit you command in normal mode
- CTRL + n/p -> To move between recent commands
- CTRL + u   -> Delete upto the begining of line
- CTRL + b   -> Cursor to begining of line
- CTRL + e   -> Cursor to end of line
- q:         -> Open vim window with command history
- q/ or q?   -> Open vim window with search history

# Windows/Tabs/Buffers
## Windows
- :split or :vsplit        -> horizontal or vertical split
- CTRL + w + w             -> Cycle to next window
- CTRL + w + hjkl          -> Go to left,down,up,right window
- CTRL + w + p             -> Go to previous window
- :ZoomToggle or <Leader>z -> Zoom in/out of a window

## Tabs
- :tabnew -> Open file in a tab
- gt      -> Next tab
- gT      -> Prior tab
- {n}gt   -> Numbered tab

## Tools
# Git (vim-fugitive)
- :Gdiff master -> Diff of current file with the one in master branch
- :Gedit branch:/foo/bar.c -> Open file in a different branch
- :Gsplit branc:% -> Open the current file in a different branch
- Add visually selected chunk for commit
  - :Gdiff -> Visual select -> :diffput -> Save index file (you can edit it the you like)


## Buffers
- :bn or :bp -> Move between buffers
- :ls        -> list open buffers
- :b <Tab>   -> cycled through the list of buffers

# File Exploration
## Netrw
- :Explore -> open file explorer
- :Vexplore -> open file explorer in vertical/horizontal window
- :Sexplore -> open file explorer in vertical or horizontal window
- :Texplore -> open file explorer in vertical or horizontal window

## FZF
- :FZF " find file under current directory
- :FZF ~ " find file under HOME directory
- Ctrl + N and Ctrl + P or the arrow key to navigate through the list of files
- <Enter>: open file in current window
- Ctrl + T: open file in new tab page
- Ctrl + X: open file in new horizontal window
- Ctrl + V: open file in new vertical window
- To close the file search window, use Esc or Ctrl+C.
- In Shell CTRL + T search for file
- In Shell OPT + C search for directory
- In Shell CTRL + R history reverse search

# Markers
  - ma -> will create mark with letter a
  - 'a -> jump to mark a (begining of line)
  - \`a -> jump to mark a (exact location) 
  - :marks -> list all the marks
  - mA -> create a global mark

# Macros
  - qa -> start recoding macro in 'a'
  - q -> stop recoding macro
  - @a -> apply macro stored in 'a'

# Tabularize
  - :Tabularize /= -> Aligning text by =
  - :Tabularize -> Reuse last pattern
  - More info [http://vimcasts.org/episodes/aligning-text-with-tabular-vim/]

