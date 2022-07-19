# CrispRstats

Mapping of reads and quantification of invalidation: 

Sequencing reads are mapped to the current Reference Human Genome (Human GRCh38/hg38) with minimap2. Resulting .bam files are then explored in the genomic region corresponding to the targeted region for each gene. This region ranges from -100 bp relative to the most downstream sgRNA to +100 bp to the most upstream sgRNA. Within this region, make the sum all sequencing reads that have deletions of at least 5 bp compared to the reference genome. This 5 bp threshold was chosen because it is the minimal size deletion which is not detected in control (scrambled) condition, due to sequencing errors. For each targeted gene, the ratio between the sum of deleted reads and the sum of total reads to obtain invalidation efficiency. 

# Installation

just copy files.

requires: 

* Java 8


# Run analysis

```

git clone https://github.com/ucagenomix/CrispRstats.git
cd CrispRstats
java -jar -Xmx4g sicelore-2.jar CrispRstats INPUT=yourfile.bam HISTO=histo.txt DETAIL=detail.txt MINSIZE=5 COORD=X:15557125-15581029

```
