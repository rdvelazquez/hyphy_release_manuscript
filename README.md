# HyPhy - Title TBD

[![HTML Manuscript](https://img.shields.io/badge/manuscript-HTML-blue.svg)](https://rdvelazquez.github.io/hyphy_release_manuscript/)
[![PDF Manuscript](https://img.shields.io/badge/manuscript-PDF-blue.svg)](https://rdvelazquez.github.io/hyphy_release_manuscript/manuscript.pdf)
[![Build Status](https://travis-ci.com/rdvelazquez/hyphy_release_manuscript.svg?branch=master)](https://travis-ci.com/rdvelazquez/hyphy_release_manuscript)

## Manuscript description

<!-- usage note: edit this section. -->

This is an initial, __rough__, working draft of the HyPhy release note for testing out manubot.

### Converting to LaTeX
requires pan-doc `pip install pandoc`  
`sh build/build.sh` to build the html, md and pdf documents and the references.json in the output dir  
`cd output`  
`pandoc manuscript.md -f markdown -t latex -s -o manuscript.tex` creates a LaTeX version of the manuscript  
{need to document how to convert the references to .bib format}

## Manubot

<!-- usage note: do not edit this section -->

This manuscript was prepared using [Manubot](https://github.com/manubot/manubot). For usage information see [github.com/manubot/rootstock](https://github.com/manubot/rootstock). The [usage.md](https://github.com/manubot/rootstock/blob/master/USAGE.md) and [example](https://manubot.github.io/rootstock/) may be particularly helpful. 

