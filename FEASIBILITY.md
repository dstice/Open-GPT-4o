# Feasibility & Resource Estimation

## 1. Goal and Ambition
Open-GPT-Omni aims to train a family of omni-modal models from scratch, ranging from 8B to 400B parameters. The most direct comparison is DeepSeek-V2 (a 236B MoE model), which reportedly cost ~$5 million to train. Our roadmap acknowledges that a fully multimodal model matching GPT-4o’s capabilities could cost 2–3× more. We need to demonstrate a realistic path to acquiring those resources.

## 2. Community Sweat Equity Model
Instead of relying solely on monetary funding, we propose a **sweat equity** model:

- **50,000 contributors** each contributing approximately **$100 worth** of time, compute, or data curation = **$5 million equivalent value**.
- Contributions can take the form of:
  - Donated GPU hours (compute pledges)
  - High-quality data creation, annotation, and cleaning
  - Code development, testing, and documentation
  - Distributed training participation

We will track contributions using a transparent ledger (e.g., a public registry of GPU-donor-hours, merged pull requests, and curated datasets).

## 3. Compute Strategy

### 3.1 Centralized Cloud Training (Primary for Proof-of-Concept)
For initial Phase 0 models (≤ 1.5B parameters), we'll use small cloud grants, academic resources, and volunteer machines. These are cheap and serve to validate the pipeline.

### 3.2 Distributed Volunteer Compute (Goal for Large-Scale)
For 8B+ models, we will investigate and adopt **fault-tolerant distributed training** frameworks that can utilize donated consumer GPUs:
- [Petals](https://github.com/bigscience-workshop/petals) – for decentralized inference/training.
- [Hivemind](https://github.com/learning-at-home/hivemind) – decentralized deep learning in a peer-to-peer network.
- A custom orchestration layer if needed, using synchronous data parallelism across nodes.

**We do not expect to merge independently trained checkpoints.** Pre-training will be a coordinated, synchronous run where many participants contribute compute to the same run, sending gradients to a shared parameter server. This is technically challenging and will be a core research contribution of the project.

### 3.3 Fallback Plan
If distributed volunteer training proves infeasible for models > 8B, the project will pivot to an open coalition seeking compute grants from cloud providers, research institutions, and philanthropic organizations, leveraging the community's demonstrated momentum.

## 4. Data Plan – Realistic and Tiered

The ambition of a 15-trillion-token dataset is long-term. Initial releases will be smaller, high-quality corpora built on top of existing open datasets.

### Phase 0–1 (Year 1): 300B–1T Tokens
- Use existing, well-curated open-source datasets: SlimPajama, The Pile, C4, RedPajama, Dolma.
- Community enhances these with specialist domains (e.g., code, STEM, multilingual) through a centralised data portal.

### Phase 2 (Year 2–3): Scaling to 2T–5T Tokens
- Build a custom data pipeline allowing contributors to submit, de-duplicate, and annotate text, image, and audio data.
- Hosting will use Hugging Face Datasets and possibly a dedicated data warehouse, **not** Fandom.com or Wikipedia (which have restrictive policies and unsuitable infrastructure). We may create a dedicated wiki-like interface for visualizing and curating subsets, but the underlying storage will be scalable and open.

### Phase 3 (Beyond): Targeting 15T Tokens
- Requires industrial-scale filtering and ingestion from CommonCrawl dumps. We’ll develop automated quality classifiers and involve the community in rating samples. The exact feasibility will be re-evaluated based on progress.

**All datasets will be released under open licenses (CC-BY, ODC-By) to ensure the model can be freely used.**

## 5. Risk and Mitigation

| Risk | Mitigation |
|------|------------|
| Insufficient volunteer compute | Focus first on smaller models; build a strong demo to attract grants; benchmark distributed efficiency early. |
| Data quality/usability | Start with proven open datasets; rigorous de-duplication and filtering scripts; community QA process. |
| Coordination overhead | Formal governance, clear working groups, automated testing and CI/CD. |
