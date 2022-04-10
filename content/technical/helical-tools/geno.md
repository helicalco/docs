---
title: Geno
pcx-content-type: tutorial
weight: 2
meta:
  title: Geno
---

# Geno

## Getting Started

This tutorial will walk you through the process of running `helical geno` commands. We will begin with analysing a geno file and understanding the different files that are created. To begin, download the genotypes file below. This file is not a representation of any population. It is a generated file.

### genotype File

A file that holds the genotype data for animals. It is arranged in a matrix where each row represents a different animal and each column represents a different marker (SNP). The first column is the animal identifier.

<a href="/geno/genos" download>Here</a> is the sample geno file we will be using for this tutorial.

### .map File

Pairs with a .geno file and holds information about the markers. The first column is an identifier for the marker. The second column is the chromosome number. The third column is the position on the chromosome.

<a href="/geno/genos.map" download>Here</a> is the sample map file we will be using for this tutorial.

### Notes

From this point on, I am going to assume you have downloaded a file called genotypes.

## Analyse

With the geno file we may want a summary of the data. This can be done with the `analyse` command.

```sh
$ helical geno analyse genotypes
```

You should get this output:

```
Individuals:                     20
Individuals with no missing loci: 0
Markers:                         1,000
SNPs:                            50
Loci with no missing:            0
Average MAF:                     0.3680
+-----+-------+------+-----------+-------------+----------+------------+
| SNP | COUNT | PROP | GENO MEAN | GENO STDDEV | SNP MEAN | SNP STDDEV |
+-----+-------+------+-----------+-------------+----------+------------+
| AA  | 246   | 0.25 | 12.30     | 3.53        | 4.92     | 1.89       |
| AB  | 244   | 0.24 | 12.20     | 3.64        | 4.88     | 1.59       |
| BB  | 277   | 0.28 | 13.85     | 3.45        | 5.54     | 2.12       |
| NC  | 233   | 0.23 | 11.65     | 3.12        | 4.66     | 1.88       |
+-----+-------+------+-----------+-------------+----------+------------+
```

- SNPs: signifies how many snps are found for each individual.
- Average MAF: the average minor allele frequency.
- Markers: the total amount of snps in the file.

Then there is a summary of each potential combination of alleles (AA, AB, BB, NC(No Call)).
For each combination there is a geno mean which signifies the average of that given allele found in a row/individual. There is also a snp mean which is the average of all the snps found in a column/snp.

If you want more details you can specifify a directory to store additional files. Lets store them in a temporary folder in the current working directory.

```sh
$ helical geno analyse genotypes -d temp/geno
```

If you head over to your temp folder you should see a folder called geno.

```sh
$ cd temp/geno
```

And listing it - `ls .` - should show you the following files:

```
genotype_report.txt  outliers.txt  snp_report.txt  summary.txt
```

The summary.txt is the exact same thing you've seen above.
If you want some more information on snps, take a look at snp_report.txt.

```sh
$ cat snp_report.txt
```

This will yield the output we want, but it'll be in poor format. This is a good example of how `column` comes in handy.

```shU
$ column -t snp_report.txt
```

Here's the first few lines of the output to be expected:

```
SnpID     MAF   #AA  #AB  #BB  #NC  %AA   %AB   %BB   %NC
SNP00001  0.33  4    5    4    7    0.20  0.25  0.20  0.35
SNP00002  0.53  7    7    4    2    0.35  0.35  0.20  0.10
SNP00003  0.28  3    5    7    5    0.15  0.25  0.35  0.25
...
```

This file shows the number of alleles, their proportions and the minor allele frequency for each snp.

The `genotype_report.txt` file holds the same information as above, except it's based on each genotype instead, and has a callrate column,
which is a measure of the proportion of individuals that have a valid allele (not an NC).

Here's a snippet of the file:

```
ID      CallRate  #AA  #AB  #BB  #NC  %AA   %AB   %BB   %NC
geno19  0.660000  11   9    13   17   0.22  0.18  0.26  0.34
geno15  0.740000  11   6    20   13   0.22  0.12  0.40  0.26
geno6   0.840000  15   17   10   8    0.30  0.34  0.20  0.16
...
```

And finally, there is outliers.txt, which shows the individuals who's mean of any snp count falls outside 2 standard deviations of the mean.
