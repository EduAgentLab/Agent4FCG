# Agent4FCG: An Agent-based Framework for Feedback Comment Generation in Automated Writing Evaluation
Package Description (Code + Dataset + Generated Feedback Comments)

This package includes the implementation code, benchmark input texts, and pre-generated feedback comments produced under multiple model and method settings. It supports:
- Benchmark input texts (Dataset/)
- Reproducing prompts/configurations and generation pipelines (Code/)
- Pre-generated feedback comments across multiple base models and methods (Generated Feedback/)

============================================================
1. Package Structure
============================================================

.
├── Code/
│   ├── Agent4FCG.yml
│   ├── IM1_Final.yml
│   ├── IM2_Final.yml
│   ├── IM3_Final.yml
│   ├── mkIM.py
│   └── mkFeedback.py
├── Dataset/
│   ├── R1-T1-01.txt
│   ├── R1-T1-02.txt
│   ├── ...
│   └── (more .txt files)
└── Generated Feedback/
    ├── gpt-4.1-mini_Agent4FCG/
    ├── gpt-4.1-mini_IM1/
    ├── gpt-4.1-mini_IM2/
    ├── gpt-4.1-mini_IM3/
    ├── Qwen3-14B_IM1/
    ├── Qwen3-14B_IM2/
    ├── Qwen3-14B_IM3/
    ├── Qwen3-14B_Agent4FCG/
        ├── C1/
        ├── C2/
        ├── ...
        └── C9/

Directory Notes:
1) Code/
- Contains executable scripts and YAML workflow configuration files deployed on the Dify platform.
  - mkIM.py: Generates intermediate outputs for the IM1/IM2/IM3 pipelines (details depend on script arguments and configuration).
  - mkFeedback.py: Generates the final feedback comments produced by Agent4FCG.
  - Agent4FCG.yml: The Dify workflow configuration for the Agent4FCG pipeline.
  - ProEval-IM1_Final.yml / ProEval-IM2_Final.yml / ProEval-IM3_Final.yml: Dify workflow configurations for the IM pipelines.

2) Dataset/
- Contains the input texts (.txt).
- File naming follows a sample ID convention such as “R1-T1-01.txt”.

3) Generated Feedback/
- Contains generated feedback outputs, organized hierarchically by:
  (1) Base model: gpt-4.1-mini / Qwen3-14B
  (2) Method/pipeline: Agent4FCG / IM1 / IM2 / IM3
  (3) Dimension: C1 … C9
- Each dimension folder contains output files aligned with the sample IDs in Dataset/.

============================================================
2. Usage (Reproduction Entry Points)
============================================================

1) Inspect the dataset
- Each .txt file under Dataset/ is a benchmark input sample.
Example:
- ls Dataset | head

2) Generate IM intermediate results (IM1/IM2/IM3)
- python Code/mkIM.py

3) Generate Agent4FCG feedback comments
- python Code/mkFeedback.py
