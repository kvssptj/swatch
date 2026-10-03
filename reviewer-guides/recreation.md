---
layout: default
title: Recreation reviewer guide
description: Review an image recreation for prompt quality, composition, detail, and appearance.
---

# Recreation reviewer guide

Use this guide after the run. Do not give this guide to the model. Use [Photo 02]({{ '/assets/photography/photo-02.png' | relative_url }}) as the input.

## Visible reference details

- A landscape-oriented photograph of a snow-covered mountain valley.
- The valley recedes toward the central distance, framed by slopes on both sides.
- The foreground is a broad, smooth snowbank. The middle distance has dark exposed rock and slopes with more texture.
- Winding dark road segments appear near the lower center. They are a small but distinctive feature, not a wide foreground highway.
- Low white and gray clouds obscure portions of the upper terrain, with deep blue sky visible above.
- The palette is predominantly white, cool gray, dark rock, and blue. There are no prominent foreground people, buildings, or trees.

## Keep generation conditions separate

Record the exact description sent to the generator, generator name and settings when available, number of attempts, and whether the reference image was supplied. If the tool rewrites the prompt and exposes that rewrite, save both. Mark undisclosed settings as unknown.

Description-only generation and reference-assisted generation test different workflows. Do not pool them. Keep the first result even if a later attempt improves it. If generation is unavailable, review the description and mark the image portion not assessable.

## Checklist

- [ ] The written prompt captures composition and relative positions, not just a generic snowy mountain scene.
- [ ] The exact generator prompt and output image are saved.
- [ ] The generated image preserves the landscape aspect ratio and main depth relationships.
- [ ] The road remains a small winding feature in the lower valley.
- [ ] Clouds, exposed rock, and snow produce a similar distribution of shapes and contrast.
- [ ] Major added, lost, or displaced elements are recorded.
- [ ] The model's own comparison is checked against the images rather than accepted as evidence.

## Quality anchors

| Dimension | Strong | Mixed | Weak |
| --- | --- | --- | --- |
| Description | Captures viewpoint, depth, road placement, clouds, and surface differences | Captures subject and palette but misses important structure | Generic landscape prompt with little reference specificity |
| Composition | Valley, slopes, foreground, and clouds retain their relative arrangement | Recognizable scene with noticeable shifts in framing or proportions | Substantially different viewpoint or scene structure |
| Distinctive details | Road scale and placement, exposed rock, and cloud cover survive | Some distinctive features survive but others disappear | Mostly a generic snowy mountain image |
| Appearance | Similar photographic treatment, palette, light, and texture | Similar palette but noticeably different texture or light | Unrequested illustration style or major color/lighting departures |

Judge fidelity separately from attractiveness. A beautiful image may be an inaccurate recreation. Pixel equality is not expected, but changes to the main composition matter more than tiny surface differences.

## Record evidence

Put the reference image and the generated image side by side. Use the same display size for both images. Identify the three most important matches and differences. Keep details that are missing from the description separate from details that the generator did not make. Record uncertainty when you cannot identify the cause of a difference. Use the [run template]({{ '/run-template/' | relative_url }}).
