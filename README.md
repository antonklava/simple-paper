# simple-paper

simple-paper is a script that creates a PDF from a set of markdown files. It's
accomplished using [Pandoc](http://pandoc.org/). Pandoc is great and very
flexible, but that flexibility requires some configuration. simple-paper makes
some assumptions about your configuration to let you start writing quickly.

Most markdown extensions from pandoc are enabled and simple-paper should work
fine for many academic papers. Details can be found in the [Pandoc user
guide](http://pandoc.org/README.html#pandocs-markdown). Extensions include:

* BibTeX bibliography
* Figures
* Footnotes
* Latex Math
* List of references
* Multiple citation formats with custom CSL
* Pictures
* Table of contents

[boilerplate.pdf](boilerplate.pdf) was created using simple-paper, see
[boilerplate/](boilerplate/1-introduction.md) for source.

## Installing and updating

For simple-paper to work make sure you meet it's [prerequisits](#prerequisits).
To install you just need to paste the line below. It will download simple-paper
to `/usr/local/bin/simple-paper` and make it executable.

```bash
curl -O https://raw.githubusercontent.com/antonklava/simple-paper/master/simple-paper && sudo mv simple-paper /usr/local/bin/ && sudo chmod +x /usr/local/bin/simple-paper
```

## New paper

Once you have simple-paper installed you can run the command below to setup a
new paper from the boilerplate. This will download and unpack a zip-file from
Github containing the boilerplate contents.

```bash
simple-paper new my-thesis # new from boilerplate
cd my-thesis
simple-paper # creates my-thesis.pdf
```

## Ordering chapters

simple-paper will use all files ending in `.md` as part of the document,
including in subdirectories. They are then ordered, so it's preferable to name
your files `1-introduction.md`, `2-background.md` etc.

If a chapter is too big for a single file you can create a directory and name
your files `1-introduction/1-abbreviations.md`,
`1-introduction/2-background.md` and so on.

## Prerequisits

You need panodc and [Pandoc](http://pandoc.org/),
[Pandoc-citeproc](https://github.com/jgm/pandoc-citeproc) and some latex engine
installed.


### OS X

Assuming you have [Homebrew](http://brew.sh/), installing this on OS X can look
like this:

```bash
brew update
brew install pandoc pandoc-citeproc
brew cask install mactex
```

You may have to update your `$PATH` to find the latex binaries (I had to add
`/usr/local/texlive/2015/bin/x86_64-darwin`).

### Debian/Ubuntu

The full TeX install is huge (3GB) so make sure you dont run this on a too
small vm. Apt will probably get you a pretty old version of pandoc so it's
preferable to install from a .deb directly.

```bash
sudo apt-get install texlive-full
curl -O https://github.com/jgm/pandoc/releases/download/1.16.0.2/pandoc-1.16.0.2-1-amd64.deb
sudo dpkg -i pandoc-1.16.0.2-1-amd64.deb
```

## Acknowledgements

Cat picture in boilerplate by Henry Riley, https://flic.kr/p/u98GdN
