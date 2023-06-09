---
title: Setup
---
# Synapse Setup

To participate in this workshop, you will need to have a [registered Synapse account](https://www.synapse.org) and accept the AD Knowledge Portal data terms of use.

1. If you have successfully created a Synapse account and are logged into Synapse, you should be able to view and download this file: <https://www.synapse.org/#!Synapse:syn26200396>
2. If you have successfully accepted the AD Portal terms of use, you should be able to view and download this file: <https://www.synapse.org/#!Synapse:syn22103212>

If you can access the first file, but not the second, click on the "Request Access" link next to the yellow lock icon and accept the AD Portal terms of use. Refresh the page, and you should be able to access the second file.

# Software Installation

Installing the software may take up to 30 minutes. You may also need to contact 
your local Information Technology Help Desk to get permission or assistance 
installing the software. 
Please do this **before the workshop**. We will not delay the start of the 
course while you install software. We *will* help you in advance to make sure 
that you have everything that you need.

If you do not already have `R` and `RStudio` installed, 
download and install the following software:

1. [R/4.3.0](https://cran.r-project.org/): Select the installation for your 
operating system (Windows, Mac, or Linux).
1. [RStudio](https://www.rstudio.com/products/rstudio/download/): Download the 
free **Rstudio Desktop**. 

You do not need to install this *exact* version of `R`, but it would be good to
make sure your `R` is relatively recent (say, updated within the past year).

Once you have installed `R` and `RStudio`, open `RStudio` to verify that the 
installation was successful.

# R Library Installation

In RStudio, copy and paste the following commands into the Console:

~~~
# install synapser
install.packages("synapser", repos = c("http://ran.synapse.org", "http://cran.fhcrc.org"))

# install other required packages
install.packages(c("tidyverse", "cowplot"), dependencies = TRUE)
~~~
{: .r}

We will also use the BioconductoR package manager to install specific packages. 
                   
~~~                   
if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")
    
BiocManager::install(c("biomaRt", "AnnotationDbi", "GO.db", "org.Mm.eg.db", "org.Hs.eg.db", "clusterProfiler", "DESeq2", "EnhancedVolcano"))
~~~
{: .r}

Once the installation has finished, copy and paste the following commands into 
the console to verify that all packages installed correctly.

~~~
library(tidyverse)
library(cowplot)
library(EnhancedVolcano)
library(biomaRt)
library(AnnotationDbi)
library(tidyverse)
library(GO.db)
library(org.Mm.eg.db)
library(org.Hs.eg.db)
library(clusterProfiler)
library(DESeq2)
library(EnhancedVolcano)
~~~
{: .r}

## Project Setup

1. Create a new project called `omicsAD`. 
    - Click the `File` menu button, then `New Project`.
    - Click `New Directory`. 
    - Click `New Project`.
    - Type `omicsAD` as the directory name. Create the project anywhere you like,
      but don't forget where you put it!
    - Click the `Create Project` button.
    This will create a file called `omicsAD.Rproj` in the directory you just 
    created. In the future you can double-click on this file to open 
    `RStudio` in this directory. This will be the easiest way to interact
    with the files/code you produce in this workshop.

2. Use the `Files` tab to create  a `data` folder to hold the data, a `scripts` 
folder to house your scripts, a `results` folder to hold results, and a doc folder to hold project-related documents. 
Alternatively, you can copy and paste the following commands into the `R` 
console for step 2 only. You still need to create a project with step 1.

~~~
dir.create("data")
dir.create("scripts")
dir.create("results")
dir.create("doc")
~~~
{: .r}

{% include links.md %}
