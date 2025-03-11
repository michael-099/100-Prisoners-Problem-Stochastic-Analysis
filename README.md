
# 100-Prisoners-Problem-Stochastic-Analysis

## 100 Prisoners Problem

Each prisoner has to find their own number in one of 100 drawers but may open only 50 of them.

The **100 prisoners problem** is a mathematical challenge in probability theory and combinatorics. In this problem, 100 prisoners, each assigned a unique number, must find their own number inside one of 100 drawers to survive. The rules state that each prisoner may open only 50 drawers and cannot communicate with other prisoners after the first prisoner enters the room. At first glance, the situation appears hopeless, but a clever strategy offers the prisoners a realistic chance of survival.

The problem was first proposed by Anna Gál and Peter Bro Miltersen in 2003.

## Problem

The 100 prisoners problem has different renditions in the literature. The following version is by Philippe Flajolet and Robert Sedgewick:

*The director of a prison offers 100 death row prisoners, who are numbered from 1 to 100, a last chance. A room contains a cupboard with 100 drawers. The director randomly places each prisoner’s number inside a closed drawer. The prisoners enter the room one after another. Each prisoner may open and look inside 50 drawers in any order. The drawers are closed again afterward. If every prisoner finds their number, all prisoners are pardoned. However, if even one prisoner fails, all prisoners are executed. Before the first prisoner enters, they may discuss strategy—but no communication is allowed once the search begins. What is the prisoners' best strategy?*

If each prisoner selects 50 drawers independently and randomly, the probability that a single prisoner finds their number is 50%. The probability that all prisoners succeed is the product of individual probabilities, which is (1/2)^100 ≈ 0.0000000000000000000000000008—a vanishingly small number. The situation appears hopeless.

## Solution

### Strategy

Surprisingly, there is a strategy that provides a survival probability of more than 30%. The key insight is that prisoners do not need to choose all their drawers beforehand. Instead, they can use the information from each opened drawer to decide the next one to open. Another crucial observation is that the success of one prisoner is not independent of the others, as they all follow a structured approach based on the way numbers are distributed.

To implement this strategy, both the prisoners and the drawers are numbered from 1 to 100. The strategy is as follows:

1. Each prisoner first opens the drawer labeled with their own number.
2. If this drawer contains their number, they succeed.
3. Otherwise, the drawer contains the number of another prisoner. The prisoner then opens the drawer labeled with this new number.
4. The prisoner repeats steps 2 and 3 until they either find their own number or fail after opening 50 drawers.

This method effectively groups prisoners into cycles within a permutation of numbers. If all cycles are 50 drawers or shorter, every prisoner will eventually find their number. The only way the strategy fails is if at least one cycle exceeds 50 drawers.

This repository contains a Monte Carlo simulation to estimate the probability of survival using this strategy.

## Source

This explanation is based on the [&#34;100 prisoners problem&#34;](https://en.wikipedia.org/wiki/100_prisoners_problem) article from Wikipedia.
