+++
title = "FLIMAnalyzer"
weight = 2
description = "Probing cellular metabolic states with fluorescence lifetime imaging microscopy"

[extra]
image = "/images/projects/flim.jpg"
legend = "Fluorescence lifetime imaging microscopy"
publications = [
    "publications/2026-label-free-optical-biomarker-for-prostate.md",
    "publications/2025-measuring-metabolic-changes-in-cancer-cells.md",
]
github = "https://github.com/uvaKCCI/flimanalyzer"
collaborators = ["Ammasi Periasamy, Horst Wallrabe, Shagufta Rehman Alam, Brian Mbogo, Jianxin Zhang, Thomas Cassidy"]
funding = "Internal seed grant"
+++

FLIMAnalyzer is a recently published Python package, developed in collaboration with Dr. Ammasi Periasamy’s group (Keck Center for Cellular Imaging) to support fluorescence lifetime imaging microscopy (FLIM) analysis. It applies machine- and deep-learning techniques to enhance the sensitivity of detecting changes in cellular redox states. Designed as an extensible analysis framework, the package includes plugins for importing multi-parameter FLIM data from tabular CSV files, filtering and organizing the data in spreadsheet format, performing statistical analyses, and visualizing data. Deep learning modules with PyTorch-based autoencoders enable feature extraction and data augmentation, including built-in support for hyperparameter tuning. The modular architecture allows for the addition of new plugins and the composition of custom, multi-stage analysis workflows by chaining plugin-defined tasks into a directed acyclic graph. As with MitosisAnalyzer, this package leverages Prefect for task orchestration, with Dask available for distributed execution at scale. Although originally developed for FLIM data analysis, the framework is adaptable to other multi-feature datasets structured in tabular format.