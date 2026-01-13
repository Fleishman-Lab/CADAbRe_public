# CUMAb
Licensed under the Non-Profit Open Software License version 3.0.

This repository contains the RosettaScripts xmls needed to run CADAbRe. The method is described in our preprint ([Link to paper](https://www.biorxiv.org/content/10.64898/2025.12.10.693474v1)). Questions, comments, and suggestions can be sent to ariel.tennenhouse@weizmann.ac.il.

## Citations
Please cite our preprint as well as IMGT 
- Giudicelli, V., Chaume, D. & Lefranc, M.-P. IMGT/GENE-DB: a comprehensive database for human and mouse immunoglobulin and T cell receptor genes. Nucleic Acids Res. 33, D256–61 (2005).
- Tennenhouse, A. et al. Structure-based design of antibody repertoires with drug-like properties. bioRxiv https://doi.org/10.64898/2025.12.10.693474 (2025).

## Installation
You will need to either have Rosetta installed or install it from http://www.rosettacommons.org. CADAbRe uses git version d9d4d5dd3fd516db1ad41b302d147ca0ccd78abd
<br>
<br>You will need to download the IMGT databases of antibody germline sequences. Please save them under a folder called "IMGT_databases" in 6 separate files ("IGHV.fasta", "IGHJ.fasta", "IGKV.fasta", "IGKJ.fasta", "IGLJ.fasta", "IGKJ.fasta"). 
<br>They are available from the following URLs:
  - [IGHV](https://www.imgt.org/genedb/GENElect?query=7.6+IGHV&species=Homo+sapiens)
  - [IGHJ](https://www.imgt.org/genedb/GENElect?query=7.6+IGHJ&species=Homo+sapiens)
  - [IGKV](https://www.imgt.org/genedb/GENElect?query=7.6+IGKV&species=Homo+sapiens)
  - [IGKJ](https://www.imgt.org/genedb/GENElect?query=7.6+IGKJ&species=Homo+sapiens)
  - [IGLV](https://www.imgt.org/genedb/GENElect?query=7.6+IGLV&species=Homo+sapiens)
  - [IGLJ](https://www.imgt.org/genedb/GENElect?query=7.6+IGLJ&species=Homo+sapiens)
<br>
