# Mechanistic Analysis Of Universality: Numerical Comparison Circuits Across Transformer Architectures

### TL;DR: 
We study the internal circuit structures of pretrained transformers on numerical comparison taks and whether these circuits are universal across models of different families and size.

### Abstract
Transformer language models reliably achieve high accuracy on many reasoning tasks; however, their internal mechanisms are not fully understood. Mechanistic interpretability seeks to remedy this gap by identifying task circuits within individual models, but it is unclear whether such circuits generalize across model families and scales. In this work, we study the universality of circuits through the lens of numerical comparisons, a simple and controlled task that enables clean and causal interventions. We conduct experiments on a set of transformer models spanning different families and sizes from 1.7b to 9b parameters. We find that models within the Qwen family exhibit a highly consistent circuit structure across architecture and scale, featuring localized attention heads that write a task relevant signal. In contrast, models from other families show qualitatively different implementations, where task relevant information emerges much earlier and is distributed across components as opposed to being concentrated within a small set of attention heads. These results serve as evidence that task behavior similarities do not imply mechanistic universality and highlight the necessity for cross model comparisons to claim generalization of internal circuits.

### Link to publication 
Accepted to LIT Workshop @ ICLR 2026: https://openreview.net/forum?id=79igg0kRtd&noteId=mSsda8vUhv

## Setup

### Conda env

```
conda create --name env python=3.10
conda activate env
```

### Install reqs

```
pip install -r requirements.txt
```

### Run

Project in active development, don't run me yet

## Project Structure

```
project/
├── output/                   # Raw dataset files (.parquet)
├── outputs_steering/         # Results and plots from activation steering experiments
├── Results/                  # Comprehensive experimental results (Ablation, Attention, Logits)
├── src/
│   ├── Experiments/          # Core experiment implementations (Ablation, Patching, Logit Lens)
│   ├── fisher_score/         # Pipeline and utils to calculate fisher scores (neuron relevance)
│   ├── steering/             # Activation steering logic and evaluation scripts
│   ├── Interpretability/     # General interpretability functions and path patching
│   ├── test_suite/           # Evaluation benchmarks and task configurations (YAML)
│   ├── utils/                # Data generation, model loading, and shared utilities
│   ├── lm-eval/              # Integration with language model evaluation frameworks
│   └── Evaluator.py          # Main evaluation entry point
├── tasks/                    # Task-specific configurations
└── requirements.txt          # Project dependencies
```
