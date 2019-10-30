# Memory Profiling in R
- To check all the memory allocaton use [profmem package](https://cran.r-project.org/web/packages/profmem/vignettes/profmem.html) 
- For profiling use [lineprof package](http://adv-r.had.co.nz/memory.html#gc) 
- To start with use garbage collection `gc()` or `gc(reset = T)`
- `object.size(...)` will give the size of the object

# Packages related to Survey data analysis
- Creating weights based on multiple questions / demographics [anesrake package](https://cran.r-project.org/web/packages/anesrake/index.html) 


# Data Table Cheat Sheets
- Merge tables
  -  merge(x, y, by='common_col') 
  -  merge(x, y, by.x='x_col', by.y='y_col') 
  -  x[y, on='common_col'] 
  -  x[y, on=c(x_col='y_col'] 
