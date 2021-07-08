---
title: CNApy Users Guide
keywords:
- constraint-programming
- metabolic-models
lang: en-US
date-meta: '2021-07-08'
author-meta:
- Sven Thiele
- Axel von Kamp
header-includes: |-
  <!--
  Manubot generated metadata rendered from header-includes-template.html.
  Suggest improvements at https://github.com/manubot/manubot/blob/main/manubot/process/header-includes-template.html
  -->
  <meta name="dc.format" content="text/html" />
  <meta name="dc.title" content="CNApy Users Guide" />
  <meta name="citation_title" content="CNApy Users Guide" />
  <meta property="og:title" content="CNApy Users Guide" />
  <meta property="twitter:title" content="CNApy Users Guide" />
  <meta name="dc.date" content="2021-07-08" />
  <meta name="citation_publication_date" content="2021-07-08" />
  <meta name="dc.language" content="en-US" />
  <meta name="citation_language" content="en-US" />
  <meta name="dc.relation.ispartof" content="Manubot" />
  <meta name="dc.publisher" content="Manubot" />
  <meta name="citation_journal_title" content="Manubot" />
  <meta name="citation_technical_report_institution" content="Manubot" />
  <meta name="citation_author" content="Sven Thiele" />
  <meta name="citation_author_institution" content="Analysis and Redesign of Biological Networks, Max Planck Institute for Dynamics of Complex Technical Systems Magdeburg" />
  <meta name="citation_author_orcid" content="0000-0002-5812-6963" />
  <meta name="citation_author" content="Axel von Kamp" />
  <meta name="citation_author_institution" content="Analysis and Redesign of Biological Networks, Max Planck Institute for Dynamics of Complex Technical Systems Magdeburg" />
  <link rel="canonical" href="https://cnapy-org.github.io/users-guide/" />
  <meta property="og:url" content="https://cnapy-org.github.io/users-guide/" />
  <meta property="twitter:url" content="https://cnapy-org.github.io/users-guide/" />
  <meta name="citation_fulltext_html_url" content="https://cnapy-org.github.io/users-guide/" />
  <meta name="citation_pdf_url" content="https://cnapy-org.github.io/users-guide/manuscript.pdf" />
  <link rel="alternate" type="application/pdf" href="https://cnapy-org.github.io/users-guide/manuscript.pdf" />
  <link rel="alternate" type="text/html" href="https://cnapy-org.github.io/users-guide/v/a3fe605398533e48e550f0caf8ecb153893ad6f0/" />
  <meta name="manubot_html_url_versioned" content="https://cnapy-org.github.io/users-guide/v/a3fe605398533e48e550f0caf8ecb153893ad6f0/" />
  <meta name="manubot_pdf_url_versioned" content="https://cnapy-org.github.io/users-guide/v/a3fe605398533e48e550f0caf8ecb153893ad6f0/manuscript.pdf" />
  <meta property="og:type" content="article" />
  <meta property="twitter:card" content="summary_large_image" />
  <link rel="icon" type="image/png" sizes="192x192" href="https://manubot.org/favicon-192x192.png" />
  <link rel="mask-icon" href="https://manubot.org/safari-pinned-tab.svg" color="#ad1457" />
  <meta name="theme-color" content="#ad1457" />
  <!-- end Manubot generated metadata -->
bibliography:
- content/manual-references.json
manubot-output-bibliography: output/references.json
manubot-output-citekeys: output/citations.tsv
manubot-requests-cache-path: ci/cache/requests-cache
manubot-clear-requests-cache: false
...






