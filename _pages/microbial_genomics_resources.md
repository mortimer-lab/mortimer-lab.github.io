---
toc: true
toc_label: "Resources for analysis of microbial genomes"
toc_icon: "bacteria"
toc_sticky: true
permalink: /microbial_genomics/
title: ""
---

We have compiled a list of commonly used software and databases in microbial genomics. If you have additional contributions to this list or notice a mistake, please contact us!

# Assembly, Annotation, and Typing

## pipelines

### Bactopia
Bactopia is a pipeline for QC, de novo assembly, annotation, and typing of bacterial genomes from short or long reads.

[Bactopia Documentation](https://bactopia.github.io/)

[Petit et al. 2020](https://journals.asm.org/doi/10.1128/msystems.00190-20)

### snippy
Snippy is a pipeline for mapping sequencing reads to a reference genome and performing variant calling. Snippy will also create a core SNP alignment from multiple samples.

[Snippy Documentation](https://github.com/tseemann/snippy)

## de novo assembly

There are numerous options for de novo assembly software. Below are some of the common tools used in bacterial genomics projects.

### Short read assembly

#### SPAdes

[SPAdes Documentation](https://github.com/ablab/spades)

[Prjibelski et al. 2020](https://doi.org/10.1002/cpbi.102)

#### SKESA

[SKESA Documentation](https://github.com/ncbi/SKESA)

[Souvorov et al. 2018](https://doi.org/10.1186/s13059-018-1540-z)

### Long read assembly

#### Trycycler

[Trycycler Documentation](https://github.com/rrwick/Trycycler)

[Wick et al. 2021](https://doi.org/10.1186/s13059-021-02483-z)

#### Flye

[Flye Documentation](https://github.com/fenderglass/Flye)

[Kolmogorov et al. 2019](https://doi.org/10.1038/s41587-019-0072-8)

### Hybrid assembly

#### Unicycler

[Unicycler Documentation](https://github.com/rrwick/Unicycler)

[Wick et al. 2017](https://doi.org/10.1371/journal.pcbi.1005595)

## Reference guided assembly

Reference guided assembly requires choosing an appropriate reference genome, mapping short reads to the reference genome, and calling variants. Below are some popular tools for performing these steps.

### Choosing a reference

A closely related, finished reference genome is usually the best choice for mapping and variant calling. For some less diverse species, it is feasible to use a single reference across the species. However, for other species with high nucleotide diversity or large accessory genomes, a reference genome from the same lineage/sequence type/cluster will be most appropriate. When sequencing is performed as part of an experiment, the best choice is always a finished genome of the lab or parental strain used in the experiment.

### Mapping

#### BWA (short reads)

[BWA-MEM Documentation](https://github.com/lh3/bwa)

[Li. 2013](https://doi.org/10.48550/arXiv.1303.3997)

#### Minimap2 (long reads)

[Minimap2 Documentation](https://github.com/lh3/minimap2)

[Li. 2018](https://doi.org/10.1093/bioinformatics/bty191)

### Variant calling

#### Pilon

[Pilon Documentation](https://github.com/broadinstitute/pilon/wiki)

[Walker et al. 2014](https://doi.org/10.1371/journal.pone.0112963)

#### freebayes

[freebayes Documentation](https://github.com/freebayes/freebayes)

[Garrison and Marth. 2012](https://doi.org/10.48550/arXiv.1207.3907)

## Annotation

### Annotating assemblies

#### Prokka

[Prokka Documentation](https://github.com/tseemann/prokka)

[Seemann. 2014](https://doi.org/10.1093/bioinformatics/btu153)

#### bakta

[Bakta Documentation](https://github.com/oschwengers/bakta)

[Schwengers et al. 2021](https://doi.org/10.1099/mgen.0.000685)

#### NCBI Prokaryotic Genome Annotation Pipeline

[PGAP Documentation](https://github.com/ncbi/pgap)

[Li et al. 2021](https://doi.org/10.1093/nar/gkaa1105)

#### ggCaller

Rather than annotating individual genome assemblies, ggCaller uses pangenome graphs for annotation and clustering.

[ggCaller Documentation](https://github.com/samhorsfield96/ggCaller)

[Horsfield et al. 2023](https://doi.org/10.1101/gr.277733.123)

### Annotating variants in a VCF

#### SnpEff

[SnpEff Documentation](http://pcingola.github.io/SnpEff/)

[Cingolani et al. 2012](https://doi.org/10.4161%2Ffly.19695)

#### BCFtools

[BCFtools csq Documentation](http://www.htslib.org/doc/bcftools.html#csq)

[Danecek and McCarthy. 2017](https://doi.org/10.1093/bioinformatics/btx100)

## Typing

The following are general tools for typing bacterial genomes. However, often it is best to use a species-specific database or typing software.

### Sequence Typing

#### PubMLST

[PubMLST](https://pubmlst.org/) hosts databases for many species with various MLST schemes as well as whole genome sequencing data and typing. [BIGSdb](https://bigsdb.readthedocs.io/en/latest/) software and the [RESTful API](https://bigsdb.readthedocs.io/en/latest/rest.html) can be used to interact with PubMLST databases.

[Jolley et al. 2018](https://doi.org/10.12688/wellcomeopenres.14826.1)

#### ARIBA

[ARIBA](https://github.com/sanger-pathogens/ariba/wiki/MLST-calling-with-ARIBA) can be used for MLST typing directly from reads using PubMLST databases.

[Hunt et al. 2017](https://doi.org/10.1099/mgen.0.000131)

### Antimicrobial Resistance

#### ARIBA

[ARIBA](https://github.com/sanger-pathogens/ariba/wiki/) can be used to identify antimicrobial resistance genes and alleles directly from reads. ARIBA requires a reference dataset. Several generic dataset are [included](https://github.com/sanger-pathogens/ariba/wiki/Task%3A-getref); however, a species-specific reference dataset will produce the most accurate results.

[Hunt et al. 2017](https://doi.org/10.1099/mgen.0.000131)

#### NCBI's AMRFinderPlus

[AMRFinderPlus](https://github.com/ncbi/amr/wiki) indentifies antimicrobial resistance genes and mutations from assembled genomes. It additionally will detect genes associated with other phenotypes like virulence and metal resistance. 

[Feldgarden et al. 2021](https://doi.org/10.1038/s41598-021-91456-0)

# Alignment

## Short multiple sequence alignment

Many aligners are available for alignment of short nucleotide or amino acid sequences. This software generally does not scale to whole genome alignment.

### MAFFT

[MAFFT Documentation](https://mafft.cbrc.jp/alignment/software/)

[Katoh et al. 2002](https://doi.org/10.1093/nar/gkf436)

### PRANK

[PRANK Documentation](https://ariloytynoja.github.io/prank-msa/)

[Löytynoja. 2014](https://doi.org/10.1007/978-1-62703-646-7_10)

## Whole genome alignment

### Creating pseudogenomes from VCFs

If you have variant calls from several isolates mapped to the same reference genome, you can incorporate those variant calls into your reference to create pseudogenomes of the same length. These pseudogenomes can be concatenated into the same file to create an alignment. Creation of alignments from VCFs is often done with custom scripts. However, pipelines like [snippy](https://github.com/tseemann/snippy#core-snp-phylogeny) also incorporate this step. If you plan to write such a script, please keep the following in mind:

- You should not assume that the reference allele is supported if the VCF includes only variant sites. Missing data from regions with deletions, ambiguous calls, or low coverage should also be incorporated into the reference sequence; this often requires specifying that variant callers output all reference sites to a VCF rather than only variant sites.
- You should also filter variants based on coverage and quality in your script.
- It can also be useful to mask regions that are known to be problematic for short read mapping and variant calling such as repetitive regions. For example, PE/PPE genes are often excluded from alignments of *Mycobacterium* genomes.

### Alignment of assemblies

#### Parsnp
Parsnp creates a rapid core genome alignment from assemblies of closely related isolates.

[Parsnp Documentation](https://harvest.readthedocs.io/en/latest/content/parsnp.html)

[Treangen et al. 2014](https://doi.org/10.1186/s13059-014-0524-x)

#### Mugsy

[Mugsy Documentation](https://mugsy.sourceforge.net/)

[Angiuoli et al. 2011](https://doi.org/10.1093/bioinformatics/btq665)

#### Mauve

[Mauve Documentation](https://darlinglab.org/mauve/mauve.html)

[Darling et al. 2010](https://doi.org/10.1371/journal.pone.0011147)

### Pan Genome Analysis

Pan genome analysis software uses annotated assemblies to identify core and accessory genes, align sequences in the same orthogroup, and create a core genome alignment.

#### Panaroo

[Panaroo Documentation](https://gtonkinhill.github.io/panaroo/)

[Tonkin-Hill et al. 2020](https://doi.org/10.1186/s13059-020-02090-4)

#### Roary
Note: Roary is no longer being maintained. We have had difficulty installing via conda recently.

[Roary Documentation](https://sanger-pathogens.github.io/Roary/)

[Page et al. 2015](https://doi.org/10.1093/bioinformatics/btv421)

# Phylogenetic analysis

## Rapid tree inference
Phylogenetic trees can be rapidly estimated from core SNP alignments. However, branch lengths in SNP alignment based phylogenies will not be accurate. Some software, like IQ-TREE, includes the option to include counts of invariant sites in the model. See [this post](https://bitsandbugs.org/2019/11/06/two-easy-ways-to-run-iq-tree-with-the-correct-number-of-constant-sites/) from Phil Ashton for further information on this topic. 

### FastTree
If you are using FastTree for phylogenetic analysis of closely related microbial genomes, be sure to use the [double-precision version](http://www.microbesonline.org/fasttree/#BranchLen) of the software.

[FastTree Documentation](http://www.microbesonline.org/fasttree/)

[Price et al. 2010](https://doi.org/10.1371/journal.pone.0009490)

### IQ-TREE

[IQ-TREE Documentation](http://www.iqtree.org/)

[Nguyen et al. 2015](https://doi.org/10.1093/molbev/msu300)

## Recombination-corrected phylogenies

### Gubbins

[Gubbins Documentation](https://github.com/nickjcroucher/gubbins)

[Croucher et al. 2015](https://doi.org/10.1093/nar/gku1196)

### ClonalFrameML

[ClonalFrameML Documentation](https://github.com/xavierdidelot/ClonalFrameML)

[Didelot and Wilson. 2015](https://doi.org/10.1371/journal.pcbi.1004041)

## Dated phylogenies

### BactDating

[BactDating Documentation](https://xavierdidelot.github.io/BactDating/)

[Didelot et al. 2018](https://doi.org/10.1093/nar/gky783)

# Clustering

## Alignment based clustering

### fastbaps

[fastbaps Documentation](https://github.com/gtonkinhill/fastbaps)

[Tonkin-Hill et al. 2019](https://doi.org/10.1093/nar/gkz361)

## kmer based clustering

### PopPUNK

[PopPUNK Documentation](https://poppunk.readthedocs.io/en/latest/)

[Lees et al. 2019](https://doi.org/10.1101%2Fgr.241455.118)

## Typing based clustering

### MLST clustering

For some species, sequence types are assigned to clonal complexes or core genome MLST schemes are used to group isolates based on a fixed threshold of differences in core genome allele assignments.

# Genome Wide Association Studies

## Input data

### unitig-caller

[unitig-caller Documentation](https://github.com/bacpop/unitig-caller)

### panfeed

[panfeed Documentation](https://github.com/microbial-pangenomes-lab/panfeed)

[Sommer et al. 2023](https://doi.org/10.1099/mgen.0.001129)

## Linear Mixed Models

### pyseer

[pyseer Documentation](https://pyseer.readthedocs.io/en/master/)

[Lees et al. 2018](https://doi.org/10.1093/bioinformatics/bty539)

## Phylogeny-based GWAS

### treeWAS

[treeWAS Documentation](https://github.com/caitiecollins/treeWAS)

[Collins and Didelot. 2018](https://doi.org/10.1371/journal.pcbi.1005958)

# Data visualization

## Browser-based annnotated phylogenies

### Microreact

[Microreact Website](https://microreact.org/)

[Argimón et al. 2016](https://doi.org/10.1099%2Fmgen.0.000093)

### iTOL

[iTOL Website](https://itol.embl.de/)

[Letunic and Bork. 2021](https://doi.org/10.1093/nar/gkab301)

### Phandango

[Phandango Website](http://jameshadfield.github.io/phandango/#/)

[Hadfield et al. 2018](https://doi.org/10.1093/bioinformatics/btx610)

## Other tree visualization software

### ggtree (R)

[ggtree Documentation](https://bioconductor.org/packages/devel/bioc/vignettes/ggtree/inst/doc/ggtree.html)

[Yu. 2020](https://doi.org/10.1002/cpbi.96)

## Data visualization tips

[Friends Don't Let Friends](https://github.com/cxli233/FriendsDontLetFriends)

# Databases

## Querying Databases

### Searching bacterial genomes from ENA
Search >600k bacterial genomes (all sequenced genomes prior to 2019)

[Blackwell et al. 2022](https://doi.org/10.1099/acmi.ac2021.po0143)

[Břinda et al. 2023](https://doi.org/10.1101/2023.04.15.536996)

### Branchwater Metagenome Query
Search metagenomes from NBI's SRA

[Branchwater Metagenome Query](https://branchwater.sourmash.bio/)

# Species specific tools and tips

## *Neisseria gonorrhoeae*

### Databases and Tools

#### PubMLST
Note that the *N. gonorrhoeae* PubMLST database is combined with other *Neisseria*

[PubMLST Neisseria Database](https://pubmlst.org/organisms/neisseria-spp)

[Jolley et al. 2018](https://doi.org/10.12688/wellcomeopenres.14826.1)

[Harrison et al. 2020](https://doi.org/10.1093/infdis/jiaa002)

#### Pathogenwatch

[Pathogenwatch: *Neisseria gonorrhoeae*](https://pathogen.watch/genomes/all?genusId=482)

[Sánchez-Busó et al. 2021](https://doi.org/10.1186/s13073-021-00858-2)

#### NG-STAR

NG-STAR is a typing system based on antimicrobial resistance loci in *N. gonorrhoeae*.

[NG-STAR Database](https://ngstar.canada.ca/pages/welcome?lang=en)

[Demczuk et al. 2017](https://doi.org/10.1128/jcm.00100-17)

#### pyngoST

NG-STAR, MLST, and NG-MAST typing can be performed from genome assemblies using [pyngoST](https://github.com/leosanbu/pyngoST) from [Sánchez-Busó et al.](https://doi.org/10.1101/2023.10.23.563537).

### Divergent and mosaic alleles in *N. gonorrhoeae*

In addition to high rates of recombination within *N. gonorrhoeae*, gonococcus can also acquire alleles from other *Neisseria* species. In some cases, these mosaic alleles can be important contributors to antimicrobial resistance. Mosaic alleles are often divergent enough that reads will not map to a reference genome with a gonococcal allele at these loci (e.g. *penA*, *mtr*).

There are also two divergent alleles of *porB*, *porB1a* and *porB1b*. Most gonococcal isolates encode *porB1b*; however, be aware that reads from an isolate with *porB1a* will not map well to a reference genome with *porB1b*.

Mosaic and divergent alleles can be assessed using de novo assemblies.

### Repetitive and phase variable loci in *N. gonorrhoeae*

*N. gonorrhoeae* employs both antigenic and phase variation facilitated by repetitive sequences across the genome (e.g. *pilE*/*pilS* and *opa* genes) and low complexity regions within genes. These sequences can be difficult to resolve depending on the read length and accuracy of the sequencing technology used.

*N. gonorrhoeae* also encodes four copies of the 23S rRNA locus. These copies cannot be resolved during assembly of short read sequencing data. If it is important to know the sequence of all four copies (e.g. for identification of azithromycin resistance associated mutations), you can use long read sequencing or map short reads to a single copy of the 23S rRNA sequence and use allele frequencies to identify the number of copies of particular mutation.

### Plasmids and mobile elements in *N. gonorrhoeae*

Most *N. gonorrhoeae* isolates encode a small cryptic plasmid. Additionally, *N. gonorrhoeae* can carry plasmids encoding antimicrobial resistance. A small, mobilizable plasmid encoding *blaTEM* confers high level resistance to pencillin. This plasmid can be difficult to assembly using short read data because of repetitive elements, and contig breaks can occur in the middle of the *bla* gene. Small plasmid like the cryptic plasmid and *blaTEM* plasmid can also be lost during Nanopore long read sequencing due to selection for long DNA fragments. Conjugative plasmids, most carrying the tetracycline-resistance conferring gene *tetM*, can also be found in many *N. gonorrhoeae* lineages.

Most *N. gonorrhoeae* also encode nine prophage within their genomes, and many additionally carry the Gonococcal Genetic Island, a mobile element integrated into the chromosome which encodes a Type IV Secretion System.
