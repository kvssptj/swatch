---
layout: default
title: Turn rough notes into a PRD
description: Test synthesis, ambiguity handling, and product reasoning.
section: Experiments
---

# Turn rough notes into a PRD

## Purpose

Learn how the model turns incomplete and conflicting information into a product document.

## What you need

- Messy meeting notes with gaps, repetition, and conflicting requests.

## Prompt

> Turn the supplied meeting notes into a concise PRD that a product, design, and engineering team can use to discuss scope and plan delivery. Consolidate repetition and organize the material around the underlying user problem rather than the order in which people spoke.
>
> Cover the problem, target users, intended outcomes, proposed scope, non-goals, prioritized requirements, and success measures. Include key user flows, dependencies, and risks where the notes support them. Make requirements specific enough to assess, with acceptance criteria for the core behavior.
>
> Separate confirmed decisions from proposals, assumptions, and open questions. Preserve conflicting requests and explain their implications rather than silently choosing one. Do not invent research findings, commitments, metric baselines, or delivery dates. Label any suggested targets or priorities as proposals when the notes do not establish them.
>
> End with the decisions needed to make the PRD actionable, indicating which block scope or delivery. Keep the document concise enough to review in one sitting.

## What to observe

- Does the model find the real problem?
- Does it preserve uncertainty instead of hiding it?
- Are the priorities supported by the notes?
- Are the success measures useful and measurable?
