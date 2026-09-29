+++
title = "Vistiq"
weight = 1
description = "Hierarchical spatiotemporal analytics across biological scales"

[extra]
image = "images/projects/vistiq.mp4"
poster = "images/projects/vistiq-poster.jpg"
image_side = "images/projects/vistiq.png"
legend = "Proliferation network of neural stem cells (NSCs) in the developing Drosophila brain. Note the bilateral symmetry of the two brain hemispheres. NSCs in magenta; proliferation marker in green. Data courtesy of [Sarah Siegrist](https://siegristlab.org)."
publications = []
github = "https://github.com/ksiller/vistiq"
collaborators = ["[Sarah Siegrist](https://siegristlab.org)", "Sagar Kasar"]
funding = "UVA Brain Institute"
+++

Biological systems are organized across interconnected spatial and temporal scales, from subcellular structures to tissues and whole organisms. While deep-learning methods have improved object detection in microscopy images, they often fail to capture higher-order spatial organization, temporal coordination, lineage relationships, and collective dynamics that underpin biological function. Consequently, rich volumetric and time-resolved datasets are reduced to fragmented measurements, limiting reproducibility, scalability, and interpretability in phenotypic analysis.

In collaboration with the Siegrist lab at UVA, we are developing Vistiq, a generalizable, modular computational framework for multi-scale quantitative analysis of biological imaging data.

- How do neural stem cells (NSCs), glia, and neurons organize in space and time to build the brain?

Built on the Prefect workflow orchestration engine, Vistiq integrates preprocessing, object detection, spatiotemporal analysis, and classification within a unified, configurable pipeline that scales from local workstations to GPU-enabled high-performance computing and cloud environments.

![Vistiq pipeline](/images/projects/vistiq-pipeline.png)

The framework is designed for extensibility: state-of-the-art segmentation and classification models can be incorporated through lightweight adapters, enabling rapid integration of emerging methods while leveraging scalable, high-throughput execution. Vistiq constructs hierarchical representations that combine intrinsic object features with spatial and temporal context, including graph-based models encoding proximity and neighborhood structure. We are currently extending Vistiq to support unsupervised phenotypic classification using classical and multimodal representation learning approaches. Analysis pipelines are defined using a fully declarative configuration, ensuring reproducibility, portability, and auditability across computational environments.
