---
# ─── The structure. Fill in the fields below, then the sections further down. ───
# Copy this file, rename it (e.g. _artifacts/mri/ghosting.md), and replace the
# content. Everything above the second "---" is fill-in-the-blank; below it is
# your writing. You never touch HTML or CSS.

name: Head motion                    # the artifact's name
aka: motion artifact                 # other names (optional)
modality: MRI                        # MRI or EEG
submodality: Functional (fMRI)       # e.g. Functional (fMRI) / Structural / Diffusion (dMRI)
section: Artifacts                   # Equipment setup / Artifacts / QC checks / Practice
origin: Physiological                # Physiological / Acquisition / Environmental / Technical
severity: Common                     # Common / Occasional / Rare
summary: The brain shifts position between volumes, blurring the image and adding ringing at high-contrast boundaries.
permalink: /artifacts/example-template/   # the page's web address (change the last part)
---

<!--
  Write each section in plain language. Delete any you don't need.
  To add an image: use "Add file → Upload files" to put it in assets/images/,
  then reference it here like:  ![short caption](/VisualQA/assets/images/your-file.png)
  This page is a live example — open it in the browser to see how it renders.
-->

## What you see

Blurring and smearing across the image, often with bright or dark bands at
high-contrast boundaries — the edge of the brain, the ventricles, the skull.
On a functional run played as a movie, the brain visibly shifts between volumes.

## Why it happens

The subject moves during acquisition. Because a volume is built up over time,
movement means different parts of the image describe different head positions.
Even sub-millimetre motion matters, and motion correlated with the task is far
more damaging than random motion.

## How to check

- Plot framewise displacement across the run and look for spikes.
- Scrub through the 4D series as a movie — real motion is obvious in motion.
- Check whether the motion tracks your task timing.

## The judgment call

There is rarely one right answer. Ringing confined to skull and scalp with an
intact gray/white boundary may still be usable for volumetrics; ringing reaching
cortex is not. Decide against your pre-registered threshold, not against a
picture — and weigh how much data you can afford to lose. If the participant is
still in the scanner, a rescan beats any post-hoc fix.

## What to do

Realignment handles small movements; regressing motion parameters helps.
Censoring high-motion volumes is common but costs degrees of freedom — report
what you excluded. Be cautious interpreting activation when motion tracks task.

## Easy to confuse with

Susceptibility-related signal dropout, which is spatially fixed and does not
vary with the motion trace.

## References

1. Example reference — replace with the sources behind your page.
