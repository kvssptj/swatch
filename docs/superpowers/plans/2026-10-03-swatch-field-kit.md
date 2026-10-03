# Swatch Field Kit Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a dependency-free Markdown field kit that GitHub Pages presents as a light documentation site.

**Architecture:** Markdown files contain all product content. One Jekyll layout and one CSS file provide the presentation. Git stores versions, and ordinary folders store experiments, models, runs, notes, and templates.

**Tech Stack:** Markdown, YAML frontmatter, Jekyll as provided by GitHub Pages, HTML, CSS, Python standard library for local validation

**Spec:** `docs/superpowers/specs/2026-10-03-swatch-field-kit-design.md`

## Global Constraints

- The repository has no runtime dependencies.
- Markdown files are the source of truth.
- The site does not use a database, authentication, provider APIs, automated execution, analytics, rankings, or a JavaScript framework.
- The interface uses one HTML layout and one CSS file.
- Content uses short sentences, active voice, consistent terms, and direct task names.
- Formal ASD-STE100 compliance is not claimed without a complete dictionary and rule check.
- Historical runs are never replaced.
- Comparisons show outputs before observations and do not select a winner.

## Review Focus

- A filename with spaces or punctuation must produce a working GitHub Pages link; Task 1 checks every internal link after the build.
- A narrow screen must show navigation without horizontal page overflow; Task 1 checks the 390-pixel layout in browser review.
- An experiment without optional assets must remain complete and readable; Task 2 checks every required heading without checking for assets.
- A run with a long raw output must preserve its content without changing the layout width; Task 3 includes and reviews a long sample output.
- Two compared runs must identify the exact shared experiment and input; Task 3 validates both references in the sample comparison.

---

### Task 1: Documentation shell

**Files:**
- Create: `.gitignore`
- Create: `_config.yml`
- Create: `_layouts/default.html`
- Create: `assets/swatch.css`
- Create: `README.md`

**Interfaces:**
- Consumes: The repository structure and visual rules in the approved specification.
- Produces: A Jekyll layout that renders `title`, `description`, `section`, and page content from Markdown frontmatter.

- [ ] **Step 1: Initialize the repository and add a Pages-safe ignore file**

Run:

```bash
git init
printf '%s\n' '_site/' '.jekyll-cache/' '.DS_Store' > .gitignore
```

Expected: `git status --short` shows only project files and does not show ignored build output.

- [ ] **Step 2: Add the site configuration**

Create `_config.yml` with:

```yaml
title: Swatch
description: A field kit for understanding how AI models behave.
url: ""
baseurl: ""
markdown: kramdown
permalink: pretty
exclude:
  - docs/superpowers
  - swatch-visual-prototype.html
```

- [ ] **Step 3: Add the shared layout**

Create `_layouts/default.html` with:

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="description" content="{{ page.description | default: site.description }}">
  <title>{{ page.title }} · {{ site.title }}</title>
  <link rel="stylesheet" href="{{ '/assets/swatch.css' | relative_url }}">
</head>
<body>
  <header class="site-header">
    <a class="brand" href="{{ '/' | relative_url }}">Swatch <span>Field notes for AI models</span></a>
    <a href="{{ site.github.repository_url | default: '#' }}">GitHub</a>
  </header>
  <div class="docs-layout">
    <aside class="sidebar" aria-label="File navigation">
      {% include navigation.html %}
    </aside>
    <main><article class="content">{{ content }}</article></main>
  </div>
</body>
</html>
```

- [ ] **Step 4: Add the file-tree navigation**

Create `_includes/navigation.html`. Link to the README, usage guide, all 15 experiments, model notes, observation notes, runs, and templates. Use `relative_url` for every internal URL.

The first links must be:

```html
<nav class="file-tree">
  <h2>Start here</h2>
  <a href="{{ '/' | relative_url }}">README.md</a>
  <a href="{{ '/how-to-use/' | relative_url }}">How to use Swatch.md</a>
