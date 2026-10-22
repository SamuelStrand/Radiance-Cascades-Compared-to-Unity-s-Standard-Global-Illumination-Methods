
# Radiance Cascades Compared to Unity's Standard Global Illumination Methods

Experimental data and performance comparisons for the research paper **"Comparative Evaluation of Real-Time Global Illumination Methods in Unity URP"**, prepared as part of a DiGRA conference research project.

## Overview

Global Illumination (GI) is an important technique in real-time rendering, allowing light to interact with surfaces and contribute to more realistic and visually consistent environments.

However, different GI techniques introduce different performance costs, making the choice of rendering method particularly important for real-time applications and video games.

This repository contains experimental measurements and comparison materials used to evaluate **Radiance Cascades** alongside other global illumination configurations in Unity's Universal Render Pipeline (URP).

The experiments focus on rendering performance across different scene types and visual styles.

## Research Objectives

The main objectives of this research are to:

- Compare the performance of different global illumination configurations in Unity.
- Evaluate the computational cost of Radiance Cascades relative to alternative approaches.
- Analyze frame rate (FPS) and frame time measurements.
- Investigate how scene characteristics influence rendering performance.
- Provide experimental data for further analysis and reproducibility.

## Compared Rendering Configurations

The experimental datasets contain measurements for four rendering configurations:

| Configuration | Dataset Identifier | Description |
|---|---|---|
| No Global Illumination | `NoGI` | Baseline rendering configuration without GI |
| Radiance Cascades | `RC` | Global illumination approach based on radiance cascades |
| Real-Time Lighting Method | `RTLM` | Real-time lighting configuration used in the experiments |
| Screen Space Global Illumination | `SSGI` | Screen-space approach to estimating indirect illumination |

These configurations are evaluated across multiple scene types to explore differences in rendering performance.

## Experimental Scenes

Three scene categories are included in the measurements.

### 1. Isometric Scene

An isometric environment used to examine rendering performance in a scene with an isometric visual perspective.

### 2. Realistic Scene

A realistic environment used to evaluate global illumination performance under more visually detailed rendering conditions.

### 3. Stylized Scene

A stylized environment used to investigate the behavior of different lighting techniques in non-photorealistic rendering.

Together, these scenes provide a basis for comparing performance across different visual contexts.

## Repository Structure

```text
.
├── Measured Data/
│   ├── Isometric/
│   │   ├── Performance_comparison_Isometric.xlsx
│   │   └── gi_run_*.csv
│   │
│   ├── Realistic FPS/
│   │   ├── Performance_comparison_Realistic.xlsx
│   │   ├── Unity/
│   │   └── gi_run_*.csv
│   │
│   └── Stylized Fps/
│       ├── Performance_comparison_Stylized.xlsx
│       ├── Unity/
│       └── gi_run_*.csv
│
├── .gitattributes
├── LICENSE
└── README.md
```

### Dataset Organization

Each experimental scene directory contains:

- **CSV files:** Raw measurements collected during individual rendering runs.
- **Excel workbooks:** Performance comparison spreadsheets for the corresponding scene.
- **Unity directories:** Additional experiment-related materials where available.

The CSV files follow the naming convention:

```text
gi_run_<METHOD>_<DATE>_<TIME>.csv
```

For example:

```text
gi_run_RC_2026-02-19_16-02-12.csv
```

The method identifier specifies the rendering configuration used during the measurement.

## Performance Metrics

The study focuses on two primary performance metrics.

### Frames Per Second (FPS)

FPS represents the number of frames rendered per second.

Higher FPS generally indicates better rendering throughput.

### Frame Time

Frame time represents the time required to render an individual frame, typically measured in milliseconds.

Lower frame times generally indicate better rendering performance.

The relationship between FPS and frame time is approximately:

\[
\text{Frame Time (ms)} = \frac{1000}{\text{FPS}}
\]

Both measurements help evaluate the computational requirements and performance characteristics of the tested rendering configurations.

## Experimental Environment

The experiments were performed using the following hardware and software environment.

### Software

| Component | Specification |
|---|---|
| Game Engine | Unity |
| Unity Version | 6000.2.12f1 |
| Rendering Pipeline | Universal Render Pipeline (URP) |

### Hardware

| Component | Specification |
|---|---|
| GPU | NVIDIA GeForce RTX 4060 Laptop GPU |
| CPU | Intel Core i7-13620H |

Performance results are specific to the experimental environment and may vary on other hardware configurations.

## Visual Comparisons

Recorded rendering videos are available to support the quantitative measurements and provide visual comparisons between the tested configurations.

**YouTube Playlist:**

[Watch Global Illumination Comparisons on YouTube](https://www.youtube.com/watch?v=daDjPJyB86o&list=PLaHv1eGKS6CyZF2IG05RV7KAHvvU5-xIQ)

These recordings complement the performance datasets by illustrating the visual output of the experimental configurations.

## Working with the Data

The experimental data is organized by scene and rendering configuration.

To examine the measurements:

1. Navigate to the `Measured Data` directory.
2. Select one of the three experimental scene folders.
3. Open the corresponding CSV files to inspect the recorded measurements.
4. Compare the measurements across the `NoGI`, `RC`, `RTLM`, and `SSGI` configurations.
5. Use the Excel workbooks for additional performance comparison and analysis.

CSV files can be processed using spreadsheet applications or data analysis tools such as Python and pandas.

### Example: Loading a Dataset with Python

```python
import pandas as pd

file_path = (
    "Measured Data/Isometric/"
    "gi_run_RC_2026-02-19_16-02-12.csv"
)

df = pd.read_csv(file_path)

print(df.head())
print(df.describe(include="all"))
```

This example loads a Radiance Cascades measurement file and displays its first rows and summary statistics.

## Reproducibility and Limitations

The repository provides recorded experimental measurements and supporting comparison materials.

When interpreting the results, consider the following:

- Performance may vary depending on GPU, CPU, and system configuration.
- Rendering workload depends on scene complexity and lighting conditions.
- FPS and frame time should be interpreted together.
- Visual quality and computational cost represent different aspects of rendering performance.
- The repository primarily contains experimental data rather than a complete, ready-to-run Unity project.

The provided datasets can be used to inspect and independently analyze the recorded experimental results.

## Research Context

**Paper:** Comparative Evaluation of Real-Time Global Illumination Methods in Unity URP

**Research Area:** Computer Graphics, Real-Time Rendering, Game Development

**Conference Context:** DiGRA

The project investigates trade-offs between rendering performance and global illumination methods in the context of real-time interactive environments.

## License

This repository is distributed under the **MIT License**.

See the [LICENSE](LICENSE) file for the complete license text.

## Acknowledgments

This repository was created to support research on real-time global illumination techniques and performance evaluation in Unity.

The experimental datasets and visual comparison materials are provided for educational and research purposes.
