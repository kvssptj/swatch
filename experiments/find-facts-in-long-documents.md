---
layout: default
title: Find facts in long documents
description: Test retrieval, context use, and attention.
section: Experiments
---

# Find facts in long documents

## Purpose

Learn whether the model can find and combine facts that are spread across long documents.

## What you need

- Several long documents.
- A question that needs facts from more than one document.

## Prompt

> Answer the supplied question using only the attached documents. Find and combine the relevant evidence across the full set rather than relying on a single passage or document.
>
> Start with a direct answer. Support each material factual claim with the document title and a precise page, section, or other available locator. Include short quotations when exact wording is necessary to establish a condition, exception, or contradiction.
>
> Keep entities, dates, units, definitions, and document versions distinct. Where sources disagree, describe the conflict and explain whether the documents establish which account takes precedence. Distinguish explicit statements from conclusions you derive by combining evidence.
>
> Identify any part of the question that the documents do not answer. Do not fill gaps with outside knowledge or treat an absence of evidence as proof that something did not occur.

## What to observe

- Does the model find all relevant facts?
- Does it combine related facts correctly?
- Are citations precise and valid?
- Does it invent missing support?
