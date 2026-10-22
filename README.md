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

| Configuration                    | Dataset Identifier | Description                                               |
| -------------------------------- | ------------------ | --------------------------------------------------------- |
| No Global Illumination           | `NoGI`             | Baseline rendering configuration without GI               |
| Radiance Cascades                | `RC`               | Global illumination approach based on radiance cascades   |
| Real-Time Lighting Method        | `RTLM`             | Real-time lighting configuration used in the experiments  |
| Screen Space Global Illumination | `SSGI`             | Screen-space approach to estimating indirect illumination |

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

| Component          | Specification                   |
| ------------------ | ------------------------------- |
| Game Engine        | Unity                           |
| Unity Version      | 6000.2.12f1                     |
| Rendering Pipeline | Universal Render Pipeline (URP) |

### Hardware

| Component | Specification                      |
| --------- | ---------------------------------- |
| GPU       | NVIDIA GeForce RTX 4060 Laptop GPU |
| CPU       | Intel Core i7-13620H               |

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

Russian Version:

# Radiance Cascades в сравнении со стандартными методами глобального освещения Unity

Экспериментальные данные и сравнение производительности для научной работы **«Сравнительная оценка методов глобального освещения в реальном времени в Unity URP» (Comparative Evaluation of Real-Time Global Illumination Methods in Unity URP)**, подготовленной в рамках исследовательского проекта для конференции DiGRA.

## Обзор

Глобальное освещение (Global Illumination, GI) — важная технология компьютерной графики в реальном времени, позволяющая свету взаимодействовать с поверхностями и влиять на освещение окружающей среды, обеспечивая более реалистичное и визуально согласованное изображение.

Однако различные методы глобального освещения предъявляют разные требования к производительности, поэтому выбор подходящего метода рендеринга имеет особое значение для приложений реального времени и видеоигр.

Этот репозиторий содержит экспериментальные измерения и материалы для сравнения, использованные при оценке метода **Radiance Cascades** наряду с другими конфигурациями глобального освещения в Universal Render Pipeline (URP) движка Unity.

Эксперименты сосредоточены на оценке производительности рендеринга в сценах разных типов и с различными визуальными стилями.

## Цели исследования

Основные цели исследования:

- Сравнить производительность различных конфигураций глобального освещения в Unity.
- Оценить вычислительные затраты метода Radiance Cascades относительно альтернативных подходов.
- Проанализировать частоту кадров (FPS) и время рендеринга одного кадра (Frame Time).
- Исследовать влияние характеристик сцены на производительность рендеринга.
- Предоставить экспериментальные данные для дальнейшего анализа и воспроизведения результатов.

## Сравниваемые конфигурации рендеринга

Экспериментальные наборы данных содержат измерения для четырёх конфигураций рендеринга:

| Конфигурация                                 | Идентификатор набора данных | Описание                                                                  |
| -------------------------------------------- | --------------------------- | ------------------------------------------------------------------------- |
| Без глобального освещения                    | `NoGI`                      | Базовая конфигурация рендеринга без GI                                    |
| Radiance Cascades                            | `RC`                        | Метод глобального освещения, основанный на каскадах излучения             |
| Метод освещения в реальном времени           | `RTLM`                      | Конфигурация освещения в реальном времени, использованная в экспериментах |
| Глобальное освещение в экранном пространстве | `SSGI`                      | Метод оценки непрямого освещения в экранном пространстве                  |

Эти конфигурации оцениваются на нескольких типах сцен, чтобы выявить различия в производительности рендеринга.

## Экспериментальные сцены

В измерениях представлены три категории сцен.

### 1. Изометрическая сцена

Изометрическое окружение, используемое для исследования производительности рендеринга в сцене с изометрической перспективой.

### 2. Реалистичная сцена

Реалистичное окружение, предназначенное для оценки производительности глобального освещения в условиях более детализированного рендеринга.

### 3. Стилизованная сцена

Стилизованное окружение, используемое для изучения поведения различных методов освещения при создании нереалистичной, или нефотореалистичной, графики.

В совокупности эти сцены позволяют сравнить производительность методов освещения в различных визуальных условиях.

## Структура репозитория

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

### Организация наборов данных

Каждая директория экспериментальной сцены содержит:

- **CSV-файлы:** исходные измерения, собранные во время отдельных запусков рендеринга.
- **Книги Excel:** таблицы сравнения производительности для соответствующей сцены.
- **Директории Unity:** дополнительные материалы, связанные с экспериментами, если они доступны.

CSV-файлы используют следующий формат именования:

```text
gi_run_<METHOD>_<DATE>_<TIME>.csv
```

