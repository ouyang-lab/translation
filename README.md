# Translation Paper Datasets
We constructed the dataset of mouse embryonic stem cells (mESCs) with the generated RNA sequence and structure features of 4,244 transcripts. The dataset includes 219 sequence features and 136 structure features for each transcript. The data to generate the in vivo and in vitro structure features were from the icSHAPE data by Spitale et.al. [1]. How these features were generated are described in the supplementary materials. The dataset includes 2,122 transcripts as the positive dataset because of their high (top 25%) translation efficiency (TE), and the other 2,122 transcripts as the negative dataset with low (bottom 25%) TE. The TE of each transcript was calculated from the RNA-seq and Ribo-seq data from the mESC by Ingolia et.al. [2]. Please check the subsection Methods for details about the TE calculation.

We constructed the dataset of zebrafish developmental stages with the same feature set as the mESCs data. The positive and the negative dataset each has 368 transcripts in total.  The data to generate the in vivo and in vitro structure features were from the DMS-seq data by Beaudoin et al. [3]. The TE of each transcript was calculated from the RNA-seq and Ribo-seq data from Beaudoin et al. [3] as well.


## musESC_combined_tab_top_bot_25.txt

This file includes the RNA sequence and structure features as well as the translation efficiency (TE) of the transcripts that belong to the top and bottom 25% TE group in mouse embryonic stem cells.


## zbfish_top_bot_25_combined_tab_6hpf.txt

This file includes the RNA sequence and structure features as well as the translation efficiency (TE) of the transcripts that belong to the top and bottom 25% TE group in zebrafish embryos.


## Feature descriptions


### 1.1 219 Sequence Features
We investigated 4 segments for each transcript, the 5’ UTR, the CDS head region that is the first 6 codons from the translation initiation site, the rest of CDS region after removing the CDS head region from the entire CDS, and the 3’ UTR. 

#### 1.1.1 Nucleotide frequency, codon frequency, and amino acid frequency
The nucleotide frequency is calculated as the ratio of the number of a specific nucleotide in a defined region on the transcript and the total number of nucleotides within the corresponding region. There are 4 types of nucleotide and 4 investigated regions on a transcript, therefore there are in total 16 nucleotide frequency features.
There are two groups of features in the codon frequency category. The first group of features is defined similarly as the nucleotide frequency, which is calculated as the ratio of the number of a type of codon in a defined region on the transcript and the total number of codons within the corresponding region. The second group of features is defined as the relative frequency of codons with a specific nucleotide as its first, second and third position, respectively. For example, within the 6 codons (“ACT”, “AGC”, “TCT”, “TCG”, “CCC”, and “CTT”) in the CDS head region of a transcript, 2 of them (“ACT” and “AGC”) have nucleotide “A” at their first position, then the corresponding feature codon-1st-A feature (nucleotide “A” at the first position of the codon) is calculated as 2/6=0.333. There are 64 different types of codons and 4 possible nucleotides at each of the 3 positions in one codon. Considering the CDS head region and the rest of CDS region, we got 152 (64 codons*2 regions + 4 nucleotide * 3 positions per codon * 2 regions = 152) features in total.
The amino acid frequency is defined as the ratio of the number of a type of amino acid in a defined region on the transcript and the total number of amino acids within the corresponding region. Including the stop codon, there are 21 amino acid frequency features for each CDS region. Therefore, there are in total 42 amino acid frequency features.
There are in total 210 features in this category.

#### 1.1.2 GC content
We calculated the GC content in the 4 different regions for each transcript. There are 4 features in this category.

#### 1.1.3 Codon repetitive rate and amino acid repetitive rate
Codon repetitive rate is defined as the averaged frequency of a codon presented in a sequence. Similarly, the amino acid repetitive rate is defined as the averaged frequency of an amino acid presented in a sequence.
There are 2 features in total in this category.

#### 1.1.4 The lengths of CDS and UTRs
The length of 5’ UTR, CDS and 3’ UTR.
There are 3 features in total in this category.

### 1.2 136 Structure Features
#### 1.2.1 in vivo structure
We got 20 features from each of the 5’ UTR, the CDS and the 3’ UTR of a transcript. We also got 6 features from the CDS head region.
There are 66 features in total in this category.

#### 1.2.2 in vitro structure
Similar as the in vivo feature, there are 66 features in total in this category.

#### 1.2.3 in silico structure
We calculated the minimum free energy of the 5’ UTR, the CDS head region, the rest of the CDS region, and the 3’ UTR.
In total, there are 4 features in this category.


# References

1.	Spitale RC, Flynn RA, Zhang QC, Crisalli P, Lee B, Jung JW, Kuchelmeister HY, Batista PJ, Torre EA, Kool ET et al: Structural imprints in vivo decode RNA regulatory mechanisms. Nature 2015, 519(7544):486-490.
2.	Ingolia NT, Lareau LF, Weissman JS: Ribosome profiling of mouse embryonic stem cells reveals the complexity and dynamics of mammalian proteomes. Cell 2011, 147(4):789-802.
3.	Beaudoin JD, Novoa EM, Vejnar CE, Yartseva V, Takacs CM, Kellis M, Giraldez AJ: Analyses of mRNA structure dynamics identify embryonic gene regulatory programs. Nat Struct Mol Biol 2018, 25(8):677-686.


