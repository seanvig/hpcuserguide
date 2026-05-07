# Sasquatch HPC User Guides

A Quarto book providing guidance, best practices, and recommendations for users of Sasquatch, a High Performance Computing (HPC) cluster.

**[View the published book](https://seanvig.github.io/hpcuserguide/)**

> **Note:** This is an archival portfolio project — a snapshot of documentation built for a previous organization. Content may not reflect current Slurm syntax or HPC best practices.

---

## About

This guide covers the full lifecycle of HPC usage, from initial onboarding through advanced job optimization. It is structured for users at all experience levels:

- **New to HPC entirely?** Start with the Introduction to HPC Clusters section.
- **Familiar with HPC but new to Sasquatch?** Start with the Quick Start Guide.

### Topics Covered

| Part | Content |
|---|---|
| HPC Quick Start Guide | Onboarding, quick start, examples, FAQ |
| Sasquatch | Cluster overview, access, storage, policies |
| Slurm | Job scheduler, submission, monitoring, scaling |
| Software | Modules, containers, R, Mamba, installation |
| Posit | Posit Workbench and Connect |
| Working Smarter | Optimization, parallelism, GPUs, Nextflow, SSH, Git, IDEs |
| RSC Resources | Support, training sessions, Linux cheat sheet |

---

## Building the Book

### Prerequisites

- [Quarto CLI](https://quarto.org/docs/get-started/) (any recent release)
- R (≥ 4.0 recommended)
- R packages listed in `DESCRIPTION`

### Install R Dependencies

```r
# Option 1: using renv (recommended for reproducibility)
install.packages("renv")
renv::restore()

# Option 2: install packages from DESCRIPTION manually
install.packages(c(
  "knitr", "rmarkdown", "quarto",
  "dplyr", "ggplot2", "readr", "tibble",
  "tidyr", "purrr", "stringr", "kableExtra"
))
```

### Render the Book

```bash
quarto render
```

Output is written to `_book/`.

### Live Preview

```bash
quarto preview
```

Opens the book in a browser and reloads automatically as you edit `.qmd` files.

---

## Repository Structure

```
_quarto.yml          # Book configuration (structure, theme, format)
_variables.yml       # Shared variables (paths, links used across chapters)
DESCRIPTION          # R package metadata and declared dependencies
index.qmd            # Preface / book home page
*.qmd                # Chapter source files
images/              # Screenshots and figures referenced by chapters
styles.css           # Custom HTML styling
_book/               # Rendered HTML output (generated, not committed)
.quarto/             # Quarto build cache (generated, not committed)
```

---

## Technical Details

| Property | Value |
|---|---|
| Engine | knitr (R) |
| Output format | HTML |
| HTML theme | cosmo |
| Quarto extensions | None |
| Code evaluation | Disabled (`eval: false`) — code is shown but not run at render time |

### R Package Dependencies

| Category | Packages |
|---|---|
| Core rendering | knitr, rmarkdown, quarto |
| Data wrangling | dplyr, readr, tibble, tidyr, purrr, stringr |
| Visualization | ggplot2 |
| Table formatting | kableExtra |