Например:

```text
gi_run_RC_2026-02-19_16-02-12.csv
```

Идентификатор метода указывает, какая конфигурация рендеринга использовалась во время измерения.

## Метрики производительности

Исследование сосредоточено на двух основных метриках производительности.

### Частота кадров (FPS)

FPS (Frames Per Second) показывает, сколько кадров отображается за одну секунду.

Более высокий FPS, как правило, означает более высокую пропускную способность рендеринга.

### Время рендеринга кадра (Frame Time)

Frame Time — это время, необходимое для рендеринга одного кадра, обычно измеряемое в миллисекундах.

Меньшее время рендеринга кадра, как правило, свидетельствует о более высокой производительности.

Приблизительная зависимость между FPS и временем рендеринга кадра выражается формулой:

\[
\text{Frame Time (ms)} = \frac{1000}{\text{FPS}}
\]

Обе метрики позволяют оценить вычислительные затраты и характеристики производительности исследуемых конфигураций рендеринга.

## Экспериментальное окружение

Эксперименты проводились с использованием следующего аппаратного и программного обеспечения.

### Программное обеспечение

| Компонент           | Характеристики                  |
| ------------------- | ------------------------------- |
| Игровой движок      | Unity                           |
| Версия Unity        | 6000.2.12f1                     |
| Конвейер рендеринга | Universal Render Pipeline (URP) |

### Аппаратное обеспечение

| Компонент                   | Характеристики                     |
| --------------------------- | ---------------------------------- |
| Графический процессор (GPU) | NVIDIA GeForce RTX 4060 Laptop GPU |
| Центральный процессор (CPU) | Intel Core i7-13620H               |

Результаты измерений относятся к указанной экспериментальной конфигурации и могут отличаться на других аппаратных платформах.

## Визуальное сравнение

Записи рендеринга доступны в видеороликах. Они дополняют количественные измерения и позволяют визуально сравнить результаты работы исследуемых конфигураций.

**Плейлист на YouTube:**

[Смотреть сравнение методов глобального освещения на YouTube](https://www.youtube.com/watch?v=daDjPJyB86o&list=PLaHv1eGKS6CyZF2IG05RV7KAHvvU5-xIQ)

Эти записи дополняют наборы данных о производительности, демонстрируя визуальный результат работы различных конфигураций.

## Работа с данными

Экспериментальные данные организованы по типам сцен и конфигурациям рендеринга.

Чтобы изучить результаты измерений:

1. Перейдите в директорию `Measured Data`.
2. Выберите одну из трёх папок с экспериментальными сценами.
3. Откройте соответствующие CSV-файлы, чтобы изучить записанные измерения.
4. Сравните результаты для конфигураций `NoGI`, `RC`, `RTLM` и `SSGI`.
5. Используйте книги Excel для дополнительного сравнения и анализа производительности.

CSV-файлы можно обрабатывать с помощью электронных таблиц или инструментов анализа данных, таких как Python и pandas.

### Пример: загрузка набора данных с помощью Python

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

Этот пример загружает файл с измерениями производительности метода Radiance Cascades и выводит первые строки данных и сводную статистику по столбцам.

## Воспроизводимость и ограничения

Репозиторий содержит записанные экспериментальные измерения и вспомогательные материалы для сравнения.

При интерпретации результатов следует учитывать следующие ограничения:

- Производительность может различаться в зависимости от GPU, CPU и конфигурации системы.
- Вычислительная нагрузка при рендеринге зависит от сложности сцены и условий освещения.
- FPS и время рендеринга кадра следует анализировать совместно.
- Визуальное качество и вычислительные затраты представляют собой разные аспекты производительности рендеринга.
- Репозиторий содержит преимущественно экспериментальные данные, а не полноценный готовый к запуску проект Unity.

Предоставленные наборы данных позволяют изучать и независимо анализировать результаты проведённых экспериментов.

## Научный контекст

**Научная работа:** Comparative Evaluation of Real-Time Global Illumination Methods in Unity URP

**Область исследования:** компьютерная графика, рендеринг в реальном времени, разработка игр.

**Конференция:** DiGRA.

Проект исследует компромиссы между производительностью рендеринга и различными методами глобального освещения в интерактивных средах реального времени.

## Лицензия

Репозиторий распространяется под лицензией **MIT**.

Полный текст лицензии представлен в файле [LICENSE](LICENSE).

## Благодарности

Этот репозиторий создан для поддержки исследований методов глобального освещения в реальном времени и оценки их производительности в Unity.

Экспериментальные наборы данных и материалы для визуального сравнения предоставляются в образовательных и исследовательских целях.
