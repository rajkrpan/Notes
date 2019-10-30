# Moving in Vim command line
  - CTRL + f -> To edit you command in normal mode

# Tabularize
  - :Tab /= -> Aligning text by =
  - More info [http://vimcasts.org/episodes/aligning-text-with-tabular-vim/]

# Buffers
  - :bn or :bp -> Move between buffers
  - :ls -> list open buffers
  - :b <Tab> -> cycled through the list of buffers

# FZF
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

# Tabs
  - Open file in a tab
  - Next tab: gt
  - Prior tab: gT
  - Numbered tab: {n}gt

# Markers
  - ma -> will create mark with letter a
  - 'a -> jump to mark a (begining of line)
  - `a` -> jump to mark a (exact location) 
  - :marks -> list all the marks
  - mA -> create a global mark

# Netrw
  - :Explore -> open file explorer
  - :Vexplore or :Sexplore -> open file explorer in vertical or horizontal window

# Macros
  - qa -> start recoding macro in 'a'
  - q -> stop recoding macro
  - @a -> apply macro stored in 'a'

# Windows split
  - :split or :vsplit -> horizontal or vertical split
  - CTRL + w + w -> Cycle to next window
  - CTRL + w + hjkl -> Move to left,down,up,right window
