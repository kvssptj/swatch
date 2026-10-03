---
layout: default
title: Description reviewer guide
description: Review an image description for coverage, spatial accuracy, text, and uncertainty.
---

# Description reviewer guide

Use this guide after the run. Do not give this guide to the model. Use [Photo 01]({{ '/assets/photography/photo-01.png' | relative_url }}) as the input.

## Visible reference details

- A yellow/ochre roadside marker occupies the right foreground, with dark lettering, a reddish border, and a broad stepped base.
- A rectangular sticker-covered board stands to its left on narrow supports. Pale fabric hangs from the board and supports.
- The marker base carries two distinct painted emblems: a triangular mountain-like design on the left and a shield-like design on the right. Their organizational meanings are not established by appearance alone.
- Snow covers much of the ground and the rising mountain slope. Dark rocks are visible in the foreground and on the slope.
- Blue sky and large clouds occupy the upper part of the image. A distant valley and a small winding road segment are visible toward the far left.

### Readable marker text

Compare the text with the full-size image. The main text includes “VIJAYAK”, “KHARDUNGLA”, “TOP”, “NORTH PULLU-14KM”, “KHALSAR – 56KM”, “NUBRA SAND DUNES-86KM”, “SIACHEN BASE CAMP164”, “16TF”, and “54 RCC”. The spaces between words are small in some places. Do not give a large penalty for small differences in spaces or dashes. Do not add a unit after 164 because the image does not show one.

Treat the stickers separately. Many are too small for reliable transcription at this resolution. Judge a claimed sticker inscription against the actual image rather than assuming every small label can be read.

## Checklist

- [ ] The overview captures the scene before small details.
- [ ] Left/right, foreground/background, and relative scale are accurate.
- [ ] The description includes both the marker and sticker board, their supports or bases, and the surrounding terrain.
- [ ] Important text is transcribed accurately without completing unreadable text from context.
- [ ] The model distinguishes visible evidence from interpretations.
- [ ] It avoids unsupported claims about altitude, capture date, temperature, photographer, or the meaning of insignia.

## Quality anchors

| Dimension | Strong | Mixed | Weak |
| --- | --- | --- | --- |
| Coverage | Main subjects and several distinctive secondary details are represented | Main subjects are right but important secondary details are missed | A main subject is omitted or misidentified |
| Spatial accuracy | Relationships let a reader reconstruct the arrangement | Mostly correct with a localized placement error | Reverses subjects or substantially misrepresents the scene |
| Text | The main text is accurate, and the response identifies unreadable parts | The response has some text errors but does not invent much text | The response invents or incorrectly reads much of the text |
| Calibration | Separates observation from interpretation at the points that need it | Some unsupported assumptions or excessive hedging | Confidently supplies facts the image cannot establish |

A short accurate description can outperform a long inventory. A plausible geographic identification should be attributed to the visible sign, not treated as independent verification of the location.

## Record evidence

Quote each important claim. Mark it as supported, partly supported, unsupported, or uncertain at the supplied resolution. Keep omissions separate from false claims. Use the [run template]({{ '/run-template/' | relative_url }}).
