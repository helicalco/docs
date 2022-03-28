---
title: Geno
pcx-content-type: tutorial
weight: 2
meta:
  title: Geno
---

# Geno

## Getting Started

### genotype File

A file that holds the genotype data for animals. It is arranged in a matrix where each row represents a different animal and each column represents a different marker (SNP). The first column will be an identifier for the animal.

<a href="../../../downloads/genos" download>Here</a> is the sample geno file we will be using for this tutorial.

### .map File

Pairs with a .geno file and holds information about the markers. The first column is an identifier for the marker. The second column is the chromosome number. The third column is the position on the chromosome.

<a href="../../../downloads/genos.map" download>Here</a> is the sample map file we will be using for this tutorial.

## Analyse

With the geno file we may want a summary of the data. This can be done with the `analyse` command.

```sh
$ helical geno analyse path/to/genos/file
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

- Snps: signifies how many snps are found for each individual.
- Average MAF: the average minor allele frequency.
- Markers: the total amount of snps in the file.

Then there is a summary of each potential combination of alleles (AA, AB, BB, NC(not counted)).
For each combination there is a geno mean which signifies the average of that given allele found in a row/individual. There is also a snp mean which is the average of all the snps found in a column/snp.

If you want more details you can specifify a directory to store additional files. Lets store them in your Documents folder.

```sh
$ helical geno analyse path/to/genos/file -d ~/Documents/geno
```

If you head over to your Documents folder you should see a folder called geno.

```sh
$ cd ~/Documents/geno
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

```sh
$ column -t snp_report.txt
```

Giving you this output:

```
SnpID     MAF   #AA  #AB  #BB  #NC  %AA   %AB   %BB   %NC
SNP00001  0.33  4    5    4    7    0.20  0.25  0.20  0.35
SNP00002  0.53  7    7    4    2    0.35  0.35  0.20  0.10
SNP00003  0.28  3    5    7    5    0.15  0.25  0.35  0.25
SNP00004  0.35  4    6    4    6    0.20  0.30  0.20  0.30
SNP00005  0.47  6    7    3    4    0.30  0.35  0.15  0.20
SNP00006  0.47  5    9    3    3    0.25  0.45  0.15  0.15
SNP00007  0.47  8    3    2    7    0.40  0.15  0.10  0.35
SNP00008  0.47  7    5    4    4    0.35  0.25  0.20  0.20
SNP00009  0.25  3    4    7    6    0.15  0.20  0.35  0.30
SNP00010  0.25  2    6    8    4    0.10  0.30  0.40  0.20
SNP00011  0.38  6    3    5    6    0.30  0.15  0.25  0.30
SNP00012  0.35  6    2    4    8    0.30  0.10  0.20  0.40
SNP00013  0.30  4    4    4    8    0.20  0.20  0.20  0.40
SNP00014  0.35  4    6    5    5    0.20  0.30  0.25  0.25
SNP00015  0.23  3    3    4    10   0.15  0.15  0.20  0.50
SNP00016  0.35  5    4    6    5    0.25  0.20  0.30  0.25
SNP00017  0.50  7    6    4    3    0.35  0.30  0.20  0.15
SNP00018  0.30  3    6    6    5    0.15  0.30  0.30  0.25
SNP00019  0.38  5    5    9    1    0.25  0.25  0.45  0.05
SNP00020  0.45  5    8    5    2    0.25  0.40  0.25  0.10
SNP00021  0.33  5    3    5    7    0.25  0.15  0.25  0.35
SNP00022  0.12  0    5    12   3    0.00  0.25  0.60  0.15
SNP00023  0.42  6    5    4    5    0.30  0.25  0.20  0.25
SNP00024  0.47  7    5    4    4    0.35  0.25  0.20  0.20
SNP00025  0.45  7    4    5    4    0.35  0.20  0.25  0.20
SNP00026  0.45  7    4    5    4    0.35  0.20  0.25  0.20
SNP00027  0.33  4    5    7    4    0.20  0.25  0.35  0.20
SNP00028  0.35  5    4    9    2    0.25  0.20  0.45  0.10
SNP00029  0.50  7    6    3    4    0.35  0.30  0.15  0.20
SNP00030  0.40  5    6    3    6    0.25  0.30  0.15  0.30
SNP00031  0.60  10   4    2    4    0.50  0.20  0.10  0.20
SNP00032  0.38  4    7    6    3    0.20  0.35  0.30  0.15
SNP00033  0.28  2    7    8    3    0.10  0.35  0.40  0.15
SNP00034  0.17  2    3    8    7    0.10  0.15  0.40  0.35
SNP00035  0.25  4    2    11   3    0.20  0.10  0.55  0.15
SNP00036  0.38  5    5    6    4    0.25  0.25  0.30  0.20
SNP00037  0.50  9    2    3    6    0.45  0.10  0.15  0.30
SNP00038  0.38  5    5    5    5    0.25  0.25  0.25  0.25
SNP00039  0.35  5    4    8    3    0.25  0.20  0.40  0.15
SNP00040  0.38  4    7    7    2    0.20  0.35  0.35  0.10
SNP00041  0.40  6    4    5    5    0.30  0.20  0.25  0.25
SNP00042  0.40  6    4    6    4    0.30  0.20  0.30  0.20
SNP00043  0.23  3    3    8    6    0.15  0.15  0.40  0.30
SNP00044  0.35  5    4    6    5    0.25  0.20  0.30  0.25
SNP00045  0.25  3    4    6    7    0.15  0.20  0.30  0.35
SNP00046  0.33  3    7    6    4    0.15  0.35  0.30  0.20
SNP00047  0.42  6    5    6    3    0.30  0.25  0.30  0.15
SNP00048  0.47  6    7    5    2    0.30  0.35  0.25  0.10
SNP00049  0.30  4    4    5    7    0.20  0.20  0.25  0.35
SNP00050  0.33  4    5    5    6    0.20  0.25  0.25  0.30
```

