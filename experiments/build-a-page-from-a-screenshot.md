---
layout: default
title: Build a page from a screenshot
description: Test perception, frontend skill, and visual fidelity.
section: Experiments
---

# Build a page from a screenshot

## Purpose

Learn how well the model reads a visual reference and turns it into working code.

## What you need

- One complete product screenshot.
- A simple frontend project or an empty HTML file.

## Prompt

> Recreate the attached screenshot as a working page in the supplied frontend project. Treat the screenshot as the visual source of truth at its original viewport size. Match the content, layout, proportions, spacing, typography, colors, borders, and other visible details as closely as the available assets allow.
>
> Use the project's existing stack and conventions. Implement the structure with semantic HTML and maintain keyboard accessibility for interactive elements. Do not substitute the screenshot itself for the page or add product features absent from the reference.
>
> Infer a sensible layout for narrower screens, recognizing that responsive behavior cannot be established from a single screenshot. Clearly identify those inferences and any substitutions for missing fonts or assets.
>
> Deliver runnable code, check the rendered page against the reference at the matching viewport, and check usability on a narrow screen. Summarize the remaining visual differences and any interactions whose behavior had to be inferred.

## What to observe

- Does the structure match the screenshot?
- Are spacing and proportions accurate?
- Does the model choose suitable HTML and CSS?
- Does the page remain usable on a narrow screen?
