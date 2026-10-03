---
layout: default
title: Analyze a messy spreadsheet
description: Test analysis, tool use, and quantitative reasoning.
section: Experiments
---

# Analyze a messy spreadsheet

## Purpose

Learn how the model cleans data, uses tools, and supports a business conclusion.

## What you need

- A CSV or spreadsheet with missing values, inconsistent labels, and extra columns.
- One business question.

## Prompt

> Use the attached file to answer the supplied business question. Inspect the data structure, units, date coverage, and record granularity before choosing an analysis. Check for missing values, duplicate records, inconsistent labels, invalid values, and other issues that could materially affect the answer.
>
> Preserve the original data. Explain consequential cleaning decisions, including how you handle exclusions, missing values, and ambiguous records. Do not silently treat missing values as zero or remove unusual observations merely because they complicate the result.
>
> Show the calculations behind the conclusion, with clear metric definitions, denominators, units, and time periods. Provide reproducible formulas or analysis code and a cleaned file if you create one. Reconcile key counts or totals to the source and distinguish association from causation.
>
> Lead the final response with the business answer and supporting figures. Explain material limitations, how sensitive the conclusion is to uncertain assumptions, and which unresolved data issues could change the recommendation.

## What to observe

- Does the model inspect the data before it calculates?
- Does it clean values without losing important records?
- Are the calculations correct and repeatable?
- Does the conclusion match the evidence?
