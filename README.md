# genome_topology
Topological analysis of genome folds based on Circuit Topology (CT) and Network Topology

Cite the code: [![DOI](https://zenodo.org/badge/428377249.svg)](https://zenodo.org/badge/latestdoi/428377249)

This package contains tools for Circuit Topology analysis pipeline of genomic structures, as presented in the paper 

Barbara Scalvini, Helmut Schiessel, Anatoly Golovnev, Alireza Mashaghi, Circuit topology analysis of cellular genome reveals signature motifs, conformational heterogeneity, and scaling, iScience, Volume 25, Issue 3, 2022, 103866, https://doi.org/10.1016/j.isci.2022.103866.

and the method chapter 

Barbara Scalvini and Alireza Mashaghi, Circuit topology analysis of single cell HiC data. Methods in Molecular Biology (2024). Publisher: Springer Nature - in preparation.

1. Accepted data formats:
The pipeline is available for PDB files containing 3D models of single-cell chromosomes. In the folder 'Hi-C maps' you can find some functions and example notebooks 
for analysis of Hi-C maps (both single-cell and population). In this case the accepted format is a txt list of contact indexes and frequencies ( you can use freely
available softwares such as Juicebox to extract a similar txt file from your Hi-C data).

2. Instructions:
Start your analysis with the 'ExtractTopology' notebook. This notebook will process your raw data and produce Ciruit Topology fractions (S%, P%, X%), Network Clustering Coefficient 
and Fractal dimension for each chromosome in your dataset. You can store this data in csv files. Also, a Topology matrix will be produced, which can be saved in TIFF file. 
The information stored in the topology matrix can be projected back onto the contact map of the chromosome with 'TopologyToContactMap.ipynb'.
- STATISTICAL ANALYSIS:
Once you have processed data stored in csv files, you can perform statistical analysis on it, with the notebook 'Process_allcells'.
 
- CUMULATIVE ANALYSIS:
 'CTforCumulative analysis.py' produces the cumulative trace of CT parameters from PDB chromosome structures. Chromosomes are sectioned into subsequently bigger portions, 
 starting from the left end of the chain. The code produces a series of CT parameters, including Fractal dimension. The data is then printed on csv file, which can be further 
 analyzed with the 'Cumulative_analysis' notebook, to find local maxima and convergence threshold of the CT traces.

- MATRIX ANALYSIS:
 The patterns present in the topology matrix can further be analyzed with 'L_pattern_analysis.ipynb'. Here you can do quantile analysis on the size of the patterns.
 
- LOCAL ANALYSIS:
You can split your chromosomes into segments to perform local topological analysis with 'Matrices_segments.ipynb'. The resulting matrices can be analyzed with 
'Local_matrix_analysis.ipynb'. This notebook will produce bar codes which quantify contact and pattern density in local regions of your chromosome.
 
 3. Other features
 - 'Brownian_motion.ipynb' produces random chains by Brownian motion simulation. It calculates the Circuit Topology matrix from the randomly generated chains.
 - The Hi-C map folder also contains tools to bin RNA-seq data, to couple with Topology parameters. Start with 'bin_RNAseq.ipynb' and do the coupling with 
 'CoupleRNAseq_CT.ipynb'. RNA-seq data can be found at the Gene Expression Omnibus (GEO) repository under accession code GSE80280.
 
