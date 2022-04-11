---
title: Introduction to Statistics
pcx-content-type: tutorial
weight: 1
meta:
  title: Introduction to Statistics
---

# Introduction to Statistics
- A hat (^ or - ) above a greek letter refers to the fact that we are working with a sample rather than a population.

## Definitions

- Population
    - A population refers to a group of animals that are part of the overall breeding structure
        - e.g. All dairy cows in New Zealand
- Sample
    - A subset of animals from a population
        - e.g. 30 dairy cows from New Zealand
- Sample Mean
    
    ![Sample Mean](../media/avg.png)
    
    Where $y_i$ is an observed trait value on an animal in the sample
    
    - An average of all observed traits
- Standard Deviation
    - A measure of how spread out the data is
        - Note - To give an idea of its measure, In a normal distribution 99.7% of the data will be within 3 standard deviations
            
            ![Standard Deviation](../media/stddev.png)
            
- Variance
    - An indication of the range of possible values that $y_i$ could be. For example a min of 1 and a max of 3 will have a smaller variance than a min of 0 and a max of 4.
    - $StandardDeviation^2$
        
        ![Variance](../media/variance.png)
        
- Coefficient of Variation
    - Represents the degree of variation relative to the size of the mean
        
        ![Coefficient of Variation](../media/coef-variation.png)
        
- Covariance
    - Measure how two traits vary together. A trait such as milk solids against a trait such as avg days on penicillin:
        
        ![Covariance](../media/covariance.png)
        
    - Can be positive or negative
        - Positive means when one grows so does the other
        - Negative means when one grows the other shrinks
- Correlation Coefficient
    - Describes the same thing as Covariance, but is a bit easier to calculate and interpret
        
        ![Correlation Coefficient](../media/correlation.png)
        
    - Ranges between -1 and +1

## Normal Distribution

- Described using the mean and variance - N(mean, variance)
- A standard normal distribution (SND) = N(0,1)

### Commonly used values for an SND

![z-value chart](../media/z.png)

- z-value
    - Used to express standard deviations from the mean
        - 2.5 is 2.5 standard deviation from the mean (positively)
    - $z_i = y_i-μ/σ$
- Percentage point (p)
    - The portion of population above the z-value
- Confidence Interval
    - Gives the portion of the population within a z-value and it’s inverse

![Bell Curve]../media/bellcurve.png)

- Selection Intensity
    - $i$
    - the average value of the portion $p$ of the population that is above the z-value

## The Empirical Rule

For any bell-shaped curve - normal distribution

- What % of values for within **1 standard deviation** of the mean in either direction
    - 68%
- What % of values fall within **2 standard deviations** of the mean in either direction
    - 95%
- What % of values fall with **3 standard deviations** of the mean in either direction
    - 99.7%