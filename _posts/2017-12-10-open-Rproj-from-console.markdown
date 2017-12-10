---
layout: default
title:  "Using console in R Studio to load project"
comments: true
categories: R Studio R Workspace 
---

People who spend most of their time using console prefer to use keyboard and avoid using mouse. I have been using R Studio for a while and was wondering if their
is a way to load R project using console. I googled a lot for what I was looking and ended up posting it as a question on [R Studio support](https://support.rstudio.com/hc/en-us/community/posts/115009415008-is-it-possible-to-load-Rproj-from-console-). 

The suggested solution is using 

```r
rstudioapi::openProject(path="path/to/project")
```

