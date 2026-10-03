---
layout: default
title: Photography kit
description: Three photographs and a repeatable workflow for visual experiments.
---

# Photography kit

I use these photos for three experiments: write a story, describe an image, and recreate an image. I use PNG copies in this kit. The kit does not include the original camera files, capture dates, or verified metadata. It does not give permission to reuse the photos.

## The photographs

Download the files and attach them to the model. Do not give the page captions or review guides to the model. Use the same files and attachment order for each run that you want to compare.

### Photo 01

![Photo 01: A yellow roadside marker and sticker-covered board in a snowy mountain landscape.]({{ '/assets/photography/photo-01.png' | relative_url }})

[Download Photo 01 (PNG)]({{ '/assets/photography/photo-01.png' | relative_url }})

### Photo 02

![Photo 02: A snow-covered valley with a winding road beneath low clouds.]({{ '/assets/photography/photo-02.png' | relative_url }})

[Download Photo 02 (PNG)]({{ '/assets/photography/photo-02.png' | relative_url }})

### Photo 03

![Photo 03: A paved road curving into a dry mountain valley with distant buildings.]({{ '/assets/photography/photo-03.png' | relative_url }})

[Download Photo 03 (PNG)]({{ '/assets/photography/photo-03.png' | relative_url }})

## Choose an experiment

| Experiment | Attach | What it tests |
| --- | --- | --- |
| [Write a story from three photos](experiments/write-a-story-from-three-photos.md) | Photos 01, 02, 03, in that order | Narrative continuity and visual grounding |
| [Describe a detailed image](experiments/describe-a-detailed-image.md) | Photo 01 | Detail, text recognition, spatial relationships, uncertainty |
| [Recreate an image](experiments/recreate-an-image.md) | Photo 02 | Translation into language and preservation of composition |

These photos show mountain roads. The story experiment tests how well a model creates one connected journey. It does not test how the model connects unrelated subjects. The photos do not show their actual sequence or the relationship between their locations.

## Run a small comparison

1. Choose two models. Run each experiment twice with each model. Start each run in a new chat. This gives you twelve runs across the three experiments. Use the results to explore model behavior. Do not use them as a statistical ranking.
2. Use the same files, attachment order, exact prompt, and available tools. For story and description runs, turn off browsing where possible so the model works from the images. Record any differences you cannot control.
3. Save the complete first response and any generated files before reviewing. Keep failures and incomplete attempts. Record follow-ups separately rather than replacing the original output.
4. Use the [run template](run-template.md) and the experiment's reviewer guide. Keep the guide out of the model's conversation.
5. Put comparable outputs beside one another. Note specific evidence, recurring strengths, failures, and variation between attempts. Where practical, review outputs under anonymous run IDs before revealing model names.

For recreation, record both the describing model and the image generator. Compare description-only generation separately from generation that also receives the reference image. If the generator differs, conclusions concern the combined workflow rather than the describing model alone.

## Context policy

The default runs use only the photographs and prompt. Do not add trip memories, inferred locations, dates, or a proposed story sequence. A later run may include photographer-provided context, but save that context verbatim and compare it only with similarly informed runs.

## Reviewer guides

- [Story guide](reviewer-guides/story.md)
- [Description guide](reviewer-guides/description.md)
- [Recreation guide](reviewer-guides/recreation.md)
