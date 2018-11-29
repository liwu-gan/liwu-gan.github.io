# Event History Modeling

This is the website for the book, Event History Modeling: A Guide for Social Scientists by Janet M. Box-Steffensmeier, Bradford S. Jones, and David Darmofal, which can be located at: liwu-gan.github.io. It replicates tables and figures from the book in both R and Stata. The website was created using the R package, Bookdown (https://bookdown.org/yihui/bookdown/), which is built on top of R Markdown (https://rmarkdown.rstudio.com/). R Markdown files, which have the .rmd extension, allow users to compile html documents for the web. The readme file will explain how to replicate the contents of the website as well as describe each of the files. 

## Getting Started

To replicate the contents of the repository, first download the folder and unzip it. Rename the folder, and make sure to update the working directory within all the files to whatever folder name you chose. The website makes use of R and R Studio, which can be downloaded at https://www.r-project.org/ and https://www.rstudio.com/. To replicate the Stata code in Stata, the user can simply copy and paste the contents of the file into a do file, making sure to get rid of the ``` marks that delineate a code chunk within R Markdown. 

## Files Information
 
The site makes use of a master, or “parent,” .rmd file, within which each of the individual chapters of the book are “child” .rmd files. Each child .rmd file, along with any tables or figures called within the file, are located in the appropriately numbered chapter folder (e.g. chapter 4). When rendering, or knitting, the parent .rmd file, each of the child .rmd files are also knitted, making it seamless to incorporate all the contents. 

The parent .rmd file is event_history.rmd. Within the event_history.rmd file, we can see the top part of the document sets the format for the output, which uses the R package Bookdown. 


```
--- 
title: "Event History Modeling: A Guide for Social Scientists"
author: "Janet M. Box-Steffensmeier, Bradford S. Jones, David Darmofal"
site: bookdown::bookdown_site
output: bookdown::gitbook
documentclass: book
bibliography: [packages.bib]
biblio-style: apalike
link-citations: yes
github-repo: rstudio/bookdown-demo
description: "This is a minimal example of using the bookdown package to write a book. The output format for this example is bookdown::gitbook."
---
```

The title of each chapter is marked by a preceding #. Underneath, each ## indicates the R and Stata code that is replicated. The code is pulled up by calling the child file from the appropriate chapter folder. 

```
This is an example of what a single chapter looks like: 

# The Cox Proportional Hazards Model 

This chapter makes use of the cabinet data used in the previous chapter. 

## Cabinet Data in R

```{r, child = 'chapter4/ch4_cabinet.rmd'}

\```

## Cabinet Data in Stata

```{r, child = 'chapter4/ch4_cabinet_stata.rmd'}

\```

```

Knitting the event_history.rmd file results in the master html file, which I rename to index.html as is customary when using Github Pages. Each of the other html files are the individual chapters that were created as a result of knitting the master file. The dta folder is where all the data files are located. 