```

Close the `nav` element after all groups.

- [ ] **Step 5: Transfer the approved visual direction into one stylesheet**

Create `assets/swatch.css`. Reuse the approved prototype values:

```css
:root {
  --background: #fff;
  --surface: #f7f7f5;
  --text: #181817;
  --muted: #696965;
  --line: #e5e5e1;
  --accent: #b65332;
  --sidebar-width: 260px;
  --sans: Inter, ui-sans-serif, -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, Arial, sans-serif;
}
```

Implement the sticky 64-pixel header, 260-pixel file sidebar, centered 720-pixel content column, tables, notes, code blocks, responsive navigation, and readable asset output. At widths below 760 pixels, place the navigation above the article and prevent horizontal page overflow.

- [ ] **Step 6: Write the repository homepage**

Create `README.md` with this frontmatter:

```yaml
---
layout: default
title: Swatch
description: A small set of tests that helps me understand how AI models behave.
permalink: /
---
```

Use the approved prototype content for these sections:

1. Why I made this
2. What Swatch contains
3. How I use it
4. What I want to learn
5. Experiment map

The learning section must define imagination, perception, taste, reasoning, research, and agency. The experiment map must contain all 15 experiments from the specification.

- [ ] **Step 7: Validate the shell**

Run:

```bash
python3 - <<'PY'
from html.parser import HTMLParser
from pathlib import Path
HTMLParser().feed(Path('_layouts/default.html').read_text())
css = Path('assets/swatch.css').read_text()
assert '@media' in css
assert 'overflow' in css
assert Path('README.md').read_text().startswith('---\n')
print('shell validation passed')
PY
```

Expected: `shell validation passed`.

Review the page at 1280 and 390 pixels. Confirm that the page has no horizontal overflow and all navigation remains available.

- [ ] **Step 8: Commit the shell**

```bash
git add .gitignore _config.yml _layouts _includes assets README.md
git commit -m "feat: add Swatch documentation shell"
```

### Task 2: Experiment library and templates

**Files:**
- Create: `how-to-use.md`
- Create: `experiments/*.md` for all 15 experiments
- Create: `templates/experiment.md`
- Create: `templates/model.md`
- Create: `templates/run.md`
- Create: `templates/comparison.md`

**Interfaces:**
- Consumes: The `default` layout and navigation paths from Task 1.
- Produces: A stable experiment structure and reusable templates for future repository content.

- [ ] **Step 1: Write the usage guide**

Create `how-to-use.md` with sections for selecting an experiment, keeping inputs equal, saving raw output, writing observations, and comparing runs. Keep each instruction sentence at 20 words or fewer.

- [ ] **Step 2: Define the experiment template**

Create `templates/experiment.md` with:

```markdown
---
layout: default
title: Experiment title
description: One sentence that states what this experiment tests.
section: Experiments
version: 1
---

# Experiment title

## Purpose

State what you want to learn.

## What you need

- List each input.

## Prompt

> Add the exact prompt.

## What to observe

- List the model behaviors to examine.

## What to keep

- Keep the exact prompt, inputs, output, model version, date, and your notes.
```

- [ ] **Step 3: Write experiments 1–5**

Create:

- `experiments/write-a-story-from-three-photos.md`
- `experiments/describe-a-detailed-image.md`
- `experiments/recreate-an-image.md`
- `experiments/improve-a-rough-visual.md`
- `experiments/design-a-product-homepage.md`

Each file must use the experiment template. Use the exact test and learning goals from the experiment map in the specification.

- [ ] **Step 4: Write experiments 6–10**

Create:

- `experiments/build-a-page-from-a-screenshot.md`
- `experiments/improve-a-weak-interface.md`
- `experiments/turn-rough-notes-into-a-prd.md`
- `experiments/review-a-product.md`
- `experiments/handle-an-unclear-request.md`

Each file must contain a complete starter prompt and a specific observation list.

- [ ] **Step 5: Write experiments 11–15**

Create:

- `experiments/research-a-question.md`
- `experiments/find-facts-in-long-documents.md`
- `experiments/analyze-a-messy-spreadsheet.md`
- `experiments/complete-a-task-with-tools.md`
- `experiments/adapt-to-a-changed-brief.md`

The changed-brief experiment must contain the initial instruction and the later requirement change as separate prompt blocks.

- [ ] **Step 6: Add the remaining templates**

Create model, run, and comparison templates with the exact fields from the specification. The run template must link to an experiment version. The comparison template must link to runs and place outputs before observations.

- [ ] **Step 7: Validate the content structure**

Run:

```bash
python3 - <<'PY'
from pathlib import Path
required = ['## Purpose', '## What you need', '## Prompt', '## What to observe', '## What to keep']
files = sorted(Path('experiments').glob('*.md'))
assert len(files) == 15, len(files)
for path in files:
    text = path.read_text()
    assert text.startswith('---\n'), path
    for heading in required:
        assert heading in text, (path, heading)
print('15 experiment files passed')
PY
```

Expected: `15 experiment files passed`.

- [ ] **Step 8: Commit the library**

```bash
git add how-to-use.md experiments templates
git commit -m "feat: add Swatch experiment library"
```

### Task 3: Model notes and complete sample workflow

**Files:**
- Create: `models/openai.md`
- Create: `models/anthropic.md`
- Create: `models/google.md`
- Create: `models/open-models.md`
- Create: `notes/model-profiles.md`
- Create: `notes/comparisons.md`
- Create: `notes/changes-over-time.md`
- Create: `runs/README.md`
- Create: `runs/example-three-photos-model-a/README.md`
- Create: `runs/example-three-photos-model-b/README.md`
- Create: `notes/example-three-photos-comparison.md`
- Remove: `swatch-visual-prototype.html`

**Interfaces:**
- Consumes: Templates from Task 2 and the Three Photos experiment path.
- Produces: One complete manual workflow that shows how to record models, preserve runs, and compare outputs.

- [ ] **Step 1: Add provider note files**

Create four short provider files. Explain that each file groups model-specific notes. Do not add current model claims or hard-coded model lists.

- [ ] **Step 2: Add observation guides**

Create three notes files:

- `model-profiles.md` explains how to summarize recurring qualitative behavior.
- `comparisons.md` explains how to compare artifacts without selecting a winner.
- `changes-over-time.md` explains how to compare the same experiment across model generations.

- [ ] **Step 3: Add the runs index**

Create `runs/README.md`. State that every run gets a new folder and that old runs are never replaced.

- [ ] **Step 4: Add two example runs**

Create two fictional Three Photos runs. Both must reference `/experiments/write-a-story-from-three-photos/`, version `1`, and the same input asset description.

Each run must include:

- Fictional model label
- Date
- Exact prompt
- Shared input description
- Raw output of at least 300 words
- Observations

Wrap raw output in a normal Markdown section, not a fixed-width element, so long text remains responsive.

- [ ] **Step 5: Add the example comparison**

Create `notes/example-three-photos-comparison.md`. Link to both example runs. State the shared experiment version and shared input before showing the two outputs. Put observations after both outputs. Do not name a winner.

- [ ] **Step 6: Run repository validation**

Run:

```bash
python3 - <<'PY'
from pathlib import Path
expected = [
    '_config.yml', '_layouts/default.html', '_includes/navigation.html',
    'assets/swatch.css', 'README.md', 'how-to-use.md',
    'templates/experiment.md', 'templates/model.md', 'templates/run.md',
    'templates/comparison.md', 'runs/README.md'
]
for name in expected:
    assert Path(name).is_file(), name
assert len(list(Path('experiments').glob('*.md'))) == 15
comparison = Path('notes/example-three-photos-comparison.md').read_text()
assert 'version: 1' in comparison
assert 'example-three-photos-model-a' in comparison
assert 'example-three-photos-model-b' in comparison
for path in Path('.').rglob('*.md'):
    assert ('TO' + 'DO') not in path.read_text(), path
print('repository validation passed')
PY
```

Expected: `repository validation passed`.

- [ ] **Step 7: Review the rendered experience**

Verify these paths in the GitHub Pages build:

- `/`
- `/how-to-use/`
- `/experiments/write-a-story-from-three-photos/`
- `/runs/example-three-photos-model-a/`
- `/notes/example-three-photos-comparison/`

Confirm that all sidebar links work, the 300-word output wraps, and the mobile layout has no horizontal page overflow.

- [ ] **Step 8: Commit the complete field kit**

```bash
git add models notes runs
git rm swatch-visual-prototype.html
git commit -m "feat: add sample Swatch workflow"
```

- [ ] **Step 9: Confirm final status**

Run:

```bash
git status --short
git log --oneline -3
```

Expected: The worktree is clean and the log contains the three implementation commits.
