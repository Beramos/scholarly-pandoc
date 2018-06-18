# README
This is my setup for rich scholarly markdown.

## Disclaimer
Most of the templates and scripts are developed or inspired by others. I've only made minor changes to tailor the style to my own preferences. This is scholarly markdown is currently work-in-progress.

## Installation
* Clone this repository.
* Install the dependencies:
    * Texlive full package:`sudo apt-get install texlive-full`
* If it does not exist create ~/.pandoc directory
* Copy all the right files to all the right places

```bash
cp -r templates ~/.pandoc/.
cp -r csl ~/.pandoc/.
cp -r css ~/.pandoc/.
```
* There are some additional tex dependencies (*memoir-article-styles.sty*,org-preamble-pdflatex.sty) you can either keep them in the same directory as the markdown input files. Or you can place them in the general tex folder (for me this is ~/.texmf/)
* [*Pandoc-crossref*](https://github.com/lierdakil/pandoc-crossref) package is used which combined fignos, eqnos, etc. into one package. Installing this package was a quite a hassle. Check your pandoc version `pandoc -v` and [download](https://github.com/lierdakil/pandoc-crossref/releases) the respective crossref release version. In the pandoc commands, point to the right location on your computer with the filter flag `--filter yourPath/pandoc-crossref`

## Usage
* Go to the example directory and run `make` to build the *.docx .tex .pdf* files from *template.md* 
* Use `make clean` to clean the directory
* This setup works perfectly with atom's [markdown preview enhanced package](https://github.com/shd101wyy/markdown-preview-enhanced).
	* Select *'use Pandoc Parser'*
	* Set pandoc path (usually */usr/bin/pandoc*)
	* Set the command line arguments: `--template=/home/name/.pandoc/templates/html.template, --filter=/home/name/.pandoc/filters/pandoc-crossref, --filter=pandoc-citeproc, --bibliography=/path/libraryName.bib,--csl=/home/name/.pandoc/csl/apsa.csl`
	* Set the pandoc options: `markdown+simple_tables+table_captions+yaml_metadata_block`

## Credits
I've got most of the material from [Kieran Healy's setup](https://github.com/pandoc-scholar/pandoc-scholar):

**Changes:**
* removed VC package
* removed proprietary font minonPro from the tex templates
* changes to css stylesheets
* addition of pandoc-crossref package
