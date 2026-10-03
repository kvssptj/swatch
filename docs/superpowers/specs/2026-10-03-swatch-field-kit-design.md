# Swatch field kit design

## Purpose

Swatch is a personal field kit for understanding how AI models behave.

New models appear often. Benchmarks and release notes do not show what a model feels like during real work. Swatch uses repeatable experiments to build this practical knowledge.

Swatch does not select the best model. It helps a person select a suitable model for a specific task.

## Audience

The first user is a product manager who evaluates models for product work. Other people can fork the repository and change the experiments for their own work.

## Product form

Swatch is a GitHub repository. Markdown files are the source of truth.

GitHub Pages presents the files as a light documentation site. The site does not contain a database, authentication, provider APIs, or task execution.

Git stores the history. Files and folders provide the information architecture.

## Primary questions

Swatch helps the user understand six model characteristics:

1. **Imagination:** Does the model make original connections and create coherent work?
2. **Perception:** What does the model see, miss, or invent?
3. **Taste:** Does the model make good visual and product decisions?
4. **Reasoning:** Can the model organize unclear information and set useful priorities?
5. **Research:** Can the model find, combine, and cite reliable information?
6. **Agency:** Can the model plan, use tools, recover, and adapt?

These characteristics are qualitative. Swatch does not combine them into one score.

## Repository structure

```text
swatch/
├── README.md
├── _config.yml
├── _layouts/
│   └── default.html
├── assets/
│   └── swatch.css
├── experiments/
│   ├── write-a-story-from-three-photos.md
│   ├── describe-a-detailed-image.md
│   ├── recreate-an-image.md
│   ├── improve-a-rough-visual.md
│   ├── design-a-product-homepage.md
│   ├── build-a-page-from-a-screenshot.md
│   ├── improve-a-weak-interface.md
│   ├── turn-rough-notes-into-a-prd.md
│   ├── review-a-product.md
│   ├── handle-an-unclear-request.md
│   ├── research-a-question.md
│   ├── find-facts-in-long-documents.md
│   ├── analyze-a-messy-spreadsheet.md
│   ├── complete-a-task-with-tools.md
│   └── adapt-to-a-changed-brief.md
├── models/
│   ├── openai.md
│   ├── anthropic.md
│   ├── google.md
│   └── open-models.md
├── notes/
│   ├── model-profiles.md
│   ├── comparisons.md
│   └── changes-over-time.md
├── runs/
│   └── README.md
└── templates/
    ├── experiment.md
    ├── model.md
    ├── run.md
    └── comparison.md
```

## File formats

### Experiment

Each experiment contains:

- Purpose
- What to give the model
- Prompt
- What to observe
- Output to keep
- Notes

The filename and title describe the task directly. Branded test names are not used.

### Model

Each model file contains:

- Provider
- Model name and version
- Date tested
- Supported input and output types
- General observations
- Links to saved runs

### Run

Each run has its own folder. The folder contains one Markdown file and any input or output assets.

A run records the exact model, experiment version, prompt, input, output, date, and observations. Old runs are not replaced.

### Comparison

A comparison links to runs that used the same experiment and input. It shows the outputs before the observations. It does not select a winner.

## Initial experiments

The first version contains 15 experiments:

1. Write a story from three photos
2. Describe a detailed image
3. Recreate an image
4. Improve a rough visual
5. Design a product homepage
6. Build a page from a screenshot
7. Improve a weak interface
8. Turn rough notes into a PRD
9. Review a product
10. Handle an unclear request
11. Research a question
12. Find facts in long documents
13. Analyze a messy spreadsheet
14. Complete a task with tools
15. Adapt to a changed brief

## Website

GitHub Pages uses Jekyll because GitHub supports it directly.

The site has:

- A small header
- A file-tree sidebar
- One readable content column
- A search control only if it works without a new dependency
- Responsive navigation for small screens

The visual design is light, quiet, and similar to modern documentation. Warm neutral colors provide a small material reference. The interface does not imitate a physical notebook.

The site uses one HTML layout and one CSS file. JavaScript is not required for the first version.

## Writing rules

Content follows applicable ASD-STE100 principles:

- Use short sentences.
- Use one main idea in each sentence.
- Prefer active voice.
- Use one term for one meaning.
- Use direct task names.
- Remove promotional language.

Formal ASD-STE100 compliance is not claimed without a complete dictionary and rule check.

## Out of scope

The first version does not include:

- A web application
- Model API connections
- Automated execution
- Authentication
- A database
- Scoring or rankings
- Analytics
- A JavaScript framework
- A package manager

## Acceptance criteria

The first version is complete when:

1. GitHub can render the repository as a Pages site.
2. The sidebar links to all primary Markdown files.
3. The README explains why Swatch exists and how to use it.
4. All 15 experiment files contain useful starter content.
5. Templates support new experiments, models, runs, and comparisons.
6. A sample model, run, and comparison show the complete manual workflow.
7. The site works on desktop and mobile screens.
8. The repository has no runtime dependencies.
