---
title: CNApy Guide
keywords:
- constraint-programming
- metabolic-models
lang: en-US
date-meta: '2022-06-23'
author-meta:
- Sven Thiele
- Axel von Kamp
- Pavlos Stephanos Bekiaris
- Philipp Schneider
header-includes: |-
  <!--
  Manubot generated metadata rendered from header-includes-template.html.
  Suggest improvements at https://github.com/manubot/manubot/blob/main/manubot/process/header-includes-template.html
  -->
  <meta name="dc.format" content="text/html" />
  <meta name="dc.title" content="CNApy Guide" />
  <meta name="citation_title" content="CNApy Guide" />
  <meta property="og:title" content="CNApy Guide" />
  <meta property="twitter:title" content="CNApy Guide" />
  <meta name="dc.date" content="2022-06-23" />
  <meta name="citation_publication_date" content="2022-06-23" />
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
  <meta name="citation_author" content="Pavlos Stephanos Bekiaris" />
  <meta name="citation_author_institution" content="Analysis and Redesign of Biological Networks, Max Planck Institute for Dynamics of Complex Technical Systems Magdeburg" />
  <meta name="twitter:creator" content="@Paulocracy2" />
  <meta name="citation_author" content="Philipp Schneider" />
  <meta name="citation_author_institution" content="Analysis and Redesign of Biological Networks, Max Planck Institute for Dynamics of Complex Technical Systems Magdeburg" />
  <link rel="canonical" href="https://cnapy-org.github.io/CNApy-guide/" />
  <meta property="og:url" content="https://cnapy-org.github.io/CNApy-guide/" />
  <meta property="twitter:url" content="https://cnapy-org.github.io/CNApy-guide/" />
  <meta name="citation_fulltext_html_url" content="https://cnapy-org.github.io/CNApy-guide/" />
  <meta name="citation_pdf_url" content="https://cnapy-org.github.io/CNApy-guide/manuscript.pdf" />
  <link rel="alternate" type="application/pdf" href="https://cnapy-org.github.io/CNApy-guide/manuscript.pdf" />
  <link rel="alternate" type="text/html" href="https://cnapy-org.github.io/CNApy-guide/v/5f252d4084ad4ea6e6ea512fa5817d238a208724/" />
  <meta name="manubot_html_url_versioned" content="https://cnapy-org.github.io/CNApy-guide/v/5f252d4084ad4ea6e6ea512fa5817d238a208724/" />
  <meta name="manubot_pdf_url_versioned" content="https://cnapy-org.github.io/CNApy-guide/v/5f252d4084ad4ea6e6ea512fa5817d238a208724/manuscript.pdf" />
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
([permalink](https://cnapy-org.github.io/CNApy-guide/v/5f252d4084ad4ea6e6ea512fa5817d238a208724/))
was automatically generated
from [cnapy-org/CNApy-guide@5f252d4](https://github.com/cnapy-org/CNApy-guide/tree/5f252d4084ad4ea6e6ea512fa5817d238a208724)
on June 23, 2022.
</em></small>

## Authors




+ **Sven Thiele**<br>
    ![ORCID icon](images/orcid.svg){.inline_icon width=16 height=16}
    [0000-0002-5812-6963](https://orcid.org/0000-0002-5812-6963)
    · ![GitHub icon](images/github.svg){.inline_icon width=16 height=16}
    [sthiele](https://github.com/sthiele)<br>
  <small>
     Analysis and Redesign of Biological Networks, Max Planck Institute for Dynamics of Complex Technical Systems Magdeburg
  </small>


+ **Axel von Kamp**<br>
    · ![GitHub icon](images/github.svg){.inline_icon width=16 height=16}
    [axelvonkamp](https://github.com/axelvonkamp)<br>
  <small>
     Analysis and Redesign of Biological Networks, Max Planck Institute for Dynamics of Complex Technical Systems Magdeburg
  </small>


+ **Pavlos Stephanos Bekiaris**<br>
    · ![GitHub icon](images/github.svg){.inline_icon width=16 height=16}
    [Paulocracy](https://github.com/Paulocracy)
    · ![Twitter icon](images/twitter.svg){.inline_icon width=16 height=16}
    [Paulocracy2](https://twitter.com/Paulocracy2)<br>
  <small>
     Analysis and Redesign of Biological Networks, Max Planck Institute for Dynamics of Complex Technical Systems Magdeburg
  </small>


+ **Philipp Schneider**<br>
    · ![GitHub icon](images/github.svg){.inline_icon width=16 height=16}
    [VonAlphaBisZulu](https://github.com/VonAlphaBisZulu)<br>
  <small>
     Analysis and Redesign of Biological Networks, Max Planck Institute for Dynamics of Complex Technical Systems Magdeburg
  </small>



<!-- ## Abstract {.page_break_before} -->




## Introduction

This is the user manual of CNApy. CNApy is a graphical interface for the modelling and analysis of metabolic networks on the basis of constraint-based (stoichiometric) modeling approaches. It allows

- Importing/exporting  SBML models
- Creating COBRApy/CNA models
- Linking a graphical representation to model data
- Convenient exploration and editing of the model
- Model analysis with standard and advanced constraint-based methods, and
- Saving everything as a CNApy *.cna project

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

### CNApy main program

There are two ways to install CNApy itself:

1. Recommended but more complicated: Under any operating system, by installing CNApy as a conda package. For detailed instructions to do this, see [https://github.com/cnapy-org/CNApy#install-cnapy-with-conda](https://github.com/cnapy-org/CNApy#install-cnapy-with-conda).
2. Not recommended but simple: Under Windows, you can install CNApy by using the .exe installer attached to [CNApy's latest release](https://github.com/cnapy-org/CNApy/releases/latest). Once you run the installer, it will guide you through the installation process. Please note that the installation process may take some time.

**NOTE: After CNApy's installation, it is recommended to download the [CNApy example projects](https://github.com/cnapy-org/CNApy-projects) (including interactive maps of models such as [ECC2](https://www.nature.com/articles/srep39647), [*i*ML1515](https://www.nature.com/articles/nbt.3956) and many more) by starting CNApy and clicking on "Download CNApy example projects..." in the "Projects" menu entry.**


### Installing additional solvers (optional)

CNApy itself is already packaged and installed with the open source linear programming solver [GLPK](https://www.gnu.org/software/glpk/) which is fast enough for calculations with small models and which is not restricted in the possible number of variables.

*Completely optional*: In addition, CNApy is also pre-packaged with the Community editions of the much more powerful commercial solvers [IBM CPLEX](https://www.ibm.com/products/ilog-cplex-optimization-studio) and [Gurobi](https://www.gurobi.com/). These community editions can only run with models up to 1000 variables. In order to use one of these solvers with models which contain more variables, the *full versions* of either two of these solvers have to be installed and connected to CNApy. In order to help you with this process, CNApy contains a wizard which explains the process in detail and which takes over some of the neccessary tasks. You can find the wizards under the "Config" menu entry.


## Configuration

CNApy can be configured via the Config menu. The different aspects of CNApy can be configured via separate dialogs:

### Configure CNApy

![
**CNApy Configuration dialog.**
](https://raw.githubusercontent.com/cnapy-org/CNApy-guide/main/content/images/configure-cnapy-dialog.png "Configuration dialog"){#fig:config-dialog}

Here you can configure which colors CNApy should use to highlight reactions on the map or in the reaction list.

### Configure COBRApy

![
**COBRApy configuration dialog.**
](https://raw.githubusercontent.com/cnapy-org/CNApy-guide/main/content/images/cobrapy-config-dialog.png "COBRApy configuration dialog"){#fig:cobrapy-config}


With this dialog selected global settings (`class cobra.Configuration()`) of the COBRApy toolbox and selected parameters of the current model can be modified. The global settings are saved, but the parameters of the current model are not and will revert to the global default values when (re-)loading a model.

- Default solver (global)

Select which solver to use as global default from the dropdown list. COBRApy supports a variety of solvers but only the ones which are installed for COBRApy on your system will be available on the list. Also, different solvers have different capabilities so you should set a default that has all capabilities that you require (e.g. glpk_exact cannot be used for MILPs).

- Solver for current model

Here you can change the solver for the current model.

- Number of processes for multiprocessing (global)

Number of processes run in parallel when Python multiprocessing is used, e.g. for FVA. Setting this to 1 disables multiprocessing.

<!-- IMPORTANT: Should be set to 1 on Windows because Python multiprocessing performs very poorly on this OS. -->
[
<i class="fas fa-info-circle fa-lg"></i> **IMPORTANT**<br>
Should be set to 1 on Windows because Python multiprocessing performs very poorly on this OS.
]{.banner .lightblue}


- Default tolerance (global)

This value is used to distinguish zero from non-zero elements for various purposes. In particular, this value is propagated to the solver (see the COBRApy source code which solver parameters are affected). Most solvers restrict the range of this value, so it must be between 1E-9 and 0.1 For details where this value is used see the COBRApy documentation and source code.

- Tolerance for the current model

Here you can change the tolerance for the current model. You may enter an arbitrary value >= 0 here but if it is not compatible with the current solver then “Apply Changes” can lead to an error message.



## User interface overview

This section gives an introduction to the CNApy UI and its components and functions.

![
**CNApy with an empty project.**
](https://raw.githubusercontent.com/cnapy-org/CNApy-guide/main/content/images/empty-project.png "Empty project"){#fig:empty-project}

This is an empty project on the right hand side we see the empty lists of reactions, metabolites and genes.
On the left we see the embedded Jupyter Console where one can interact programmatically with the model and UI.
We can create a new project by importing SBML models, editing the reactions and adding graphical maps.
We can also load one of the projects included in our projects repository.

Let’s go to Project in our menubar and open the `ECC2comp.cna` project.

![
**CNApy with the ECC2comp project.**
](https://raw.githubusercontent.com/cnapy-org/CNApy-guide/main/content/images/ecc2comp-project.png "ECC2comp project"){#fig:ecc2-project}


In this picture we see CNApy with the open ECC2comp project.
On the right hand side (1) we see the populated reactions and metabolites lists with the color coded current values and a form with corresponding details for the selected reaction/metabolite.

The upper part of the reactions lists contains several columns. In the "Scenario" column the current scenario values are shown and can also be edited via this column. The "Flux" column contains the results of the last computation, e.g. the fluxes from a FBA. The "LB" and "UB" columns show the lower/upper bounds of the reactions and after a FVA the results of this analysis will be displayed there.

The reactions list contains buttons that lets us add/delete reactions to/from the model.
Changing the metabolite identifier or other details in the metabolite/reaction form has an instant effect on the corresponding reactions/metabolites in the model.

When selecting a metabolite in the metabolite tabs a list of reactions (and corresponding equations) in which this metabolite participates is shown a the bottom. By double-clicking on a reaction or metabolite ID one can switch to the respective object.

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
These constraints can fix the flux of a reaction or set a lower and upper bounds for the flux.

The scenario can be edited via the reaction boxes on the map or the "Scenario" column of the reaction list. 
Accepted values are either a single float like `1.5` or a pair of floats like `-10, 1.2`.
A single float fixes the flux of the reaction to this value (`1.5`).
While a pair sets the lower flux bound of the reaction to the first value (`-10`) and the upper flux bound to the second value (`1.2`).
Note that in a scenario you can use values outside the defined lower/upper bound of a reaction. In such a casse the scenario will supersede the reaction bounds which allows temporary modification of the bounds without the need to change the model.

![
**Reaction box with scenario value.**
](https://raw.githubusercontent.com/cnapy-org/CNApy-guide/main/content/images/scenario-box.png "Reaction box with scenario value"){#fig:scenario-box}

Reactions boxes with scenario constraints are marked by the scenario color and a green frame.
The frame turns yellow, if the scenario constraint lies outside the reaction bounds of the model.

To remove the constraints on a reaction simply delete the scenario value in the reaction box or "Scenario" column of the reaction list.

You can save and load scenarios as `*.scen` files. One scenario can be set as the default scenario of your project.
This can be done via *set current scenario as default scenario* in the *Scenario* menu.
The project must then be saved, and the next time you open the project the scenario is already set.

CNApy implements an edit history for the scenario with the tool buttons you can undo and redo your changes to the scenario.
You can also import all the values that are currently in the reaction boxes into the scenario (can be useful for applying a MCS), and you can change the model's reaction bounds to the current scenario values.


## Analysis functions

### Flux balance analysis (FBA)

Optimizes the value of the current objective function and shows a flux distribution that realizes this optimum.
The objective function is a linear function over the reaction rates in the network, its coefficients can be modified in the reaction dialogs.
To display the current objective function you can choose *Show optimization function* from the *Analysis* menu.
The current objective value is shown in the console as well as the status bar at the bottom of the main window.
Note that the flux distribution calculated by FBA is usually not unique.

### Auto FBA

This is a checkable option which switches the "Auto FBA" mode on or off. In "Auto FBA" mode a FBA is automatically performed when a scenario is changed or when a reaction property that potentially influences the FBA result is changed.

### Parsimonious FBA (pFBA)

In parsimonious FBA first the objective function optimized and then with this optimum as additional constraint the sum of the fluxes in the network is minimized.
This has the advantage that redundant internal cyclic fluxes are suppressed and that a lot of reactions will have zero flux which makes the solution easier to understand.

### Flux variability analysis (FVA)

In FVA the maximal/minimal rate of each reaction is calculated.
This gives the possible flux range for each reaction.

### Make scenario feasible

A scenario is infeasible if the given fluxes in this scenario are incompatible with each other. An example would be a flux of a product that is higher than the substrate flux multiplied by the maximal product yield. Such a situation could for instance arise due to measurement errors if the given fluxes come from experimental measurements. 

With "Make scenario feasible" the given fluxes in the scenario are modified to be consistent which basically relies on minimzing the sum of absolute differences between the given values and the computed values that make the scenario consistent. There are two main settings that control this minimization: Firstly, one can choose whether the differences are linear or quadratic terms, resulting in a linear program (LP) or quadratic program (QP) respectively (the latter requires a QP-capable solver like CPLEX or Gurobi). Secondly, the (reciprocal) weights with which the differences enter the objective function can either all be equal, relative to their absolute flux values (i.e. larger fluxes are more likely to be changed when resolving infeasibilities), or taken from a specified field in the reaction annotation (in the last case, where a reaction has no entry in the specified annotation field, the default weight is used). Note that only reactions with scenario fluxes fixed to values unequal to zero enter the optimization.

After optimization, the current scenario is modified so that it contains the calculated consistent fluxes and the necessary changes are shown on the console. You can go back to the original values via the scenario history.

Known issue: The solvers are currently accessed through the optlang interface. Setting up the quadratic ojective for the QP via this interface incurs a significant overhead which increases with the number of fluxes set in the scenario. This means that the method as a whole can become quite slow in case more than a few dozen fluxes were set despite the fact that solving the QP itself is ususally quite fast.

### Elementary modes (EFM)

EFM can be calculated via [efmtool](https://csb.ethz.ch/tools/software/efmtool.html) which is automatically installed with CNApy. After calculation a [navigation panel](#efmmcs-navigation-and-analysis) appears to acces the results.

#### Options

When reactions are marked with 0 flux in a scenario and the option “consider 0 in current scenario as off” is activated then only the subset of EFM/EFV is calculated in which these reactions do not participate

### Computational strain design

#### Minimal cut sets

Minimal cut sets (MCS) can be calculated in CNApy using the dual method. After calculation a [navigation panel](#emfmcs-navigation-and-analysis) appears to acces the results.

![
**Minimal cut sets computation dialog.**
](https://raw.githubusercontent.com/cnapy-org/CNApy-guide/main/content/images/mcs-dialog.png "Minimal cut sets computation dialog"){#fig:mcs-dialog}

- Target and Desired region(s)

For the dual method one or more target regions must be defined which describe the network behaviour that is to be suppressed.
In addition, one or more desired regions may be defined which describe the network behaviour that is to be preserved.
Each target/desired region is defined by a set of linear equality constraints over the reaction rates in the network.
All target and desired regions must be initially feasible or an error will be raised. Also make sure that 0 is not included in any target or desired region (0 as target cannot be suppressed and 0 as desired is always fulfilled).

Note that all non-default reaction bounds (as defined by cobra.Configuration().bounds) are automatically added to all target and desired regions before MCS computation.

- Current solver

MCS can be calculated via optlang using the currently active MILP solver.
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

With CPLEX or Gurobi as solver, MCS can also be enumerated by cardinality, i.e. all MCS of successively increasing size (up to max. size) are computed.
In addition, with these solvers a continuous search mode is possible which is similar to the any MCS method but usually much faster.

- Exclude boundary reactions as cuts

Do not allow knock-out of boundary reactions (reactions that cross the system boundary, e.g. exchange reactions).

- Consider constraints given by scenario

Take reaction bounds set by the current scenario into account for all target and desired regions.

#### Compute strain designs

Opens a dialog which serves as front-end of the [StrainDesign](https://github.com/klamt-lab/straindesign) package for MILP-based strain design computation which supports MCS, MCS with nested optimization, OptKnock, RobustKnock and OptCouple, GPR-rule integration, gene and reaction knockouts and additions as well as regulatory interventions. A detailed description can be found in its [documentation](https://straindesign.readthedocs.io/en/latest/).

### EFM/MCS Navigation and analysis

After the computation of EFM or MCS a navigation panel appears below the map. With this you can browse through the results, select a subset of the modes/MCS and show some statistics. There is also a button for saving the results and one to clear them and close the navigation panel.

![
**Mode/MCS Navigation Panel.**
](https://raw.githubusercontent.com/cnapy-org/CNApy-guide/main/content/images/mode-navigator.png "Mode/MCS Navigation Panel"){#fig:navigator}

- Select...

In this text field you can enter a comma-separated list of reaction IDs. After pressing "Enter" on the keyboard the subset of modes/MCS is shown in which all specified reactions occur. If you prepend a reaction ID with an exclamation mark (e.g. !R1) this means that the specified reaction must not participate in selected the modes/MCS. To revert the selection click on the clear button embedded in the text field.

- Reaction participation

Calculate the relative participation of each reaction in the currently selected modes/MCS. The results are shown in the reaction boxes and the "Flux" column of the reaction list.

- Size histogram

Calculate the pathway lengths/number of reactions of the currently selected modes/MCS. The result is shown as a size historam in the integrated Jupyter console.

### Flux optimization

Launches a dialog in which you can enter a linear expression (over the fluxes) that can then be maximized or minimized. The result is then displayed on the map(s) and the reaction list.
The flux values of the current scenario are taken into during the optimization.

### Yield optimization

Launches a dialog in which you can enter two linear expressions (over the fluxes), which serve as numerator/denominator of a linear fractional
program which then be maximized or minimized.
A typical application would be the maximization of a product yield: When the exchange fluxes for ethanol and glucose are *EX_etoh* and *EX_glc* then maximizing *EX_etoh/-EX_glc gives* the maximal ethanol yield on glucose.
For this to work correctly, there must be no flux vector in the network where the denominator becomes zero and the nominator is non-zero.
The result is then displayed on the map(s) and the reaction list.
The flux values of the current scenario are taken into during the optimization.

### Plot flux space

Launches a dialog in which you can configure a plot that shows the projection of the solution space in 2D or 3D where the axes can be flux expressions or yield expressions.
In the simplest case one can for example plot the growth rate against the substrate uptake rate.
The flux values of the current scenario are taken into account during the calculations.

### Show model stats

Shows the stoichiometric matrix and basic model properties on the console. In particular, the degrees of freedom of the stoichiometric matrix and the number of conservation relations are calculated for this.

### Net conversion of the external metabolites

Shows the conversion of external metabolites of the current flux distribution. Because there are no external metabolites in COBRApy models this conversion is derived from the rates through the boundary fluxes.

### Compute in/out fluxes at a metabolite

If a flux distribution has been calculated (e.g. by FBA) this function shows the magnitude of all fluxes going in/coming out of a specified metabolite.
The reaction fluxes are displayed as stacked bar graphs on the console.
You can either call this function from the Analysis menu and specify a metabolite or right-click on a metabolite in the list and call the function from the context menu.

### Clipboard calculator

![
**Clipboard calculator.**
](https://raw.githubusercontent.com/cnapy-org/CNApy-guide/main/content/images/clipboard-calculator.png "Clipboard calculator"){#fig:clipboard-calc}

The clipboard calculator allows you to perform arithmetic operations with the values stored in the clipboard, the current reaction rates or a fixed value that you can enter in this dialog.
The result of the operation replaces the current flux values.


### Programming CNApy

##### Under Construction

- accessing the COBRApy Model
- accessing scenario and computed values
- accessing the CNApy UI


## References {.page_break_before}

<!-- Explicitly insert bibliography here -->
<div id="refs"></div>
