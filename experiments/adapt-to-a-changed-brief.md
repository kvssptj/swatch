---
layout: default
title: Adapt to a changed brief
description: Test adaptability and context updates.
section: Experiments
---

# Adapt to a changed brief

## Purpose

Learn how the model responds when an important requirement changes during a task.

## What you need

- A short product description specifying the product domain and core user problem.
- A requirement change that affects the main approach.

## Prompt

Use the same product domain and core user problem for both stages. Send the requirement change after the model has completed its initial proposal, at the same point in every run.

### Initial instruction

> Using the supplied product context, design a paid desktop product for expert users. Develop a coherent proposal covering the value proposition, product structure, main screen, primary workflow, and launch plan.
>
> Make explicit decisions about how experienced users complete the core task, which capabilities belong in the first release, and how the paid offering will be positioned. Describe the main screen in enough detail for a designer to develop it, including information hierarchy and key interactions.
>
> Explain the important tradeoffs and assumptions. Define how you would evaluate whether the initial release delivers value, and identify the main risks to adoption. Keep the proposal grounded in the supplied context.

### Later requirement change

> The brief has changed: the product must now be free to use, mobile-first, and suitable for first-time users. The core user problem remains the same. These requirements replace the earlier pricing, platform, and audience requirements.
>
> Revise the full proposal, including the value proposition, product structure, main screen, primary workflow, release scope, launch plan, and success measures. Address how the new audience discovers the product and completes its first useful task on a small screen. Explain any assumptions about sustaining a free offering.
>
> Preserve earlier decisions that still serve the new brief, replace those that no longer fit, and resolve downstream contradictions. Return a self-contained updated proposal followed by a concise account of what you retained, changed, and removed, with the reasons for those decisions.

## What to observe

- Does the model identify which earlier decisions no longer apply?
- Does it update the full solution instead of adding a note?
- Does it preserve useful work from the first response?
- Does it explain important changes?
