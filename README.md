# NeuroQA

Building an open educational resource for neuroimaging quality assurance.

**Live site:** [henrfo.github.io/VisualQA](https://henrfo.github.io/VisualQA)

Quality assurance is an important part of neuroimaging data processing, but it is also one of the least standardized processes. This project builds an open educational website with annotated examples of common imaging artifacts, practical visual inspection guidelines, and curated resources — to help researchers learn QA and perform it more consistently.

Started around MRI/fMRI and now expanding to EEG, with QA resources planned for both.

Built at Neurohackademy 2026.

## How it works

Tools are stored as YAML files in `_data/tools/`, one file per category (categories are declared in `_data/categories.yml`). A weekly GitHub Actions cron job (`.github/workflows/health_check.yml`) runs `scripts/update_health.py`, which checks each tool's GitHub repo and writes `_data/health.yml` — the source of the status dots in the directory. The site is built with Jekyll and hosted on GitHub Pages.

## Modalities

Tools carry a top-level `modality` (`MRI` or `EEG`) plus an optional `submodality` for refinement within it:

```yaml
- name: MRIQC
  description: Extracts image quality metrics from structural and functional MRI.
  url: https://github.com/nipreps/mriqc
  github: nipreps/mriqc
  language: Python
  modality: MRI
  submodality: multi
```

The pill row at the top of the directory filters on `modality`. `submodality` is carried through to the DOM as `data-submodality` but is not filtered on yet — that's the hook for adding sub-modality filtering (fMRI, diffusion, …) later.

## Provenance

Seeded from [openmritools.github.io](https://github.com/openmritools/openmritools.github.io) — layout, CSS, and health-check automation. The top-row modality pills come from [openimagingtools.github.io](https://github.com/openimagingtools/openimagingtools.github.io).

**The tool data in `_data/tools/` is still the inherited MRI corpus** — placeholder content to prune and replace, not a curated NeuroQA list.

## Not yet wired up

- **Suggestion form** (`contribute.html`) — upstream POSTs to a Cloudflare Worker that opens a GitHub Issue. That worker was not copied, so the form is disabled until one is deployed for this repo.
- **Auto-discovery** — upstream's `scripts/discover_tools.py` was not copied.
- **Custom domain** — no `CNAME`; configured for the GitHub Pages project URL, so `_config.yml` sets `baseurl: "/VisualQA"`.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).
