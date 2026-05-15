# Training Strategy

## Core Principle: Synchronous Distributed Pre-training
Open-GPT-Omni’s models will be trained from scratch using a **single coordinated training run** across multiple devices, not by post-hoc merging of separately trained checkpoints. The “merge kit” approach (common for fine-tuned LLaMA variants) is not applicable to pre-training from random initialization. 

We use the following strategies:

## 1. Small-Scale Validation (Phase 0)
- Dense text-only models up to 1.5B parameters.
- Trained on a few hundred billion tokens using 1–8 GPUs (e.g., A6000/A100).
- Purpose: validate architecture, data pipeline, and training hyperparameters discovered by **AutoResearch**.

## 2. Distributed Data Parallelism for Intermediate Models (8B–120B)
For models that exceed single-node memory:

- **Fully Sharded Data Parallelism (FSDP)** or **DeepSpeed ZeRO** to shard model states.
- Training run is orchestrated across many volunteers’ GPUs using a central coordinator.  
  - Each node computes gradients on a micro-batch.
  - Gradients are averaged synchronously (All-Reduce).
  - All nodes see the same sequence of data batches and update parameters identically.

- **Volunteer node protocol:**
  1. Register and download a Docker image / conda environment.
  2. Connect to the training coordinator (IP and token).
  3. Receive data shard and model checkpoint slice.
  4. Run training for N steps, upload gradients, download updated parameters.
  5. System handles node churn with checkpointing and fault tolerance.

## 3. Mixture of Experts with Expert Parallelism (for 200B+ Models)
For ultra-large MoE models, we will combine:
- **Expert Parallelism** – each volunteer node might hold a subset of experts.
- **Data Parallelism** for the shared attention layers.
- This is research territory; we will contribute open-source implementations if successful.

## 4. What We Do NOT Support
- **Federated averaging of separately pre-trained models** – leads to weight mismatch and poor convergence.
- **Merging model weights after independent training** – only applicable to fine-tuned models from the same base, not from scratch.

## 5. Reproducibility and Transparency
Every training run will be logged via W&B (or similar) and reproducible configs published in the repository. Checkpoints will be released at milestones.

## 6. AutoResearch Integration
AutoResearch (automated hyperparameter search) will be used to determine optimal learning rates, batch sizes, and architectural parameters on small-scale runs before scaling. These configurations will be fixed for the large synchronized run; they are not used to independently develop weights per contributor.
