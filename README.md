# Alzheimer’s Brain Shape Analysis
> Graduate research-style final project (unpublished paper)
>
> M.S. in Statistics, University of Massachusetts Amherst


This project applies geometric and statistical modeling to analyze structural differences in the corpus callosum between Alzheimer’s patients and healthy controls. Using Kendall’s shape space, Fréchet means, and energy-distance permutation testing, it demonstrates how non-Euclidean statistics can capture subtle but meaningful geometric variations that traditional linear methods overlook.

---

## Paper Overview

Traditional Euclidean approaches to shape data treat anatomical structures as vectors in flat space, ignoring variation due to **rotation, translation, and scale**.  
This project instead models each shape as a point on a **Riemannian manifold** (Kendall’s shape space) allowing for mathematically valid comparisons, averages, and inferences between shapes.

As part of the full analysis pipeline, two datasets were analyzed:

- **Simulated Shape Data (Validation Phase):**  
  Synthetic shapes of hands, hammers, and glasses were generated to test the behavior of the statistical pipeline under well-separated conditions.  
  These experiments confirmed that the methods could correctly identify group-level differences, recover meaningful Fréchet means, and form distinct clusters in shape space.

- **ADNI Brain Shape Data (Application Phase):**  
  Real 2D landmark data of the corpus callosum were extracted from the **Alzheimer’s Disease Neuroimaging Initiative (ADNI)** dataset.  
  Subjects were divided into *Control* and *Alzheimer’s* groups, and the same geometric tools were used to detect shape-based biomarkers.  
  The results revealed smoother, more rounded corpus callosum shapes among Alzheimer’s subjects—differences that were **statistically significant** under the energy-distance test and supported by clustering patterns.

Together, these datasets show a full analysis pipeline: from controlled simulation (method validation) to real neuroimaging data (practical application).  
Full mathematical background, statistical derivations, and figures are detailed in the accompanying paper (`paper.pdf`).


## Methodological Summary

| Technique                   | Description                                                                                                                                                                                                                                                                                     |
| --------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Manifold Geometry**       | Kendall’s shape space models shapes as points on a curved manifold rather than a flat Euclidean plane. This allows for mathematically valid averaging, distance measurement, and inference while preserving the intrinsic geometry of the data.                                                    |
| **Fréchet Mean**            | The Fréchet mean extends the concept of an average to non-Euclidean spaces. It computes the “central” shape by minimizing the sum of squared geodesic (manifold) distances between all shapes, producing an intrinsic mean that’s invariant to rotation, scale, and translation.                   |
| **Energy Distance Test**    | This nonparametric hypothesis test measures how different two distributions are based on pairwise distances between their elements. By resampling group labels via permutation, it provides a robust, distribution-free way to assess whether Alzheimer’s and control shapes differ statistically. |
| **Hierarchical Clustering** | Shapes are grouped based on Kendall distances using agglomerative linkage. This reveals whether brain shape differences naturally separate into clusters corresponding to the Alzheimer's and control groups.                                                                     |
| **Data Visualization**      | Statistical and geometric results are visualized using shape overlays, dendrograms, and heatmaps of Kendall distances. These plots communicate how geometric patterns vary between groups and validate findings from the statistical tests.                                                        |


