# CADAbRe
Licensed under the Non-Profit Open Software License version 3.0.

This repository contains the RosettaScripts xmls needed to run the CADAbRe design steps and some examples. The method is described in our preprint ([Link to paper](https://www.biorxiv.org/content/10.64898/2025.12.10.693474v1)). Questions, comments, and suggestions can be sent to ariel.tennenhouse@weizmann.ac.il.

## Citations
Please cite our preprint, the paper defining the CDR H3 residue frequencies, HuCAL PLATINUM, and RosettaScripts 
- Tennenhouse, A. et al. Structure-based design of antibody repertoires with drug-like properties. bioRxiv (2025).
- Zemlin, M. et al. Expressed Murine and Human CDR-H3 Intervals of Equal Length Exhibit Distinct Repertoires that Differ in their Amino Acid Composition and Predicted Range of Structures. J. Mol. Biol. (2003). 
- Prassler, J. et al. HuCAL PLATINUM, a synthetic Fab library optimized for sequence diversity and superior performance in mammalian expression systems. J. Mol. Biol. (2011).
- Fleishman, S. J. et al. RosettaScripts: a scripting language interface to the Rosetta macromolecular modeling suite. PLoS One 6, e20161 (2011).

## Installation
You will need to either have Rosetta installed or install it from http://www.rosettacommons.org. CADAbRe uses git version d9d4d5dd3fd516db1ad41b302d147ca0ccd78abd

## Running CADAbRe
A flags file called "flags" is provided. The Rosetta database needs to be updated to the location of the Rosetta database corresponding to the Rosetta executable used. 

### Step 1: Relax the structure of the parental antibody
We recommend relaxing the parental structures before design. A RosettaScripts xml for running the relax can be found at xmls/Relax.xml, and example pdbs can be found in examples/example_pdbs. Please note that in our CADAbRe protocol, we run the initial relax 15 times and take the lowest-scoring one. The output for the example pdbs can be found in examples/example_pdbs_relaxed. Each relax job should take about 15 minutes to run on one CPU. 

### Step 2: Threading combinations of human germlines on each parental structure
An example xml for running the threading can be found at xmls/CADAbRe.xml. Examples of several germline combinations threaded on the relaxed structure of PDB ID 3NAA can be found in examples/example_pdbs_threaded. Each threading job should take about 5 minutes to run on one CPU. 

### Step 3: Selecting combinations of frameworks that freely combine to give diverse, low-energy structures
A jupyter notebook for training EpiNNet can be found at https://github.com/Fleishman-Lab/htFuncLib-web-server (htFuncLib.ipynb)

### Step 4: Selecting allowed CDR H3 point mutations based on each selected stucture
Example xmls for running the alanine scan and hydrogen-bond scan can be found at xmls/alascan.xml and xmls/alascan_Hbond.xml, respectively. Files summarizing the results from the alanine and hydrogen-bond scan on PDB ID 3NAA can be found at examples/example_scanning_summaries/3naa_alascan.log and examples/example_scanning_summaries/3naa_Hbond.log, respectively. Each position should take about one minute to run on one CPU. 

An example xml for modeling all allowed point CDR H3 point mutations can be found at xmls/filterscan.xml. An example file summarizing the mutations allowed at each CDR H3 position based on the per-residue frequency data for PDB ID 3NAA can be found at examples/example_scanning_summaries/3naa_allowd_muts.resfile. The per-position residue frequency data is summarized in "H3_per_res_AA_freqs_data.csv". A file summarizing the results for PDB ID 3NAA can be found at examples/example_scanning_summaries/3naa_4.resfile. Each mutation modeled at each position should take about one minute to run on one CPU. 

### Step 5: Combinatorial enumaration of allowed point mutations based on each selected structure
An example xml for running the combinatorial enumeration can be found at xmls/H3_combinatorial_enumeration.xml. An example pdb file created for a design based on PDB ID 3NAA can be found at examples/example_H3_design/3naa_example_H3_design.pdb.gz. Each design job should take about two minutes to run on one CPU. 
