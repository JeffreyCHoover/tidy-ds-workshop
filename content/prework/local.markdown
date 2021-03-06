---
title: Local setup
author: ''
date: "2019-04-02"
slug: local
categories: []
tags: []
linktitle: "Local setup"
menu:
  prework:
    name: "Local setup"
    weight: 3
toc: yes
type: docs
---



## What do I need to do before the workshop?

You'll need to follow these setup instructions:

1. [Install/upgrade software](#system)
1. [Install R packages](#packages)
1. [Install Git & GitHub](#github) (optional)

In this workshop, we will use R and [RStudio](https://www.rstudio.com/products/rstudio/). RStudio is not required but recommended, because it makes it easier for an average user to work with R. If you choose not to use the RStudio IDE, you will have to install Pandoc (http://pandoc.org), otherwise there is no need to install Pandoc separately because RStudio has bundled it. 

-----

## Install/upgrade software {#system}

### Install R

* A [recent version of R](https://cran.rstudio.com/) (>= 3.5.1 "Feather Spray") is recommended. You can check your version from the R Console:


```r
R.version.string
```


### Install RStudio

* [RStudio](https://www.rstudio.com/products/rstudio/download/#download) (>= 1.1.463)  is recommended.


### Upgrading your system

For more help installing or upgrading R and RStudio, please read through these links:

1. [Chapter 6 in **Happy Git with R**](http://happygitwithr.com/install-r-rstudio.html)
1. [Maintaining R from **What They Forgot to Teach You About R**](https://whattheyforgot.org/maintaining-r.html)
    - See ["How to transfer your library when updating R"](https://whattheyforgot.org/maintaining-r.html#how-to-transfer-your-library-when-updating-r)

-----

## Install R packages {#packages}

There are to possible methods for installing the necessary packages:

* [Install the companion package](#companion)
* [Install packages individually](#ind-install)

### tidydscompanion {#companion}

You can download our workshop companion package from GitHub:


```r
install.packages("remotes")
remotes::install_github("wjakethompson/tidydscompanion", dependencies = TRUE)
```

Can you load the package?


```r
# should just work if installed
library(tidydscompanion)
```

Proceed to [installing Hugo](#install-hugo).

### Individual package installation {#ind-install}

For this workshop, you'll need to install several R packages. This section will guide you through installing the packages we will use. If you are comfortable installing packages in R, then you could run this code from your R console to install all of the necessary packages:


```r
from_cran <- c("tidyverse", "rmarkdown", "bookdown", "blogdown",
               "fivethirtyeight", "babynames")
from_gh <- c("apreshill/bakeoff")
```


```r
install.packages(from_cran, dependencies = TRUE)

# install.packages("remotes")
remotes::install_github(from_gh, dependencies = TRUE)
```

Proceed to [installing Hugo](#install-hugo).

### Install Hugo {#install-hugo}

Hugo (https://gohugo.io) is the static site generator on which **blogdown** is based. You must install Hugo in order to build a site using the **blogdown** package. You may install Hugo using the **blogdown** package helper function in your R Console:


```r
blogdown::install_hugo()
```

#### Update Hugo (if necessary) {#update-hugo}

In your R Console, please do the following to make sure that you are working with the latest version of Hugo (>= 0.54.0): 
    

```r
blogdown::hugo_version() # to check your version
blogdown::update_hugo() # to force an update
```


### Download script {#script}

Click <a href="../tidy-ds-installs.R" download>here</a> to download an R script for installing all the necessary packages.

-----

## Install Git & GitHub {#github}

Although version control will not be explicitly covered in this workshop, it is highly recommended. It not only allows you to keep track of when and why changes were made to a file, but also provides an easy method for sharing your code. If you would like to use GitHub during the workshop, please follow the steps below from the online book [Happy Git with R](https://happygitwithr.com/):

### Installation

1. [Register a GitHub account](https://happygitwithr.com/github-acct.html)
1. [Install Git](https://happygitwithr.com/install-git.html) 
1. [Introduce yourself to Git](https://happygitwithr.com/hello-git.html)

### Connect Git, GitHub, RStudio

1. [Connect to GitHub](https://happygitwithr.com/push-pull-github.html)
1. Do one of the following:
    - [Cache credentials for HTTPS](https://happygitwithr.com/credential-caching.html)
    - [Set up keys for SSH](https://happygitwithr.com/ssh-keys.html)
1. [Connect RStudio to Git and GitHub](https://happygitwithr.com/rstudio-git-github.html)

### Test-drive

We encourage you to follow a ["New project, GitHub first" workflow](https://happygitwithr.com/new-github-first.html). This means that if you want to work locally, you'll want to be comfortable doing the following steps:

1. [Make a repo on GitHub](https://happygitwithr.com/new-github-first.html#make-a-repo-on-github-1)
1. [Make a new RStudio project via git clone](https://happygitwithr.com/new-github-first.html#new-rstudio-project-via-git-clone)
1. [Make local changes, save, commit](https://happygitwithr.com/new-github-first.html#make-local-changes-save-commit-1)
1. [Push your local changes to GitHub](https://happygitwithr.com/new-github-first.html#push-your-local-changes-to-github)
