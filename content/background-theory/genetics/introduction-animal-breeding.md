---
title: Introduction to Animal Breeding
pcx-content-type: tutorial
weight: 1
meta:
  title: Introduction to Animal Breeding
---

# Introduction Animal Breeding

## Note all questions are posed in regards to genetic evaluation unless stated otherwise

- Successful animal breeding requires
    - The collection and storage of data on individually identified animals
    - complete pedigree information about the sire and dam of each animal
    - appropriate statistical methods and computing hardware
- What percentage of your herd should be recorded?
    - Ideally all animals should be recorded following the International Committee on Animal Recording guidelines.

## What to do with the information

- How are animals ranked
    - On their Estimated Breeding Value (EBV)
    - What does an EBV incorporated
        - Records on the animal
        - Information on the sire and dam of the animal
        - Information on all progeny of that animal
- What are animals evaluated on?
    - Different traits, usually several which are then weighted by their relative economic values

## Mendelian Inheritance

- Locus
    - Specific, fixed position on a chromosome where a particular gene or genetic marker is located (can refer to the location of anything in the genome)
    - Plural = loci
- What is Mendelian Inheritance
    
    What we learned at school. The idea is that a genotype from a sire and a genotype from a dam will be combinated to give chances to get a new certain genotype. That given genotype would then be the reference for the phenotype.
    
    ![punnet-square.png](../media/punnet-square.png)
    

## Inifinitesimal Model

A trait is influence by an infinitely large number of genes, which make an infinitely small contribution to the phenotype.

- How do genetic evaluation models take this into account?
    - They assume that there are an infinite number of loci affecting each trait called quantitative trait loci (QTL). The goal is to estimate the combined effect of all loci for each trait on each animal.
- What is a major gene
    - Individual loci that have large effects on trait
        - Costs to much to use in current models and there are still questions as to minor genes influencing major genes

## Gene Action

- Influence of alleles on others when sharing a genotype

Suppose there is a gene locus that contributes to the growth of animals. Assume $A_1$, contributes to 50 grams of weight at birth, $A_2$ 30, and $A_3$ 5.

- Additive
    - $A_1 +A_2$ would be 80 grams and $A_2+A_3$ would be 35 grams and so on...
- Dominance
    - Additional effects on traits when certain alleles are in combination.
        - When $A_1$ combinates with $A_2$ there is an additional 10 grams of weight
- Epistasis
    - Interaction between different loci causing change in a trait. For instance $A_1A_2$ occurs while $B_3B_7$ exists will result in a lost of 5 grams to weight.
- What does this mean for genetic evaluation
    - Not too much, the only thing genetic evaluation concerns itself with is Additive gene actions.

## Animal Identification

- Why is it important?
    - Errors in identification/ poor identification can lower estimates of genetic variability and can result in biased genetic evaluations
- What are the musts?
    - Each animal is uniquely identified
    - Birth date and ID of sire and dam
- Why keep track of the sire and dam?
    - It has an effect on the estimation of breeding values, inbreeding coefficients, and amount of genetic variability remaining in the population
    - The more generations recorded, the better. Three will suffice.
- What is the base population?
    - The animals in the population that were randomly mating before genetic evaluation begun, i.e. no record of parentage

## Data

- What is data in relation to genetic evaluation
    - Traits of economic importance and all the variables that could influence the expression of those traits
- What was the problem with the old school breeding scheme
    - Originally milk production/yield was the primary goal with a disregard for other traits. Successful selection for milk yield saw a positive correlation in fertility and health issues.
    - How is this problem solved?
        - A recording scheme that attempts to define all of the traits that could influence productivity and profitability.
- Define a trait
    - Observed and recorded variables associated with productivity
        - e.g. Calf weight, milk yields, conformation of animal
- What is a contemporary group?
    - A set of animals that have had an equal opportunity to breed
- Which animals should be recorded in the herd?
    - All animals in a contemporary group
- What factors should be recorded?
    - Observed variables associated with productivity and any factors relating to the observation such as:
        - age of the animal
        - contemporary group
        - location (herd, province, country)
        - month of the year
        - breed of animal
        - age of dam
        - track conditions
        - who took the measurements
        
        **The factors affecting a trait are as important as the trait itself**
        
    

## Breeding Objective

- A function of the traits that are to be changed.
- H = $v_1T_1+v_2T_2+v_3T_3+v_4T_4+v_5T_5$
    
    Where $v_i$ are relative economic values for each trait and $T_i$ are the true breeding values for those traits. Note T will be unknown
    
- How do we approximate the breeding objective?
    - Say the first 3 traits are recorded and a 6th trait that is relevant/correlated to Trait 5. We approximate the breeding objective by an index:
        
        I = $w_1EBV_1+w_2EBV_2+w_3EBV_3+w_6EBV_6$
        
        Where $w_i$ are the economic weights, and $EBV_i$ are estimated breeding values of the animal for given traits (1,2,3,6).
        

## How is Genetic Change Measured?

- An average of the EBVs of a particular group of animals