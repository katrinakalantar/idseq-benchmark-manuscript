# idseq-benchmark-manuscript

## Overview

This directory contains scripts required for the analyses presented in the manuscript: *IDseq – An Open Source Cloud-based Pipeline and Analysis Service for Metagenomic Pathogen Detection and Monitoring* <https://idseq.net>.

This represents a snapshot in time analyzing results from IDseq pipeline v 3.13. As outlined in the manuscript, the up-to-date documentation on IDseq can be found in the project repositories (listed below) with user-facing documentation available at <https://help.idseq.net> . 
- <https://github.com/chanzuckerberg/idseq-dag>
- <https://github.com/chanzuckerberg/idseq-web>
- <https://github.com/chanzuckerberg/idseq-bench>


## Organization

Directory Structure : 
   * The `/results_scripts` directory contains the raw data, scripts, and output. 
       * The `/data` directory contains the raw data for each of the benchmarks.
       * The `/meta-tax-bakeoff` directory is a copy of <https://https://github.com/yesimon/metax_bakeoff_2019>, in which the *Metagenomics Bench* script is used for generation of benchmark metrics. Data published by Ye. et al is unchanged. note: only the metrics and plotting functionality is added here. 
       * The `/output` directory contains some of the interim figures that were combined into Figures 3 and S2.
       * The scripts (`Generate IDseq Results.ipynb`, `Figure3.ipynb`, `Figure4.ipynb`, `Supp. Benchmark Datasets`) are used to process output data and generate analyses, metrics, and plots included in the manuscript (See *Analysis Workflow* below).
   * The `/figures` directory contaings the final figures.
       

## Analysis Workflow

The following steps were used to perform the benchmarking analyses:

1. Download IDseq reports from IDseq Project: **Cell Reports Benchmarking Metagenomics Tools**.
2. Run **Generate IDseq Results.ipynb** to generate input file comparable to Ye et al format.
3. Run **Metagenomics Bench.ipynb** in `metatax_bakeoff_2019/plotting` directory to obtain benchmark metrics (AUPR, F1-score, Precision, Recall, etc.). The metrics calculated by this script are output to files that are plotted independently for the idseq-benchmark-manuscript.
4. Run **Figure3.ipynb** to take in the benchmark metrics and output plots, which make up Figure 3 and Figure S2.
5. Run **Figure4.ipynb** to take in the results from running kraken2 and IDseq on the Divergent Rhinovirus C dataset and plot the recall results.



### License 
MIT
