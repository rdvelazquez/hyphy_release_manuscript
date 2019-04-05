---
author-meta:
- Sergei L KosaKovsky Pond
- Ryan D Velazquez
date-meta: '2019-04-05'
keywords:
- software
- evolution
- statistical methods
- natural selection
lang: en-US
title: HyPhy - Title TBD
...






<small><em>
This manuscript
([permalink](https://rdvelazquez.github.io/hyphy_release_manuscript/v/80f589932c1b66d0d3fcdc060c7b6de76b181f38/))
was automatically generated
from [rdvelazquez/hyphy_release_manuscript@80f5899](https://github.com/rdvelazquez/hyphy_release_manuscript/tree/80f589932c1b66d0d3fcdc060c7b6de76b181f38)
on April 5, 2019.
</em></small>

## Authors



+ **Sergei L KosaKovsky Pond**<br>
    · ![GitHub icon](images/github.svg){.inline_icon}
    [spond](https://github.com/spond)
    · ![Twitter icon](images/twitter.svg){.inline_icon}
    [sergeilkp](https://twitter.com/sergeilkp)<br>
  <small>
     Institute for Genomics and Evolutionary Medicine, Temple University
  </small>

+ **Ryan D Velazquez**<br>
    · ![GitHub icon](images/github.svg){.inline_icon}
    [rdvelazquez](https://github.com/rdvelazquez)<br>
  <small>
     Institute for Genomics and Evolutionary Medicine, Temple University
  </small>



## Abstract {.page_break_before}

Here we announce the latest release of the HyPhy software package.
HyPhy is designed for the analysis of genetic sequences using stochastic evolutionary models with common application to understanding the pressures exerted by natural selection.
HyPhy is widely used, actively supported, open source and freely available on a multitude of platforms. 
The codebase is available at <https://github.com/veg/hyphy>. 
Documentation, tutorials and downloads are available at <https://hyphy.org>.

## Introduction

HyPhy (Hypothesis testing using Phylogenies) is an open source software package for comparative sequence analysis using stochastic evolutionary models. 
Since its initial release in 2005 [@OG5Jd8Ck] HyPhy has become an integral tool for the bioinformatics community with over 10,000 registered users, over 2,000 peer-reviewed citations and approximately 1,000 HyPhy jobs processed each week on the datamonkey web server [@E9o1eL84; @1DlzNU0dT; @1DPhLuJmc]. 
Extensions and improvements to the HyPhy package have been ongoing since its inception, with active feedback between users and developers producing new features tailored to the specific needs of the research community. 
Here we announce the release of the newest version of HyPhy (version 2.4.0) and document how the software has been (1) packaged for easy use in a variety of settings (2) optimized for larger datasets (3) redesigned to follow modern bioinformatics best practices and (4) extended to include a broader set of standard analyses.

## Packaged for Easy Use in a Variety of Settings

The users of HyPhy vary greatly in their technical proficiency, from biologists unfamiliar with the command line to bioinformaticians who want to incorporate HyPhy into their own software. 
To meet the needs of this divers user set, HyPhy has been packaged and distributed for use in multiple different forms as outlined in table 1. 


| Usage                   | Required Skills | Easily Extensible | Mac | Windows | Linux | Tutorial                                                 | Download or Link                           |
|-------------------------|-----------------|-------------------|-----|---------|-------|----------------------------------------------------------|-------------------------------------------|
| Custom HBL Scripts | HBL             | Yes               | Yes |         | Yes   | <http://hyphy.org/about/#example-hbl-script>               | <https://github.com/veg/hyphy>              |
| Command Line Invocation | Command line    | Yes               | Yes |         | Yes   | To Be Written                                            | <https://github.com/veg/hyphy>             |
| Command Line Prompt     | Command line    | Yes               | Yes |         | Yes   | <http://hyphy.org/tutorials/current-release-tutorial/>     | <https://github.com/veg/hyphy>              |
| PhyPhy                  | Python          | Yes               | Yes |         | Yes   | <https://github.com/sjspielman/phyphy>                     | <http://sjspielman.org/phyphy/>             |
| DataMonkey              | None            |                   | Web | Web     | Web   | <http://datamonkey.org/help>                               | <http://datamonkey.org/>                    |
| HyPhy-GUI               | None            |                   | Yes |         | Yes   | <http://hyphy.org/tutorials/current-release-tutorial_gui/> | <https://github.com/veg/hyphy-gui/releases> |
| Galaxy                  | None            | Yes               | Web | Web     | Web   | <https://galaxyproject.org/support/>                       | <https://galaxy.hyphy.org>                  |
| MEGA                    | None            |                   | Yes | Yes     | Yes   | <https://www.megasoftware.net/docs>                        | <https://www.megasoftware.net/>             |

## Optimized for Larger Datasets 

HyPhy has been optimized to analyze datasets with thousands of sequences and tens of thousands of sites. 
This optimization was accomplished by (1) integrating recent algorithmic advances from the fields of machine learning and natural language processing [@TkofEaUO] into the core c++ implementation (2) incorporating fast Bayesian methods [@BLiAMJec] (3) developing parallel implementations for commute intensive processes and (4) providing high performance computing infrastructure[@E9o1eL84; @1DlzNU0dT; @1DPhLuJmc] free of charge to the global community, helping to democratize access to scientific computing resources [@16bcy34vy].

_(performance numbers...)_

## Redesigned to Follow Modern Bioinformatics Best Practices

The design of the original HyPhy implementation emphasized convenient writing and execution of single HyPhy Batch Language (HBL) scripts. 
This decision manifested in the easy to use command line prompt which guided users interactively through selecting the desired analysis and choosing the specific analysis parameters. 
Also, the HBL itself was designed to allow sophisticated models to be specified and fit with concise scripts, facilitated by extensive use of a global namespace. 
As the common use of HyPhy has shifted over the last decade from one-off analyses toward larger studies and use within pipelines, the demands on HyPhy have also shifted. 
HyPhy has therefore been redesigned to address the requirements of these changing use cases.   

Usage as a typical command line tool (i.e. an executable name followed by key word arguments) has been added alongside the interactive command line prompt. 
This change, along with the ability to use relative paths to files, has made using HyPhy in pipelines and batch analyses much more seamless.
In addition to being easier to use, the package is also now easier to install. HyPhy is now installable with bioconda [@sYguBb3Q] which has become the defacto package manager for scientific software. Users no longer need to concern themselves with dependencies, environments and build processes but can simply `conda install hyphy`.


The inner workings of HyPhy have also been improved, providing a more reliable package that is easier to extend.
To this end, namespacing has been introduced.
Before, all variables were automatically declared at a global scope. 
Namespaces helped facilitated the refactoring and standardization of the template batch files for easier comprehension and reuse.  
Additionally, extensive automated testing has been implemented.
The automated testing is executed as a part of a continuous integration (CI) pipeline which which both expedites development and helps ensure healthy software is delivered.
The automated testing includes: unit tests for over 90% of HBL functions, method tests on all the core analyses and likelihood testing [@MOcKAui8] which compares the likelihood values calculated by HyPhy with other popular maximum-likelihood software packages and informs the developers if discrepancies are identified.

## Extended to Include a Broader Set of Standard Analyses

Although the HyPhy package provides for limitless customization via writing HBL scripts, users can run many common analyses without needing to concern themselves with the HBL at all. 
The HyPhy package comes with pre-written HBL scripts for easily performing some of the most commonly used analyses. 
These analyses can be executed in the various places HyPhy is available and include (in alphabetical order):  
  
+ aBSREL [@w4iHLQCq; @hX6CSnea] (adaptive Branch-Site Random Effects Likelihood) - Detecting positive selection at individual branches  
+ BGM [@V35tv36N] (Bayesian Graphical Models) - Testing for co-evolving sites  
+ BUSTED [@13wl6FKEJ] (Branch-Site Unrestricted Statistical Test for Episodic Diversification) - Testing gene-wide selection at pre-defined lineages  
+ FADE (FUBAR Approach to Directional Evolution) - Evaluating if sites are subject to directional selection  
+ FEL [@1AP8NmEKg] (Fixed Effects Likelihood) - Inferring non-synoymous and synonymous substitution rates on a per-site basis for smaller datasets using maximum likelihood  
+ FUBAR (Fast, Unconstrained Bayesian AppRoximation) - Infer non-synonymous and synonymous substitution rates on a per-site basis for larger datasets using Bayesian methods  
+ GARD [@PTZuTBNs] (Genetic Algorithm for Recombination Detection) - Screen multiple sequence alignment for recombination  
+ MEME [@hI0YJStl] (Mixed Effects Model of Evolution) - Test the hypothesis that individual sites have been subject to episodic positive/diversifying selection  
+ RELAX [@OpDB3a8r] - Evaluate whether the strength of natural selection has been relaxed or intensified along a specific set of branches  
+ SLAC [@1AP8NmEKg] (SingleLikelihood Ancestor Counting) - Infer non-synonymous and synonymous substitution rates on a per-site basis 

## References {.page_break_before}

<!-- Explicitly insert bibliography here -->
<div id="refs"></div>
