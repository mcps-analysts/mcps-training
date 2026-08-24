# MCPS Training & Resources

This repository is the shared home for public-facing **training and research documentation for users of the Mexico City Prospective Study (MCPS)**.

It is designed as a **modular resource**. Individual subject areas can be developed as self-contained modules while sharing a common website, visual identity, navigation, terminology, translation framework, and publication process.

The first module is **Getting Started with R and JupyterLab on MCPS DNAnexus**, a beginner-friendly introduction for users who are new to DNAnexus and cloud-based analysis.

## Current content

### DNAnexus onboarding

The current tutorial introduces the core workflow for working with R and JupyterLab on MCPS DNAnexus, including:

- navigating an MCPS DNAnexus project;
- understanding persistent project storage and temporary JupyterLab computing;
- working with persistent DNAnexus (`[DX]`) notebooks;
- accessing project data from R;
- saving, ending, and resuming analyses;
- understanding computing resources and costs; and
- working safely with MCPS research data.

The repository also contains a small hands-on R notebook and synthetic training dataset used by the tutorial.

## Future scope

The repository is intended to grow as MCPS training and documentation needs develop.

Future modules may cover areas such as:

- non-genetic MCPS datasets and analysis workflows;
- survival analysis;
- NMR metabolomics;
- genetics datasets and analysis workflows;
- DNAnexus and computing guidance;
- data-access and data-use guidance; and
- future MCPS workshops.

As the repository grows, modules will remain logically separate while sharing the common MCPS training infrastructure.

The planned long-term repository architecture is documented in [`docs/decisions/0001-repository-architecture.md`](docs/decisions/0001-repository-architecture.md).

## Public-resource principle

This repository is intended to support a public-facing MCPS training resource.

It must not contain individual-level MCPS research data, restricted or confidential documentation, credentials or secrets, or other material that should not be publicly accessible.

Training examples should use synthetic or otherwise approved public material.

## Development and contact

The main developer and point of contact for this resource is:

**Diego Aguilar-Ramirez**  
Nuffield Department of Population Health, University of Oxford  
<diego.aguilar-ramirez@ndph.ox.ac.uk>

If you are considering developing new training or documentation material for this resource, please contact Diego so that its scope and integration with the wider MCPS training resource can be discussed.

## Local development

The website is built with [Quarto](https://quarto.org/).


