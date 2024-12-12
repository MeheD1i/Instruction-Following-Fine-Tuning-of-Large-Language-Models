# Instruction-Following-Fine-Tuning-of-Large-Language-Models

## Overview
This repository contains the implementation of fine-tuning large language models (LLMs) to enhance their ability to follow instructions and solve mathematical problems. The project focuses on models such as **Llama-3.2-1B-Instruct** and **Qwen 2.5 1.5B**, fine-tuned on datasets like Alpaca and Camel-AI Math.

## Objectives
The primary goals of this project are:
1. Improve instruction-following capabilities of LLMs.
2. Enhance mathematical reasoning with domain-specific fine-tuning.

## Key Features
- **Instruction Fine-Tuning**: Using datasets like Alpaca for general instructions and Camel-AI Math for math problems.
- **4-bit Quantization**: Efficient model compression for fine-tuning.
- **Parameter-Efficient Fine-Tuning (QLoRA)**: Targeted tuning of model modules to save resources.

## Results
| Task                   | Model Version    | Dataset              | Perplexity |
|------------------------|------------------|----------------------|------------|
| Mathematical Reasoning | Llama-3.2-1B     | Math                 | 1.68       |
| Instruction Following  | Llama-3.2-1B     | Alpaca               | 2.81       |
| Combined Tasks         | Llama-3.2-1B     | Math + Alpaca        | 2.68       |
| Mathematical Reasoning | Qwen 2.5 1.5B    | Math                 | 1.36       |
| Combined Tasks         | Qwen 2.5 1.5B    | Math + Alpaca        | 1.61       |
| Combined Tasks         | Qwen 2.5 1.5B    | Math + Alpaca        | 2.61       |

The **Qwen 2.5 1.5B** model outperformed others, especially in mathematical reasoning tasks with a perplexity score as low as **1.36** on the Math dataset.

## Methodology
1. **Dataset Preparation**:
   - **Alpaca Dataset**: Contains diverse instruction-response pairs for fine-tuning general tasks.
   - **Camel-AI Math Dataset**: Focuses on logical reasoning and structured problem-solving in math.
2. **Data Preprocessing**:
   - Applied cleaning and formatting using `unsloth` framework.
   - Combined topic and sub-topic columns in Camel-AI dataset for improved structure. We had to clean the dataset by using prompting.
3. **Fine-Tuning**:
   - Models were quantized to 4-bit representations to optimize training.
   - Parameter-efficient fine-tuning using QLoRA.

## Usage
### Prerequisites
- Python 3.8+
- Libraries: `transformers`, `datasets`, `bitsandbytes`

## Acknowledgments
This project was developed by Raiyan Ahmed, Mehedi Hasan, and Mahir Shahriar Abir. Special thanks to the creators of Alpaca and Camel-AI datasets for providing valuable resources.

