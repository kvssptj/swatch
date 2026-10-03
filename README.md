---
layout: default
title: Swatch
description: A small set of tests that helps me understand how AI models behave.
permalink: /
---

# Swatch

<img class="landing-logo" src="assets/swatch-logo.png" alt="Textured Swatch fan deck logo" width="290">

Swatch is a small set of tests that helps me understand how AI models behave.

## Why I made this

New AI models appear often. Each model has different strengths, limits, and habits.

Benchmarks give useful data. Release notes list new functions. These sources do not show what a model feels like during real work.

As a product manager, I need practical knowledge. I need to know how a model writes, sees, designs, researches, and uses tools.

I also need to know how the model handles unclear requests. Small behavior differences can change a product experience.

> **Swatch does not select the best model.** It helps me select a suitable model for a specific task.

## What Swatch contains

Swatch contains repeatable experiments. Each experiment tests one or more model behaviors.

One experiment gives a model three photos. The model must use the photos to write a short road-trip story.

Another experiment gives a model one image. The model must describe the image and then make a similar image.

I can use the same experiment with different models. I can then compare the actual outputs.

## How I use it

1. **Select an experiment.** Select a task that tests the behavior that you want to examine.
2. **Use the same input.** Give each model the same prompt, instructions, and source files.
3. **Keep the output.** Save the complete response. Do not replace an old response with a new response.
4. **Write what you notice.** Record good work, errors, assumptions, and unexpected behavior.
5. **Compare the work.** Put the outputs next to each other. Do not reduce the result to one score.

## What I want to learn

I use each experiment to examine a part of the model. I want to understand how the model sees, thinks, and acts.

<div class="learning-grid">
<section><h3>Imagination</h3><p>Does the model make original connections? Can it create clear work with a distinct style?</p></section>
<section><h3>Perception</h3><p>What does the model see? Does it understand details, space, and visual relationships?</p></section>
<section><h3>Taste</h3><p>Can the model make good design choices? Does it use hierarchy, composition, and restraint?</p></section>
<section><h3>Reasoning</h3><p>Can the model organize unclear information? Does it make sound assumptions and set useful priorities?</p></section>
<section><h3>Research</h3><p>Can the model find reliable information? Can it combine sources and show evidence for its claims?</p></section>
<section><h3>Agency</h3><p>Can the model make a plan, use tools, recover from errors, and respond to a changed request?</p></section>
</div>

## Experiment map

Each experiment gives me a different view of the model. Together, the experiments create a useful model profile.

| Experiment | Test | What I learn |
| --- | --- | --- |
| Write a story from three photos | Use three photographs in one road-trip story. | Imagination, visual grounding, narrative, style |
| Describe a detailed image | Describe all relevant parts of a dense photograph. | Perception, space, detail, hallucination |
| Recreate an image | Describe an image and then make a similar image. | Visual translation and image fidelity |
| Improve a rough visual | Turn a rough visual and a brief into polished work. | Taste, composition, instruction use |
| Design a product homepage | Design a homepage from a short product description. | UI taste, hierarchy, copy, frontend skill |
| Build a page from a screenshot | Build a working page from one screenshot. | Perception, frontend skill, visual fidelity |
| Improve a weak interface | Improve an interface that has clear design problems. | Design judgment and restraint |
| Turn rough notes into a PRD | Turn incomplete meeting notes into a useful PRD. | Synthesis, ambiguity, product reasoning |
| Review a product | Review a product screen and recommend changes. | Product judgment, reasoning, priorities |
| Handle an unclear request | Respond to a broad request with limited direction. | Questions, assumptions, initiative |
| Research a question | Answer one question with eight to ten sources. | Search, synthesis, citation quality |
| Find facts in long documents | Find related facts in several long documents. | Retrieval, context use, attention |
| Analyze a messy spreadsheet | Use a difficult spreadsheet to answer a business question. | Analysis, tool use, quantitative reasoning |
| Complete a task with tools | Find options, compare them, and make an artifact. | Planning, tool selection, recovery |
| Adapt to a changed brief | Change an important requirement during the task. | Adaptability and context updates |

## Ready-to-run photography kit

Start with my [photography kit](photography-kit.md). It has three photos for the story, description, and recreation experiments. It also has review guides with clear quality checks. Use the [run template](run-template.md) to save each run and compare the results.
