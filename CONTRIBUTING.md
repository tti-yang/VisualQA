# Contributing content

You do **not** need to know HTML, CSS, or git. Everything below happens in your
web browser, on GitHub. You write the content into a ready-made structure; a
maintainer places it on the site.

## Adding or revising an artifact page

**1. Start from the template.** Open
[`_artifacts/example-template.md`](_artifacts/example-template.md) — it's a page
already filled in as an example. This is the structure: a few labelled fields at
the top, then plain-language sections (What you see · Why it happens · How to
check · **The judgment call** · What to do · Easy to confuse with · References).

**2. Make your own copy.** On that file, click the pencil (✏️) to edit, or use
**Add file → Create new file** and paste the template in. Name it like
`_artifacts/mri/ghosting.md`. Change the `permalink:` line to match
(e.g. `/artifacts/mri/ghosting/`).

**3. Fill it in.** Replace the fields and the text under each heading with your
content. Use the **Preview** tab while editing to see it formatted. Leave out
any section that doesn't apply.

**4. Add images or videos.** Use **Add file → Upload files** to put them in
`assets/images/` (or `assets/videos/`). Reference one in your page like:

```
![short caption](/VisualQA/assets/images/your-file.png)
```

**5. Save (“Commit”).** Add a short note like “draft ghosting page” and save.
That's it — your draft is stored and versioned, so nothing is ever lost.

**6. Revise anytime.** Come back and edit the same file as often as you like.
When it's ready, tell a maintainer and it gets published into the site's
navigation.

## Prefer not to use GitHub?

Open a submission form instead: **Issues → New issue → “Submit an artifact.”**
It's a guided form with the same fields; you can drag-and-drop images straight
into it. A maintainer turns it into a page.

## The fields, briefly

| Field | Meaning |
|-------|---------|
| `name` | The artifact's name |
| `aka` | Other names for it (optional) |
| `modality` | `MRI` or `EEG` |
| `submodality` | e.g. Functional (fMRI) / Structural / Diffusion (dMRI) |
| `section` | Equipment setup / Artifacts / QC checks / Practice |
| `origin` | Physiological / Acquisition / Environmental / Technical |
| `severity` | Common / Occasional / Rare |
| `summary` | One plain sentence |

Write for someone learning QA. Describe how a researcher actually reasons about
severity and context — the judgment call — not just a single "right" answer.
