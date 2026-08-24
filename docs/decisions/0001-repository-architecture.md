# ADR 0001: Single modular repository for MCPS training and resources

**Status:** Accepted  
**Date:** 2026-08-24

## Context

MCPS training and public-facing research documentation are expected to expand substantially over time.

The initial resource is a beginner-friendly tutorial for using R and JupyterLab on DNAnexus. Future material may cover multiple domains, including non-genetic MCPS data, survival analysis, NMR metabolomics, genetics datasets and analysis workflows, and broader computing or data-access guidance.

These resources are expected to share substantial infrastructure:

- MCPS branding and visual design;
- English/Spanish translations;
- common terminology;
- website navigation;
- data-safety guidance;
- reusable screenshots and components;
- Quarto configuration and deployment; and
- maintenance by a shared group of developers.

Creating a separate repository for each tutorial or subject area would duplicate this infrastructure and make it harder to maintain a coherent public-facing resource.

## Decision

Maintain MCPS training and public-facing research documentation in a **single modular repository**:

```text
mcps-training/
```

The repository will support a single Quarto-based website. Individual subject areas will be treated as logically separate **modules** that share the common site infrastructure.

The current DNAnexus onboarding tutorial is the **first module**, rather than the defining purpose of the repository.

## Modular architecture

At present, the repository contains only one substantial module, so its structure remains relatively flat:

```text
mcps-training/
├── participant-guide/
├── training-materials/
├── instructor-guide/
├── assets/
├── docs/
├── index.qmd
├── _quarto.yml
└── README.md
```

In the current structure:

- `participant-guide/` contains the participant-facing DNAnexus onboarding tutorial;
- `training-materials/` contains the practical materials used by that tutorial;
- `instructor-guide/` is reserved for associated instructor/project-manager guidance;
- `assets/` contains shared images and styling; and
- `docs/` contains developer and architecture documentation.

As additional substantial subject areas are introduced, the repository is expected to evolve towards a module-based structure such as:

```text
mcps-training/
├── modules/
│   ├── dnanexus-onboarding/
│   │   ├── participant-guide/
│   │   ├── training-materials/
│   │   └── instructor-guide/
│   │
│   ├── survival-analysis/
│   │   ├── participant-guide/
│   │   ├── training-materials/
│   │   └── instructor-guide/
│   │
│   ├── nmr-metabolomics/
│   │   ├── participant-guide/
│   │   ├── training-materials/
│   │   └── instructor-guide/
│   │
│   └── genetics/
│       ├── participant-guide/
│       ├── training-materials/
│       └── instructor-guide/
│
├── assets/
├── docs/
├── index.qmd
├── _quarto.yml
└── README.md
```

This structure is illustrative rather than fixed. The exact organisation should be reconsidered when a second substantial module is developed.

The current DNAnexus files will **not** be reorganised pre-emptively. Moving them under `modules/dnanexus-onboarding/` should be considered when the repository actually needs to accommodate additional modules.

The aim is to keep individual subject areas logically separate while preserving shared infrastructure at repository level.

## Shared versus module-specific content

As the repository grows, broadly reusable resources should remain shared where practical. Examples include:

- MCPS branding and CSS;
- common website configuration;
- shared data-safety guidance;
- translation conventions;
- architecture documentation; and
- reusable site components.

Content that belongs to a particular subject area should remain within that module. Examples include:

- domain-specific tutorials;
- notebooks;
- synthetic training datasets;
- workshop exercises; and
- instructor guidance specific to that module.

This separation should allow modules to develop independently without duplicating the common infrastructure.

## When to create a separate repository

A future module should normally remain within `mcps-training`.

A separate repository should be considered only when there is a substantive reason, such as:

- substantially different ownership or maintenance responsibilities;
- a different security or access model;
- a substantially different technical stack;
- an independent software or workflow lifecycle;
- requirements that make shared Quarto deployment impractical; or
- another clear need for independent versioning and governance.

The size of a module or number of pages alone is **not** a reason to create a separate repository.

## Public-repository principle

The repository is intended to be suitable for public release.

Restricted MCPS content must therefore not be placed in this repository merely because it is contained in a particular directory or module.

The repository must never contain:

- individual-level MCPS research data;
- credentials or secrets;
- restricted project information;
- non-public documentation; or
- other material that should not be publicly accessible.

Public documentation and training should use synthetic or otherwise approved examples.

## Consequences

### Benefits

- One coherent public-facing MCPS training and documentation resource.
- Shared branding, terminology, navigation, and deployment.
- A common framework for future English/Spanish versions.
- Reusable onboarding and data-safety guidance.
- Less duplication across subject areas.
- Modules that can evolve independently within a shared framework.
- One historical record of architecture and design decisions.

### Trade-offs

- The repository will become larger and cover multiple subject areas.
- Navigation and repository structure will need to evolve as modules are added.
- Shared conventions will need to be maintained carefully.
- Reorganisation will eventually be required when the current single-module structure becomes multi-module.
- Some future modules may ultimately justify independent repositories.

## Future review

This decision should be revisited when a **second substantial module** is ready to be incorporated.

At that point, the maintainers should decide how best to implement the `modules/` structure, migrate the existing DNAnexus onboarding material, and update the Quarto navigation without unnecessarily disrupting the public site.

The main aim of this decision is therefore not to prescribe the final directory structure in advance, but to establish the principle that MCPS training and public-facing documentation should develop as a **coherent, modular resource** rather than as a collection of unrelated repositories.
