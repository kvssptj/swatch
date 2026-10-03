---
layout: default
title: Find facts in long documents
description: Test retrieval, context use, and attention.
section: Experiments
version: 1
---

# Find facts in long documents

## Purpose

Learn whether the model can find and combine facts that are spread across long documents.

## What you need

- Several long documents.
- A question that needs facts from more than one document.

## Prompt

> Answer the question from the supplied documents. Cite the document and section for each fact. If the documents do not support a claim, say so.

## What to observe

- Does the model find all relevant facts?
- Does it combine related facts correctly?
- Are citations precise and valid?
- Does it invent missing support?
