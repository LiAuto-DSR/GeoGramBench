<div align="center">

 # GeoGramBench

<div>
GeoGramBench: Benchmarking the Geometric Program Reasoning  in Modern LLMs
</div>
</div>

<div align="center">
[![Hugging Face Collection](https://img.shields.io/badge/Agentica-fcd022?style=for-the-badge&logo=huggingface&logoColor=000&labelColor)](https://huggingface.co/datasets/LiAuto-DSR/GeoGramBench)
</div>

## Overview
Geometric spatial reasoning forms the foundation of many applications in artificial intelligence, yet the ability of large language models (LLMs) to operate over geometric information expressed in procedural code remains underexplored. In this paper, we address this gap by formalizing the \texttt{Program-to-Geometry} task, which challenges models to translate procedural drawing code into accurate and abstract geometric reasoning. To evaluate this capability, we present \textbf{GeoGramBench}, a benchmark of 500 carefully refined problems organized by a tailored three-level taxonomy that considers geometric complexity rather than traditional mathematical reasoning complexity. Our comprehensive evaluation of 17 frontier LLMs reveals consistent and pronounced deficiencies: even the most advanced models achieve less than 50\% accuracy at the highest abstraction level. These results highlight the unique challenges posed by program-driven spatial reasoning and establish GeoGramBench as a valuable resource for advancing research in symbolic-to-spatial geometric reasoning.


## Taxonomy
We propose a taxonomy whose primary principle is the construction of increasingly complex mathematical geometric diagrams from code.
<strong>Primitive Recognition</strong>: Problems involving procedural code that specify only one or two geometric primitives (e.g., points, lines, arcs, circles, polygons), focusing on basic mathematical properties such as length, area, or angle.
<strong>Local Relation Composition</strong>: Problems with multiple local geometric elements, requiring the recognition, integration, and composition of spatial relationships among sub-components of the diagram.
<strong>Global Abstract Integration</strong>: Items demanding spatial direction, parameterization, recursion, 3D objects, composite structures, or advanced geometric operations (e.g., rotation, folding, projection), thus requiring not only the construction of complex diagrams but also global and stepwise spatial reasoning across the entire configuration.

![](figures/geogrambench_example.png)

## Evaluation
We evaluate a total of 17 mainstream large language models (LLMs), spanning both proprietary API and leading open-source systems. The closed-source models include GPT-4o, GPT-o3-mini, the GPT-o1 series, and Gemini-Pro-1.5. The open-source models cover a wide range of scales, including DeepSeek-R1, DeepSeek-v3-0324, and QwQ-32B, as well as other prominent models from 32B down to 1.5B parameters: DeepSeek-R1-distillation variants, Bespoke-Stratos-32B, s1.1-32B, LIMO-32B, Sky-T1-mini-7B, and DeepScaleR-1.5B-preview.

| Model | Primitive | Compositional | Abstract | ALL |
|-------|-----------|-----------|-----------|--------------|
| <strong>Closed-source Models</strong> |
| GPT-o3-mini | 84.33 | 75.66 | 42.16 | 70.00 |
| GPT-o1 | <strong>86.76</strong> | <strong>76.02</strong> | <strong>43.35</strong> | <strong>70.92</strong> |
| GPT-o1-preview | 74.79 | 55.98 | 26.20 | 53.15 |
| GPT-o1-mini | 79.62 | 63.21 | 29.09 | 58.94 |
| GPT-4o | 39.81 | 21.29 | 4.96 | 21.40 |
| Gemini-Pro-1.5 | 49.26 | 31.79 | 15.92 | 31.64 |
| <strong>Open-source Models</strong> |
| DeepSeek-R1 | <strong>85.66</strong> | <strong>75.27</strong> | <strong>40.38</strong> | <strong>69.17</strong> |
| DeepSeek-v3-0324 | 80.57 | 68.89 | 27.67 | 62.05 |
| QwQ-32B | 85.17 | 73.12 | 37.92 | 67.20 |
| DeepSeek-R1-Distill-Qwen-32B | 79.78 | 67.83 | 35.92 | 62.68 |
| Bespoke-Stratos-32B | 62.50 | 42.56 | 17.02 | 40.55 |
| s1.1-32B | 75.37 | 58.96 | 26.58 | 54.60 |
| LIMO-32B | 76.59 | 59.63 | 25.53 | 54.98 |
| DeepSeek-R1-Distill-Qwen-7B | 72.79 | 58.74 | 24.16 | 53.38 |
| Sky-T1-mini-7B | 71.45 | 57.75 | 24.79 | 52.70 |
| DeepSeek-R1-Distill-Qwen-1.5B | 60.29 | 39.02 | 11.03 | 36.70 |
| DeepScaleR-1.5B-preview | 65.44 | 47.89 | 15.76 | 43.83 |