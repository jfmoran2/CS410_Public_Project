# Holy Book Similarity Analysis

## CS410 Text Information Systems, Final Project, Fall 2018

Click here to start docker container at [mybinder](https://mybinder.org/v2/gh/jfmoran2/CS410_Public_Project/master)

For browsing (rather than the interactive notebook in mybinder) the main notebook is holybooks.ipynb, and the PDF equivalent is holybooks.pdf

### Authors

Graham Chester - grahamc2: Division of Labour, 50% share: text processing, LDA, t-SNE coding, documentation, voiceover

John Moran - jfmoran2: Division of Labour, 50% share: sourcing, cleaning, preprocessing data, documentation, voiceover, mybinder setup, repo management.

## Functionality Overview

This Jupyter notebook tool was developed to enable the visualisation of similarities and differences of the major texts from many of the worlds largest religions. It also includes non-religious works from approximately similar periods (of translation) as a benchmark. While the tool is focused on religious works, it is general enough to be applied to be used to visualize the comparison of books from any genre.

The tool, as supplied, consists of a Jupyter notebook and the raw texts downloaded from the websites below. It requires the installation of a fairly standard Python data science stack as described in the installation section below.

### Data Sources

All books were sourced from open data sites in accordance with their licensing terms, as follows:

* Christianity: 2.2 billion followers, [King James Bible](http://www.o-bible.com/dlb.html)
* Islam: 1.6 billion followers, [Quran](http://tanzil.net/trans/) (Yusuf Ali version)
* Hinduism: 1 billion followers, [Bhagavad Gita](https://www.holybooks.com/bhagavad-gita-three-modern-translations/)
* Buddhism: 380 million followers, [Tipitaka](https://www.accesstoinsight.org/tech/download/bulk.html)
* Mormonism: 15 million followers, [Book of Mormon](http://holybooks.com/wp-content/uploads/2010/05/Book-of-Mormon.txt)
* Judaism: 14 million followers, [Torah](http://www.mechon-mamre.org/htmlzips/et002.zip)
* Shakespeare [collection](http://www.gutenberg.org/ebooks/author/65)
* Jane Austen [collecton](http://www.gutenberg.org/ebooks/search/?query=Jane+Austen)

## Installation

### Option 1: Cloud

There are two options for installation. The first and simplest isn't really installation at all. The Jupyter notebook can be started directly from [mybinder](https://mybinder.org/v2/gh/jfmoran2/CS410_Public_Project/master). It will take several minutes to start as it copies across file from this github [repo](https://github.com/jfmoran2/CS410_Public_Project), then builds and starts a docker container with the Python required libraries, but in the meantime you can browse the notebook itself.

### Option 2: Local Machine

This Jupyter notebook is built on a reasonably standard Python Data Science stack. Perhaps the easiest to install the prerequisites, if they are not already on your Windows, Mac or Linux machine, is to download and install Anaconda (Python version 3) from [here](https://www.anaconda.com/download), and then "conda install nltk", or refer to the official [NLTK website](http://www.nltk.org/install.html)

If you have an existing Python 3.5 or above installation and don't wish to install Anaconda, you can do the following, but you may need to be careful with versions:

```Python
pip install numpy scipy matplotlib pandas scikit-learn jupyter nltk
```

You will then need to clone or download the GitHub repo from [here](https://github.com/jfmoran2/CS410_Public_Project). This contains the Jupyter notebook, and the raw religious texts in a directory called 'books-raw'.

At a terminal/command line window you then type 'jupyter notebook' in the directory that contains the notebook and books-raw directory. This will start the notebook server at port 8888 on your local machine and open a browser window. If you have any problems check this [quickstart guide](https://jupyter.readthedocs.io/en/latest/content-quickstart.html)

## Usage

Clicking on holybook.ipynb in the Jupyter notebook file browser window will open this notebook, and putting your cursor in a cell clicking on ">| Run" will run the cell. The processing steps in this notebook are:

1) **Load libraries**, initialize display options, download stopwords

2) **Define utility functions** for displaying similarity map, displaying topic words, and filtering text.

3) **Text Cleaning:** Sections to clean each book by reading the raw text from file(s) in the "books-raw" directory and creating a cleaned file in the 'books' directory. In the case of the old and new testament, a clean file is created for each chapter.

4) **Text Processing:** Stopword removal, stemming and lemmatization

5) **Word Count Vectorisation** using TFIDF

6) **Topic Discovery** using LDA

7) **t-SNE** based similarity mapping

8) **MDS** based similarity mapping
