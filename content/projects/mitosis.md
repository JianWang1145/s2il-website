+++
title = "MitosisAnalyzer"
weight = 3
description = "Unsupervised tracking of mitotic spindle dynamics"

[extra]
image = "/images/projects/mitosis.mp4"
poster = "images/projects/mitosis-poster.jpg"
legend = "First division of a C. elegans embryo. Mitotic spindle (green) and DNA (magenta) fluorescently labeled. Data courtesy of Vitaly Zimyanin and Stefanie Redemann."
publications = ["publications/2026-chromokinesin-klp-19-regulates-microtubule-overlap.md"]
github = "https://github.com/uvarc/mitosisanalyzer"
collaborators = ["Vitaly Zimyanin", "Stefanie Redemann", "Xavier Horton"]
funding = ""
+++

MitosisAnalyzer is a Python package for tracking spindle poles in dividing cells over time, developed in collaboration with Dr. Stefanie Redemann’s group in the School of Medicine. Accurate tracking of spindle poles enables detailed quantification of cell division dynamics, offering critical insight into mechanisms of chromosome segregation and potential cellular defects associated with disease. The tool converts time-series image data into spindle pole trajectories through a sequence of tasks: denoising, normalization, cell and spindle pole segmentation, coordinate extraction, and time-series plots using a combination of deep learning and standard Python packages (Cellpose, OpenCV, Scikit-Image, Pandas, Seaborn). On the backend, the package uses the Prefect workflow engine to orchestrate these steps into a directed acyclic graph, allowing seamless scaling from local execution to parallel or distributed processing with Dask. The package runs on local or HPC/cloud systems and includes a plugin for the open-source Napari image viewer for interactive inspection and curation of spindle pole trajectories overlaid on the raw data. This combination of scalable batch processing and user-friendly visualization has significantly boosted the group’s analysis throughput.
