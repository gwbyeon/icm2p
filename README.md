# icm2 data processing pipeline and analysis codes

**icm2** (in-cell mutate-and-map) is a method to characterize RNA structure inside cells. The experiment generates two-dimensional accessibility mapping data under cellular conditions. This code demonstrates how such data can be used to model RNA secondary structure ensembles. The input here is the .fastq files from Illumina sequencing run for an icm2 experiment. Outputs are a set of visualizations of the data and a set of secondary structures and their weights fitted by REEFFIT. The repository accompanies [PAPER CITATION HERE] and reproduces the analysis presented in the paper.

## Dependencies

Utilities 
```json
cutdapt
bowtie2
bbmap
samtools
bamtools
shapemapper2
viennarna
```

Python packages
```json
numpy
rdatkit
reeffit
```

R packages
```json
data.table
cowplot
tidyverse
scales
Biostrings
edgeR
limma
hues
viridis
impute
ggrepel
```

* Python packages rdatkit and reeffit should be installed and properly set up so that they can be called in the working environment. (see https://github.com/ribokit/RDATKit and https://github.com/ribokit/REEFFIT)

* Same goes for ViennaRNA package. Its standalone programs should be set up to be called from the environment.

### Usage

* The set of scripts here are used to do the following:
1. Pre-process and align the sequencing reads (p0.sh)
2. Make correlated mutation counts matrix (m2matrix.py)
3. Data visualization; clustering; output constraints (icm2.R)
4. Ensemble model fits (reeffit\_bootstrap\_run.sh)

* wrapper.sh and reeffit\_bootstrap\_run.sh contain slurm job execution commands

* bonus\_combined.dot is the set of 500 suboptimals sampled by RNAsubopt used as input to REEFFIT exactly for the paper.

* The parameters within each script were used to produce the analysis presented in the paper. The index are available under index/reference\*. The raw sequencing data can be downloaded from GEO under accession code GSE155656.

## Reference

[CITATION GOES HERE]
<hr/>

