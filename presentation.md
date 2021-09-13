# Data and file management

Robert Turner, University of Sheffield RSE Team
September, 2021

<style>
    .reveal h1 { font-size: 2em; }
</style>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

# Acknowledgements

Contains elements from [Reproducible Research Data and Project Management in R](https://github.com/annakrystalli/rrresearchACCE20), by Anna Krystalli and from [Methods in Research Software Engineering](https://github.com/davidwilby/ResearchSoftwareMethods) by David Wilby.

# About me

![Bob Turner](images/bobicorn.jpg){ height=256px }

Mix of software engineering and research experience.

# RSE Team

![RSE](https://github.com/RSE-Sheffield/RSE-Sheffield.github.io/raw/master/assets/images/logo/rse-logoonly-stroke.png){ height=256px }

13 RSEs, 35 projects / year worth ~£11m total

# This presentation is flawed

Focusses on what to do, not how to do it.

# In this session...


# Data Management

# Data Management Plan

* Start early. [Make an RDM](https://www.sheffield.ac.uk/library/rdm/dmp) plan before collecting data.
* Anticipate data products as part of your thesis outputs.
* Think about what technologies to use.

# Own your data

<blockquote class="twitter-tweet tw-align-center" data-conversation="none" data-lang="en"><p lang="en" dir="ltr">Act as though every short term study will become a long term one <a href="https://twitter.com/tomjwebb?ref_src=twsrc%5Etfw">@tomjwebb</a>. Needs to be reproducible in 3, 20, 100 yrs</p>&mdash; Oceans Initiative (@oceansresearch) <a href="https://twitter.com/oceansresearch/status/556107891610894337?ref_src=twsrc%5Etfw">January 16, 2015</a></blockquote>

Take initiative & responsibility. Think long term.

# Spreadsheets?

<blockquote class="twitter-tweet tw-align-center" data-conversation="none" data-lang="en"><p lang="en" dir="ltr"><a href="https://twitter.com/tomjwebb">@tomjwebb</a> stay away from excel at all costs?</p>&mdash; Timothée Poisot (@tpoi) <a href="https://twitter.com/tpoi/status/556107000950829056">January 16, 2015</a></blockquote>

> Do you agree?

# Excel

<blockquote class="twitter-tweet tw-align-center"><p lang="en" dir="ltr">THRILLED by this announcement by the Human Gene Nomenclature Committee. <a href="https://t.co/BqLIOMm69d">pic.twitter.com/BqLIOMm69d</a></p>&mdash; Janna Hutz (@jannahutz) <a href="https://twitter.com/jannahutz/status/1290666010228514824?ref_src=twsrc%5Etfw">August 4, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
But good for data viewing / entry, sometimes, perhaps...

# Databases

<blockquote class="twitter-tweet tw-align-center" data-conversation="none" data-lang="en"><p lang="en" dir="ltr"><a href="https://twitter.com/tomjwebb">@tomjwebb</a> Entering via a database management system (e.g., Access, Filemaker) can make entry easier &amp; help prevent data entry errors <a href="https://twitter.com/tpoi">@tpoi</a></p>&mdash; Ethan White (@ethanwhite) <a href="https://twitter.com/ethanwhite/status/556119480493813760">January 16, 2015</a></blockquote>

<blockquote class="twitter-tweet tw-align-center" data-conversation="none" data-lang="en"><p lang="en" dir="ltr"><a href="https://twitter.com/ethanwhite">@ethanwhite</a> +1 Enforcing data types, options from selection etc, just some useful things a DB gives you, if you turn them on <a href="https://twitter.com/tomjwebb">@tomjwebb</a> <a href="https://twitter.com/tpoi">@tpoi</a></p>&mdash; Gavin Simpson (@ucfagls) <a href="https://twitter.com/ucfagls/status/556120176748290048">January 16, 2015</a></blockquote>

#

<blockquote class="twitter-tweet tw-align-center" data-conversation="none" data-lang="en"><p lang="en" dir="ltr"><a href="https://twitter.com/tomjwebb">@tomjwebb</a> it also prevents a lot of different bad practices. It is possible to do some of this in Excel. <a href="https://twitter.com/tpoi">@tpoi</a></p>&mdash; Ethan White (@ethanwhite) <a href="https://twitter.com/ethanwhite/status/556119826582605824">January 16, 2015</a></blockquote>
Have a look at the Data Carpentry [**SQL for Ecology** lesson](http://www.datacarpentry.org/sql-ecology-lesson/)

# Data formats

* **`.csv`**: *comma* separated values.
* **`.tsv`**: *tab* separated values.
* **`.txt`**: no formatting specified.

<blockquote class="twitter-tweet tw-align-center" data-conversation="none" data-lang="en"><p lang="en" dir="ltr"><a href="https://twitter.com/tomjwebb">@tomjwebb</a> It has to be interoperability/openness - can I read your data with whatever I use, without having to convert it?</p>&mdash; Paul Swaddle (@paul_swaddle) <a href="https://twitter.com/paul_swaddle/status/556148166270406656">January 16, 2015</a></blockquote>

**more unusual formats will need instructions on use.**

# Ensure data is machine readable

![](images/robot-reading.jpg){ height=256px }

Andrea De Santis, unsplash.com

# bad

<img src="https://raw.githubusercontent.com/annakrystalli/rrresearchACCE20/master/slides/assets/img/bad_xl1.png" width=600px>

# bad

<img src="https://raw.githubusercontent.com/annakrystalli/rrresearchACCE20/master/slides/assets/img/bad_xl2.png" width=600px>

# good

<img src="https://raw.githubusercontent.com/annakrystalli/rrresearchACCE20/master/slides/assets/img/good_xl.png" width=600px>

# ok

<img src="https://raw.githubusercontent.com/annakrystalli/rrresearchACCE20/master/slides/assets/img/ok_xl.png" width=600px>

* could help data entry
* `.csv` or `.tsv` copy would need to be saved.

# Basic quality control

Use good null values, missing values are a fact of life:

* Usually, best solution is to **leave blank**
* **`NA`** or **`NULL`** are also good options
* **NEVER use `0`**. Avoid numbers like **`-999`**
* Don’t make up your own code for missing values

#

<blockquote class="twitter-tweet" data-conversation="none" data-lang="en"><p lang="en" dir="ltr"><a href="https://twitter.com/tomjwebb">@tomjwebb</a> don&#39;t, not even with a barge pole, not for one second, touch or otherwise edit the raw data files. Do any manipulations in script</p>&mdash; Gavin Simpson (@ucfagls) <a href="https://twitter.com/ucfagls/status/556107371634634755">January 16, 2015</a></blockquote>

<blockquote class="twitter-tweet" data-conversation="none" data-lang="en"><p lang="en" dir="ltr"><a href="https://twitter.com/tomjwebb">@tomjwebb</a> <a href="https://twitter.com/srsupp">@srsupp</a> Keep one or a few good master data files (per data collection of interest), and code your formatting with good annotation.</p>&mdash; Desiree Narango (@DLNarango) <a href="https://twitter.com/DLNarango/status/556128407445323778">January 16, 2015</a></blockquote>

# Data security

**Raw data are sacrosanct**

# Give yourself less rope

![](https://raw.githubusercontent.com/annakrystalli/rrresearchACCE20/master/slides/assets/jon-moore-399469-unsplash.jpg){ height=150px }

*Photo by Jon Moore, unsplash.com*

- It's a good idea to **[revoke your own write permission](https://kb.iu.edu/d/abdb) to the raw data file**. Then you **can't accidentally edit it**.
- It also makes it **harder to do manual edits** in a moment of weakness, when you know you should **just add a line to your data cleaning script**.

# Know your main copies 

![](https://raw.githubusercontent.com/annakrystalli/rrresearchACCE20/master/slides/assets/abstract-art-background-270456.jpg){ height=150px }

*Photo: Pexels CC0*

- identify the `main` copy of files
- keep it safe and and accessible
- consider version control
- consider centralising

# How to avoid catastrophes

<blockquote class="twitter-tweet tw-align-center" data-conversation="none" data-lang="en"><p lang="en" dir="ltr"><a href="https://twitter.com/tomjwebb">@tomjwebb</a> Back it up</p>&mdash; Ben Bond-Lamberty (@BenBondLamberty) <a href="https://twitter.com/BenBondLamberty/status/556120946722222080">January 16, 2015</a></blockquote>

# Backup: on disk

- consider using backup software like [Time Machine](https://support.apple.com/en-gb/HT201250) (mac) or [File History](http://www.thundercloud.net/infoave/new/windows-10-has-a-time-machine/) (Windows 10)

# Backup: in the cloud

- dropbox, googledrive etc.
- if [installed](https://tools.google.com/dlpage/drive) on your system, can programmatically access them through `R`
- some version control

# Backup: the Open Science Framework [osf.io](https://osf.io/)

- version controlled
- easily shareable
- works with other apps (eg googledrive, github)

# Backup: Github

- most solid version control.
- keep everything in one project folder.
- Can be problematic with really large files.

# Good File Naming

# Let's face it...

- There are going to be files
- **LOTS** of files
- The files will **change over time**
- The files will **have relationships to each other**

# It'll probably get complicated

![](https://raw.githubusercontent.com/annakrystalli/rrresearchACCE20/master/slides/assets/img/files_messy_tidy.png)

# **File organization** and **naming** is a mighty weapon against chaos

- Make a file's **name** and **location** ***VERY INFORMATIVE*** about:
    - what it is, 
    - why it exists, 
    - how it relates to other things

- The more things are **self-explanatory**, the better.

# What works, what doesn't?

**NO**

~~~
myabstract.docx
Joe’s Filenames Use Spaces and Punctuation.xlsx
figure 1.png
fig 2.png
JW7d^(2sl@deletethisandyourcareerisoverWx2*.txt
~~~

**YES**

~~~
2014-06-08_abstract-for-sla.docx
joes-filenames-are-getting-better.xlsx
fig01_scatterplot-talk-length-vs-interest.png
fig02_histogram-talk-attendance.png
1986-01-28_raw-data-from-challenger-o-rings.txt
~~~

# Question

> What makes a good file name?

# Three principles for good (file) names

1. Machine readable
2. Human readable
3. Play well with default ordering

# Machine readable

- **Regular expression and globbing friendly**
  - Avoid spaces, punctuation, accented characters, case sensitivity

- **Easy to compute on**
  - Deliberate use of delimiters

# Filtering and search through [Globbing](http://searchsecurity.techtarget.com/definition/globbing)

In the following:

```{shell}
ls -lh *Plasmid*
```

```{shell}
*Plasmid*
```

is a **glob**.

# Excerpt of complete file listing

![](https://raw.githubusercontent.com/annakrystalli/rrresearchACCE20/master/slides/assets/img/plasmid_names.png)

# Example of globbing to filter file listing

![](https://raw.githubusercontent.com/annakrystalli/rrresearchACCE20/master/slides/assets/img/plasmid_glob.png)

# Search using Mac OS Finder search facilities

![](https://raw.githubusercontent.com/annakrystalli/rrresearchACCE20/master/slides/assets/img/plasmid_mac_os_search.png){ height=256px }

# Delimit information with punctuation

**Deliberate use of `"-"` and `"_"` allows recovery of metadata from the filenames:**

- `"_"` underscore used to delimit units of metadata I want to access later
- `"-"` hyphen used to delimit words so our eyes don't bleed

![](https://raw.githubusercontent.com/annakrystalli/rrresearchACCE20/master/slides/assets/img/plasmid_delimiters.png)

# Splitting filenames by delimiters

![](https://raw.githubusercontent.com/annakrystalli/rrresearchACCE20/master/slides/assets/img/plasmid_delimiters_code.png)

This happens to be `R` but also possible in the `shell`, `Python`, etc.

# Include important metadata

e.g. I'm saving a number of files of temperature data extracted at different resolutions (`res`) and for a number of months (`month`). Including these parameters in the filename allows me to use them to target files to read in.

```{r}
write.csv(df, paste("variable", res, month, sep ="_"))
df <- read.csv(paste("variable", res, month, sep ="_"))
```

# Recap: machine readable

- Easy to search for files later
- Easy to filter file lists based on names
- Easy to extract info from file names, e.g. by splitting

# New to regular expressions and globbing? be kind to yourself and avoid

- Spaces in file names
- Punctuation
- Accented characters

# Human readable

- Name contains info on content

# Example: Which set of file(name)s do you want at 3 a.m. before a deadline?

![](https://raw.githubusercontent.com/annakrystalli/rrresearchACCE20/master/slides/assets/img/human_readable_not_options.png)

# Embrace the slug

![](https://raw.githubusercontent.com/annakrystalli/rrresearchACCE20/master/slides/assets/img/slug_filenames.png)

# Use slugs to link inputs, scripts & outputs

## The scripts

~~~
01_marshal-data.r
02_pre-dea-filtering.r
03_dea-with-limma-voom.r
04_explore-dea-results.r
90_limma-model-term-name-fiasco.r
~~~

## The figures left behind

~~~
02_pre-dea-filtering-preDE-filtering.png
03-dea-with-limma-voom-voom-plot.png
04_explore-dea-results-focus-term-adjusted-p-values1.png
04_explore-dea-results-focus-term-adjusted-p-values2.png
...
90_limma-model-term-name-fiasco-first-voom.png
90_limma-model-term-name-fiasco-second-voom.png
~~~

# Recap: Human readable

- **Easy to figure out what the heck something is, based on its name**

# Play well with default ordering

- Put something numeric first
- Use the ISO 8601 standard for dates
- Left pad other numbers with zeros

# Examples: **Chronological order** and **Logical order**

# **Chronological order:** Order by date / time

![](https://raw.githubusercontent.com/annakrystalli/rrresearchACCE20/master/slides/assets/img/chronological_order.png)

# Dates

![](https://raw.githubusercontent.com/annakrystalli/rrresearchACCE20/master/slides/assets/img/iso_8601.tiff)

# Dates

Use the **ISO 8601** standard for dates: `YYYY-MM-DD`

![](https://raw.githubusercontent.com/annakrystalli/rrresearchACCE20/master/slides/assets/img/chronological_order.png)

# **Logical order:** Put something numeric first

![](https://raw.githubusercontent.com/annakrystalli/rrresearchACCE20/master/slides/assets/img/logical_order.png)

# Left pad other numbers with zeros


**If you don’t left pad, you get this:**

~~~
10_final-figs-for-publication.R
1_data-cleaning.R
2_fit-model.R
~~~

**which is just sad :(**

# Recap: Play well with default ordering

- Put something numeric first
- Use the **ISO 8601** standard for dates
- Left pad other numbers with zeros


# Recap: Three principles for (file) names

1. Machine readable
2. Human readable
3. Play well with default ordering

**Go forth and use awesome file names :)**
