# Things to learn
  - How to get file path in vim
  - how to use ctrl-n and ctrl-p in command mode so that it use search instead of move between recent commands
  -

# Editing
## Autocompletion

# Moving around
## Moving in Vim command line
  - CTRL + f -> To edit you command in normal mode
  - CTRL + n/p -> To move between recent commands
  - q: -> Open vim window with command history
  - q/ or q? -> Open vim window with search history

# Windows/Tabs/Buffers
## Windows split
  - :split or :vsplit -> horizontal or vertical split
  - CTRL + w + w -> Cycle to next window
  - CTRL + w + hjkl -> Move to left,down,up,right window

## Tabs
  - Open file in a tab
  - gt -> Next tab
  - gT -> Prior tab
  - {n}gt -> Numbered tab

## Buffers
  - :bn or :bp -> Move between buffers
  - :ls -> list open buffers
  - :b <Tab> -> cycled through the list of buffers

# File Exploration
## Netrw
  - :Explore -> open file explorer
  - :Vexplore or :Sexplore -> open file explorer in vertical or horizontal window

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