<small><em>
This manuscript
([permalink](https://cnapy-org.github.io/users-guide/v/a3fe605398533e48e550f0caf8ecb153893ad6f0/))
was automatically generated
from [cnapy-org/users-guide@a3fe605](https://github.com/cnapy-org/users-guide/tree/a3fe605398533e48e550f0caf8ecb153893ad6f0)
on July 8, 2021.
</em></small>

## Authors



+ **Sven Thiele**<br>
    ![ORCID icon](images/orcid.svg){.inline_icon}
    [0000-0002-5812-6963](https://orcid.org/0000-0002-5812-6963)
    · ![GitHub icon](images/github.svg){.inline_icon}
    [sthiele](https://github.com/sthiele)<br>
  <small>
     Analysis and Redesign of Biological Networks, Max Planck Institute for Dynamics of Complex Technical Systems Magdeburg
  </small>

+ **Axel von Kamp**<br>
    · ![GitHub icon](images/github.svg){.inline_icon}
    [axelvonkamp](https://github.com/axelvonkamp)<br>
  <small>
     Analysis and Redesign of Biological Networks, Max Planck Institute for Dynamics of Complex Technical Systems Magdeburg
  </small>



<!-- ## Abstract {.page_break_before} -->




## Introduction

This is the user manual of CNApy. CNApy is a graphical interface for the modelling and analysis of metabolic networks on the basis of constraint-based (stoichiometric) modeling approaches. It allows

- the import/export of SBML models
- creating COBRApy/CNA models
- linking a graphical representation to the model data
- convenient exploration and  editing of the model
- model analysis with standard and advanced constraint-based methods
- and saving everything as a CNApy *.cna project

The methods provided for model analysis (some of them are part of CNApy but most are functions from CNA and COBRApy) include:

- Flux balance analysis
- Parsimonious flux balance analysis
- Flux variability analysis
- Minimal cut sets
- Elementary modes
- Phase plane analysis
- Yield optimization


CNApy is available at [https://github.com/cnapy-org/CNApy](https://github.com/cnapy-org/CNApy) under the [Apache-2.0 License](https://github.com/ARB-Lab/CNApy/blob/master/LICENSE).

We appreciate any comments or suggestions for improvements and we are greatly interested in your feedback which you can give at our [User Forum](https://groups.google.com/g/cellnetanalyzer-user-forum).

For feature requests and bug reports please use our [Issue tracker](https://github.com/cnapy-org/CNApy/issues)

Thank you for using CNApy!



## Installation

The easiest way to install CNApy is using conda. First install conda and then:

- Create a conda environment with all dependencies

    ```sh
    conda create -n cnapy-1.0.0 -c conda-forge -c cnapy cnapy=1.0.0
    ```

- Activate the cnapy conda environment

    ```sh
    conda activate cnapy-1.0.0
    ```

- Run CNApy

    ```sh
    cnapy
    ```

On windows you may also use the [graphical installer](https://github.com/cnapy-org/CNApy/releases/download/v1.0.0/CNApy-1.0.0-Windows-x86_64.exe).


## Configuration

When we start CNApy for the first time we are greeted with a dialog like this.

![
**CNApy Configuration dialog.**
](https://raw.githubusercontent.com/cnapy-org/users-guide/main/content/images/config-dialog.png "Configuration dialog"){#fig:config-dialog}

With this dialog you can configure which Matlab/Octave installation CNApy should use.

The minimal cut set computation in CNApy uses functions that are provided by CellNetAnalyzer.
To be able to use these functions you have to provide CNApy with either a path to a Matlab installation >R2019 or the path to an Octave executable >4, and of course with a path to a recent CellNetAnalyzer installation.
You can do this by clicking these buttons (1).
If you change the settings CNApy performs some basic tests to make sure everything is working.
If all checks are successful green check marks  are shown, if a check fails a red cross  is shown.

If no check can be performed, a yellow question mark  is shown.
For example, the check of the CNA directory needs a working Matlab or Octave installation.

You can also configure which colors CNApy should use to highlight reactions on the map or in the reaction list.


## User interface overview

This section gives an introduction to the CNApy UI and its components and functions.

When we have finished our first configuration we are greeted with a window like this.

![
**CNApy with an empty project.**
](https://raw.githubusercontent.com/cnapy-org/users-guide/main/content/images/empty-project.png "Empty project"){#fig:empty-project}

This is an empty project on the right hand side we see the empty lists of reactions and metabolites.
On the left we see the embedded Jupyter Console where one can interact programmatically with the model and UI.
We can create a new project by importing SBML models, editing the reactions and adding graphical maps.
We can also load one of the projects included in our projects repository.

Let’s go to Project in our menubar and open the `ECC2comp.cna` project.

![
**CNApy with the ECC2comp project.**
](https://raw.githubusercontent.com/cnapy-org/users-guide/main/content/images/ecc2comp-project.png "ECC2comp project"){#fig:ecc2-project}


In this picture we see CNApy with the open ECC2comp project.
On the right hand side (1) we see the populated reactions and metabolites lists with the color coded current values and corresponding details for the selected reaction/metabolite.
The reactions list contains buttons that lets us add/delete reactions to/from the model.
The console (2) now shows the output of some computations, and above the console we have a map view (3) with a graphical representation of our network.
On top (4) we have the menu bar which gives us access to the various functionalities of CNApy and a Toolbar for quick access to often used functions.

We can add new maps via the Map menu, and drag reactions from the reaction list onto the desired position on the map.


## Create a new project

In this Section we explain how to create a new network project.
We also have a video on that topic [https://youtu.be/bsNXZBmtyWw](https://youtu.be/bsNXZBmtyWw).

CNApy starts with an empty Project.
You can directly add new reactions via the reaction mask on the right.
By pressing the *Add new reaction* button.

Then simply type the reaction formula into the Equation field. For example `A + 2 B -> C`.

The associated metabolites `A`, `B` and `C` are then automatically added to the model.

Changing metabolite identifiers in the metabolite form instantly rewrites the reaction equation of the associated reactions.

Creating big models by adding single reactions is very cumbersome.
Therefore CNApy allows you to create a new project from an SBML file.
You find the point *New project from SBML* in the *Project* menu.

After importing an SBML model the reaction list is populated with all the reactions from the model.

You can add a map to our project, by going to the *Map* menu and clicking *add new map*.

From the *Map* menu we can also *change the background image* of our map.
Any SVG image can be used as a background.

You can add multiple maps that highlight different aspects of your model.

Reaction boxes can be put on the map by dragging over them from the reactions list.

You can adjust the box size with the keyboard shortcuts `Ctrl`{.grey} + `+`{.grey} and `Ctrl`{.grey} + `-`{.grey}.
You can move the reaction box to the desired position by dragging them on their handles.
If you want to move all reaction boxes together, press `Ctrl`{.grey} while dragging.

Positioning a big number of reaction boxes can be tiresome.
CNApy allows you to load and save reaction box positions.
This facilitates reuse among similar projects.

The size of the background image can be adjusted with the shortcuts `Ctrl`{.grey} + `Shift`{.grey} + `+`{.grey} and `Ctrl`{.grey} + `Shift`{.grey} + `-`{.grey}.

To save a project click *Save Project as* in the *Project* menu.
It is important to add the `.cna` extension to the file name.
This way your files can be found by CNApy.


## Scenarios

In CNApy you can define a scenario under which metabolic analysis like the FBA will be performed.
In essence a scenario is a set of flux constraints for a set of reactions.
These constraints can fix the flux of a reaction or constraint lower and upper bounds for the flux.

The scenario can be edited via the map, by entering values into the corresponding reaction boxes. 
Accepted values are either a single float like `1.5` or a pair of floats like `(-10, 1.2)`.
A single float fixes the flux of the reaction to this value (`1.5`).
While a pair sets the lower flux bound of the reaction to the first value (`-10`) and the upper flux bound to the second value (`1.2`).

![
**Reaction box with scenario value.**
](https://raw.githubusercontent.com/cnapy-org/users-guide/main/content/images/scenario-box.png "Reaction box with scenario value"){#fig:scenario-box}

Reactions boxes with scenario constraints are marked by the scenario color and a green frame.
The frame turns yellow, if the scenario constraint contradicts the reaction constraints of the model.

To remove the constraints on a reaction simply delete the scenario value in the reaction box.

You can save and load scenarios as `*.scen` files. One scenario can be set as the default scenario of your project.
This can be done via *set current scenario as default scenario* in the *Scenario* menu.
The project must then be saved, and the next time you open the project the scenario is already set.

CNApy implements an edit history for the scenario with the tool buttons you can undo and redo your changes to the scenario.
You can also import all the values that are currently in the reaction boxes into the scenario, and you can change the model's reaction bounds to the current scenario values.


## Analysis functions

### Flux balance analysis (FBA)

Optimizes the value of the current objective function and shows a flux distribution that realizes this optimum.
The objective function is a linear function over the reaction rates in the network, its coefficients can be modified in the reaction dialogs.
To display the current objective function in the console you can call “Show optimization function” from the analysis menu.
Note that the flux distribution calculated by FBA is usually not unique.

### Parsimonious FBA (pFBA)

In parsimonious FBA first the objective function optimized and then with this optimum as additional constraint the sum of the fluxes in the network is minimized.
This has the advantage that redundant internal cyclic fluxes are suppressed and that a lot of reactions will have zero flux which makes the solution easier to understand.

### Flux variability analysis (FVA)

In FVA the maximal/minimal rate of each reaction is calculated.
This gives the possible flux range for each reaction.

### Elementary modes (EFM)/elementary flux vectors (EFV)

EFM can be calculated via CNA or directly via efmtool while for EFV CNA is required.

![
**Elementary Flux Mode Computation Dialog.**
](https://raw.githubusercontent.com/cnapy-org/users-guide/main/content/images/efm-dialog.png "Elementary Flux Mode Computation Dialog"){#fig:efm-dialog}

#### Options for CNA and efmtool

When reactions are marked with 0 flux in a scenario and the option “consider 0 in current scenario as off” is activated then only the subset of EFM/EFV is calculated in which these reactions do not participate

#### Additional options for CNA

- use flux bounds to calculate elementary flux vectors
To calculate EFV instead of EFM, activate this option. Flux bounds defined in the reactions and the current scenario are then taken into account as inhomogeneous constraints. A flux bound is only included when its absolute value is greater than the value given as “Threshold for bounds to be unconstrained”.

- check reversibility

Unchecking this option will lead to all reactions being considered reversible even if they have a rate minimum ≥ 0.

- only convex basis

Currently has no effect (need to be able to switch computation method first).

- consider isozymes only once

If a group of reactions has the same stoichiometry then only the modes with one representative of that group are calculated.

- use rational numbers

Use rational numbers of arbitrary length for EFM/EFV computation (efmtool part only, results will still appear as floating point numbers)
To calculate EFV instead of EFM, activate this option. Flux bounds defined in the reactions and the current scenario are then taken into account as inhomogeneous constraints. A flux bound is only included when its absolute value is greater than the value given as “Threshold for bounds to be unconstrained”.

### Minimal cut sets

Minimal cut sets (MCS) can be calculated in CNApy using the dual method.


![
**Minimal cut sets computation dialog.**
](https://raw.githubusercontent.com/cnapy-org/users-guide/main/content/images/mcs-dialog.png "Minimal cut sets computation dialog"){#fig:mcs-dialog}

- Target and Desired region(s)

For the dual method one or more target regions must be defined which describe the network behaviour that is to be suppressed.
In addition, one or more desired regions may be defined which describe the network behaviour that is to be preserved.
Each target/desired region is defined by a set of linear equality constraints over the reaction rates in the network.
All target and desired regions must be initially feasible or an error will be raised. Also make sure that 0 is not included in any target or desired region (0 as target cannot be suppressed and 0 as desired is always fulfilled).

Note that all non-default reaction bounds (as defined by cobra.Configuration().bounds) are automatically added to all target and desired regions before MCS computation.

- Solver

MCS can either be calculated via CNA (using either Octave or Matlab) or via optlang using different MILP solvers.
For CNA the solver must be chosen while optlang uses the solver for the current model (cf. Solver for current model).
Not all variants and solvers allow for the same options so these will partly be disabled depending on the chosen solver.

- Max. solutions

Maximal number of MCS to calculate.

- Max. size

Only calculate MCS which consists of up to this number of cuts.

- Time limit

Do not run the search for longer than this limit.
It is strongly recommended to use this parameter because MCS computation can take very long especially when searching for smallest MCS.

- MCS search

MCS can be enumerated iteratively, either the smallest first (least number of cuts) or any MCS (up to the number of cuts given by max. size).
With the latter option new MCS are found more quickly but may not be the smallest.

With CPLEX or Gurobi as solver, MCS can also be enumerated by cardinality, i.e. all MCS of successively increasing size (up to max. size) are computed. In addition, with these solvers a continuous search mode is possible which is similar to the any MCS method but often faster.

- Gene KOs (CNA only)

If the model contains the gene-reaction association, search for gene knock-outs instead of reaction knock-outs.

- Exclude boundary reactions as cuts (optlang only)

Do not allow knock-out of boundary reactions (reactions that cross the system boundary, e.g. exchange reactions).

- Consider constraints given by scenario

Take reaction bounds set by the current scenario into account for all target and desired regions.



*The rest of this document is a full list of formatting elements/features supported by Manubot.
Compare the input (`.md` files in the `/content` directory) to the output you see below.*

## Basic formatting

**Bold** __text__

[Semi-bold text]{.semibold}

[Centered text]{.center}

[Right-aligned text]{.right}

*Italic* _text_

Combined *italics and __bold__*

~~Strikethrough~~

1. Ordered list item
2. Ordered list item
    a. Sub-item
    b. Sub-item
        i. Sub-sub-item
3. Ordered list item
    a. Sub-item

- List item
- List item
- List item

subscript: H~2~O is a liquid

superscript: 2^10^ is 1024.

[unicode superscripts](https://www.google.com/search?q=superscript+generator)⁰¹²³⁴⁵⁶⁷⁸⁹

[unicode subscripts](https://www.google.com/search?q=superscript+generator)₀₁₂₃₄₅₆₇₈₉

A long paragraph of text.
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

Putting each sentence on its own line has numerous benefits with regard to [editing](https://asciidoctor.org/docs/asciidoc-recommended-practices/#one-sentence-per-line) and [version control](https://rhodesmill.org/brandon/2012/one-sentence-per-line/).

Line break without starting a new paragraph by putting  
two spaces at end of line.

## Document organization

Document section headings:

# Heading 1

## Heading 2

### Heading 3

#### Heading 4

##### Heading 5

###### Heading 6

### A heading centered on its own printed page{.center .page_center}

<!-- an arbitrary comment. visible in input, but not visible in output. -->

Horizontal rule:

---

`Heading 1`'s are recommended to be reserved for the title of the manuscript.

`Heading 2`'s are recommended for broad sections such as *Abstract*, *Methods*, *Conclusion*, etc.

`Heading 3`'s and `Heading 4`'s are recommended for sub-sections.

## Links

Bare URL link: <https://manubot.org>

[Long link with lots of words and stuff and junk and bleep and blah and stuff and other stuff and more stuff yeah](https://manubot.org)

[Link with text](https://manubot.org)

[Link with hover text](https://manubot.org "Manubot Homepage")

[Link by reference][manubot homepage]

[Manubot Homepage]: https://manubot.org

## Citations

Citation by DOI [@doi:10.7554/eLife.32822].

Citation by PubMed Central ID [@pmc:PMC6103790].

Citation by PubMed ID [@pubmed:30718888].

Citation by Wikidata ID [@wikidata:Q56458321].

Citation by ISBN [@isbn:9780262517638].

Citation by URL [@{https://greenelab.github.io/meta-review/}].

Citation by alias [@deep-review].

Multiple citations can be put inside the same set of brackets [@doi:10.7554/eLife.32822; @deep-review; @isbn:9780262517638].
Manubot plugins provide easier, more convenient visualization of and navigation between citations [@doi:10.1371/journal.pcbi.1007128; @pubmed:30718888; @pmc:PMC6103790; @deep-review].

Citation tags (i.e. aliases) can be defined in their own paragraphs using Markdown's reference link syntax:

[@deep-review]: doi:10.1098/rsif.2017.0387

## Referencing figures, tables, equations

Figure @fig:square-image

Figure @fig:wide-image

Figure @fig:tall-image

Figure @fig:vector-image

Table @tbl:bowling-scores

Equation @eq:regular-equation

Equation @eq:long-equation

## Quotes and code

> Quoted text

> Quoted block of text
>
> Two roads diverged in a wood, and I—  
> I took the one less traveled by,  
> And that has made all the difference.

Code `in the middle` of normal text, aka `inline code`.

Code block with Python syntax highlighting:

```python
from manubot.cite.doi import expand_short_doi

def test_expand_short_doi():
    doi = expand_short_doi("10/c3bp")
    # a string too long to fit within page:
    assert doi == "10.25313/2524-2695-2018-3-vliyanie-enhansera-copia-i-insulyatora-gypsy-na-sintez-ernk-modifikatsii-hromatina-i-svyazyvanie-insulyatornyh-belkov-vtransfetsirovannyh-geneticheskih-konstruktsiyah"
```

Code block with no syntax highlighting:

```
Exporting HTML manuscript
Exporting DOCX manuscript
Exporting PDF manuscript
```

## Figures

![
**A square image at actual size and with a bottom caption.**
Loaded from the latest version of image on GitHub.
](https://github.com/manubot/resources/raw/15493970f8882fce22bef829619d3fb37a613ba5/test/square.png "Square image"){#fig:square-image}

![
**An image too wide to fit within page at full size.**
Loaded from a specific (hashed) version of the image on GitHub.
](https://github.com/manubot/resources/raw/15493970f8882fce22bef829619d3fb37a613ba5/test/wide.png "Wide image"){#fig:wide-image}

![
**A tall image with a specified height.**
Loaded from a specific (hashed) version of the image on GitHub.
](https://github.com/manubot/resources/raw/15493970f8882fce22bef829619d3fb37a613ba5/test/tall.png "Tall image"){#fig:tall-image height=3in}

![
**A vector `.svg` image loaded from GitHub.**
The parameter `sanitize=true` is necessary to properly load SVGs hosted via GitHub URLs.
White background specified to serve as a backdrop for transparent sections of the image.
](https://raw.githubusercontent.com/manubot/resources/main/test/vector.svg?sanitize=true "Vector image"){#fig:vector-image height=2.5in .white}

## Tables

| *Bowling Scores* | Jane          | John          | Alice         | Bob           |
|:-----------------|:-------------:|:-------------:|:-------------:|:-------------:|
| Game 1 | 150 | 187 | 210 | 105 |
| Game 2 |  98 | 202 | 197 | 102 |
| Game 3 | 123 | 180 | 238 | 134 |

Table: A table with a top caption and specified relative column widths.
{#tbl:bowling-scores}

|         | Digits 1-33                        | Digits 34-66                      | Digits 67-99                      | Ref.                                                        |
|:--------|:-----------------------------------|:----------------------------------|:----------------------------------|:------------------------------------------------------------|
| pi      | 3.14159265358979323846264338327950 | 288419716939937510582097494459230 | 781640628620899862803482534211706 | [`piday.org`](https://www.piday.org/million/)               |
| e       | 2.71828182845904523536028747135266 | 249775724709369995957496696762772 | 407663035354759457138217852516642 | [`nasa.gov`](https://apod.nasa.gov/htmltest/gifcity/e.2mil) |

Table: A table too wide to fit within page.
{#tbl:constant-digits}

|          | **Colors** <!-- $colspan="2" --> |                      |
|:--------:|:--------------------------------:|:--------------------:|
| **Size** | **Text Color**                   | **Background Color** |
| big      | blue                             | orange               |
| small    | black                            | white                |

Table: A table with merged cells using the `attributes` plugin.
{#tbl: merged-cells}

## Equations

A LaTeX equation:

$$\int_0^\infty e^{-x^2} dx=\frac{\sqrt{\pi}}{2}$$ {#eq:regular-equation}

An equation too long to fit within page:

$$x = a + b + c + d + e + f + g + h + i + j + k + l + m + n + o + p + q + r + s + t + u + v + w + x + y + z + 1 + 2 + 3 + 4 + 5 + 6 + 7 + 8 + 9$$ {#eq:long-equation}

## Special

<i class="fas fa-exclamation-triangle"></i> [WARNING]{.semibold} _The following features are only supported and intended for `.html` and `.pdf` exports._
_Journals are not likely to support them, and they may not display correctly when converted to other formats such as `.docx`._

[Link styled as a button](https://manubot.org "Manubot Homepage"){.button}

Adding arbitrary HTML attributes to an element using Pandoc's attribute syntax:

::: {#some_id_1 .some_class style="background: #ad1457; color: white; margin-left: 40px;" title="a paragraph of text" data-color="white" disabled="true"}
Manubot Manubot Manubot Manubot Manubot.
Manubot Manubot Manubot Manubot.
Manubot Manubot Manubot.
Manubot Manubot.
Manubot.
:::

Adding arbitrary HTML attributes to an element with the Manubot `attributes` plugin (more flexible than Pandoc's method in terms of which elements you can add attributes to):

Manubot Manubot Manubot Manubot Manubot.
Manubot Manubot Manubot Manubot.
Manubot Manubot Manubot.
Manubot Manubot.
Manubot.
<!-- $id="element_id" class="some_class" $style="color: #ad1457; margin-left: 40px;" $disabled="true" $title="a paragraph of text" $data-color="red" -->

Available background colors for text, images, code, banners, etc:  

`white`{.white}
`lightgrey`{.lightgrey}
`grey`{.grey}
`darkgrey`{.darkgrey}
`black`{.black}
`lightred`{.lightred}
`lightyellow`{.lightyellow}
`lightgreen`{.lightgreen}
`lightblue`{.lightblue}
`lightpurple`{.lightpurple}
`red`{.red}
`orange`{.orange}
`yellow`{.yellow}
`green`{.green}
`blue`{.blue}
`purple`{.purple}

Using the [Font Awesome](https://fontawesome.com/) icon set:

<!-- include the Font Awesome library, per: https://fontawesome.com/start -->
<link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.7.2/css/all.css">

<i class="fas fa-check"></i> <i class="fas fa-question"></i> <i class="fas fa-star"></i> <i class="fas fa-bell"></i> <i class="fas fa-times-circle"></i> <i class="fas fa-ellipsis-h"></i>

[
<i class="fas fa-scroll fa-lg"></i> **Light Grey Banner**<br>
useful for *general information* - [manubot.org](https://manubot.org/)
]{.banner .lightgrey}

[
<i class="fas fa-info-circle fa-lg"></i> **Blue Banner**<br>
useful for *important information* - [manubot.org](https://manubot.org/)
]{.banner .lightblue}

[
<i class="fas fa-ban fa-lg"></i> **Light Red Banner**<br>
useful for *warnings* - [manubot.org](https://manubot.org/)
]{.banner .lightred}


## References {.page_break_before}

<!-- Explicitly insert bibliography here -->
<div id="refs"></div>
