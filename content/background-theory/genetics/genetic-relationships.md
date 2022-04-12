---
title: Genetic Relationships
pcx-content-type: tutorial
weight: 3
meta:
  title: Genetic Relationships
---

# Genetic Relationships
## Gametic Relationship Matrix

Gametic Relationship Matrix is used to find the probabilities that alleles are in common between individuals

Needs a genomic pedigree table to build

![genomic-pedigree-table.png](../media/genomic-pedigree-table.png)

![Gametic Relationship Matrix](../media/gametic-relationship.png)

Gametic Relationship Matrix

Say we want to calculated the contribution $A_m$ has on $C_m$ (sire of C) ($A_m,C_m$). We look at the genomic pedigree table and see that $C_m$ has parents $A_m$ and $A_f$. We then calculated:

$(A_m,C_m)=0.5*[(A_m,A_m)+(A_m,A_f)]$

$= 0.5 * [0 + 1]$

$= 0.5$

Which is to say 0.5 * [($A_m$s contribution to $A_m$) + ($A_m$s contribution to $A_f)]$

This can be done recursively as long as the animals are in chronological order.

Taking a look at the diagonal of the matrix. Any probabilities found in the top right or bottom left of a square is the inbreeding coefficient.

## Additive Genetic Relationships

Obtaining additive relationship matrix from gametic relationship matrix. Gives the expected genetic variances or covariance between animals

## Dominance Genetic Relationships

Was stated that isn’t important in genetic evaluation

## Epistatic Genetic Relationships

Was stated that isn’t important in genetic evaluation

## Meuwissen and Luo Algorithm for Inbreeding

Used to find inbreeding coefficients. Seems a bit complex