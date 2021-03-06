# paper directory

This directory contains all the files necessary to produce a final manuscript. 

When possible, I attempt to write the manuscript in R Markdown. The `main.Rmd` is used to write the main manuscript. I use a custom tex template [adapated from Steven V. Miller](http://svmiller.com/blog/2016/02/svm-r-markdown-manuscript/) to produce the R Markdown in PDF format. You can define a variety of options in the YAML header to get a different look. The template itself contains more details about all of these options. Most importantly, the `anonymous` option can be changed to true to remove author names and change to the crappy double spaced and ragged edged manuscript that most journals expect. You can see a version of what a nicely formatted version of this template looks like [here](http://pages.uoregon.edu/aarong/assets/fullmanuscript.pdf) and a version that has been anonymized [here](http://pages.uoregon.edu/aarong/assets/fullmanuscript_submission.pdf). I also include an MS Word template that can be used to knit to Word when necessary.  

I sometimes just write the manuscript using `main.Rmd`. However, sometimes it is preferable to keep separate Rmd files for tables and figures and any technical appendices. Journals often want tables and figures at the end of the document and sometimes I just don't want my main document to be slowed down by the processing of code. Starter code for these two R Markdown files are also located in this directory. When I do it this way, the three PDFs can be combined together with the `combine_pdfs.py` python script. This will create a `full_manuscript.pdf` file that includes all PDFs. Users will have to have the [PyPDF2 library](https://github.com/mstamy2/PyPDF2) installed in order for this script to work. In order for page numbering to be accurate, the pagenumber variable will also need to be adjusted for the supplementary R Markdown files. 

In order to create tables and figures, I usually just load constructed data from the analysis side of the directory using relative paths from within R Markdown. Something like:

```
load("../../analysis/output/constructed_data.RData")
```

This ensures that the analysis and paper are drawing from the same data source. 

Citation is done using the `project.bib` bibtex file. I usually create this file from Zotero. See [here](http://rmarkdown.rstudio.com/authoring_bibliographies_and_citations.html#bibliography_placement) for information about citation syntax in R Markdown.
