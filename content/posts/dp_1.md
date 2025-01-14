---
title: "Coding - Dynamic Programming"
date: "2025-01-12"
summary: "A framework to solve dynamic programming problems."
description: "A framework to solve dynamic programming problems."
toc: true
readTime: true
autonumber: true
math: true
tags: ["coding", "dynamic programming"]
showTags: true
hideBackToTop: false
---

## Context
I used to be pretty intimidated by dynamic programming (DP). Every time I saw those recursive formulas or multi-dimensional DP tables, I wanted to run for the hills.

Yet, during the winter break, I found myself knee-deep in dynamic programming problems—one after going through tens of DP problems. 

In this (my very first!) blog post, I’d like to share the “aha!” moments with DP starting from the most classic Knapsack problems: **0/1 and Unbounded Knapsack**. I hope it spares you at least a few hair-pulling moments if you’re about to dive into the wacky world of DP!

For the rest, I'll cover:

1.	A summary of common DP problem types related to the Knapsack Problem
2.	The four essential components of a dynamic programming solution
3.	Sample code snippets demonstrating how to apply this DP framework in practice

## Problem Overview

One of the most common types of dynamic programming (DP) problems involves selecting elements from a set or list, using each either once or multiple times, to achieve a specific goal. This goal could be finding a min/max value (e.g., [Combination Sum II](https://leetcode.com/problems/combination-sum-ii/)) or determining the number of ways to reach a target (e.g., [Coin Change II](https://leetcode.com/problems/coin-change-2/)).

More generally, these problems aim to achieve a goal under certain constraints:

- **Goal:** Find the min/max value or determine all possible ways to achieve a specific **outcome**.
- **Constraints:**
  - The **frequency** to use each element.
    - Once -> 0/1 Knapsack
    - Unlimited times -> Unbounded Knapsack
  - Requirements of the **outcomes**, eg. a target sum.

**Keep the goal and constraints in mind**, as in the later section, we will discuss how to use them to define the states in a DP table.

## The 4-Step Framework for Dynamic Programming

The essence of DP algorithm is to trade in the space complexity to achieve a more performant time complexity usually of its DFS counterpart(sole recursion without memoization). Therefore, it's very common to assume we are going to define a DP table to store some intermediate results. We can start the DP table either as an 1D or 2D list / hashmap. Every element or entry in the DP table is the so-called **state**.

As I code up DP algorithms, I like to follow a **4-step framework** around the aka state to organize my thoughts. 

This framework includes:

- **State Definition**
- **State Transition**
- **State Initialization**
- **Final Result**

### State Definition