This file shows the number of alleles, their proportions and the minor allele frequency for each snp.

The genotype_report.txt file holds the same information as above, except it's based on each genotype instead, and has a callrate column,
which is a measure of the proportion of individuals that have a valid allele (not an NC).

```
ID      CallRate  #AA  #AB  #BB  #NC  %AA   %AB   %BB   %NC
geno19  0.660000  11   9    13   17   0.22  0.18  0.26  0.34
geno15  0.740000  11   6    20   13   0.22  0.12  0.40  0.26
geno6   0.840000  15   17   10   8    0.30  0.34  0.20  0.16
geno16  0.760000  11   11   16   12   0.22  0.22  0.32  0.24
geno17  0.860000  17   9    17   7    0.34  0.18  0.34  0.14
geno10  0.820000  11   14   16   9    0.22  0.28  0.32  0.18
geno7   0.640000  8    15   9    18   0.16  0.30  0.18  0.36
geno13  0.740000  8    13   16   13   0.16  0.26  0.32  0.26
geno3   0.760000  14   13   11   12   0.28  0.26  0.22  0.24
geno1   0.820000  15   13   13   9    0.30  0.26  0.26  0.18
geno12  0.720000  21   7    8    14   0.42  0.14  0.16  0.28
geno8   0.700000  15   8    12   15   0.30  0.16  0.24  0.30
geno11  0.800000  9    18   13   10   0.18  0.36  0.26  0.20
geno14  0.720000  10   8    18   14   0.20  0.16  0.36  0.28
geno18  0.780000  16   10   13   11   0.32  0.20  0.26  0.22
geno2   0.820000  11   12   18   9    0.22  0.24  0.36  0.18
geno9   0.800000  9    12   19   10   0.18  0.24  0.38  0.20
geno4   0.780000  11   17   11   11   0.22  0.34  0.22  0.22
geno5   0.860000  15   17   11   7    0.30  0.34  0.22  0.14
geno0   0.720000  8    15   13   14   0.16  0.30  0.26  0.28
```

And finally, there is outliers.txt, which shows the individuals who's mean of any snp count falls outside 2 standard deviations of the mean.
