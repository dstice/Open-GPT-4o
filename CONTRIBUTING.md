# Contributing to Open-GPT-Omni

Welcome! We’re building an open omni-modal AI model from scratch. This document guides you through your first contribution and shows what’s next.

## Immediate Ways to Help (Tiny First Tasks)
All tasks are meant to be completable in an afternoon, even for beginners. Pick one that matches your skill:

### 🧹 Data Ladder
1. **Find and upload a small, open dataset** – find a CC-BY licensed text corpus (e.g., a book, public domain articles) and submit it via our data portal (link TBD). Minimum size: 10MB.
2. **De-duplicate a dataset** – run our provided dedup script on a Hugging Face dataset and report duplicate counts.
3. **Translate 100 sentences** – help us create a multilingual seed dataset by translating English prompts into your native language.

### 💻 Code Ladder
1. **Run the 124M model training** – follow the `README` to train the tiniest model on a single GPU and report your results in the `#phase0-results` channel.
2. **Add a unit test** – see the `tests/` directory and add a test for any untested utility function.
3. **Improve the AutoResearch visualization** – our AutoResearch dashboard is basic; add a new metric graph.

### 📝 Documentation Ladder
1. **Fix a broken link or typo** – small PRs are hugely appreciated.
2. **Translate a doc page** – help non-English speakers by translating one of the `.md` files.
3. **Write a tutorial** – explain how to set up the distributed training node on Windows/Linux/Mac.

## How to Submit
1. Fork the repository.
2. Create a branch (`git checkout -b my-task`).
3. Make your changes, commit, and push.
4. Open a pull request. A maintainer will review.

**First-time contributor?** Label your PR with “good first issue” and we’ll be extra supportive.

## Roadmap of Achievable Milestones
This roadmap is intentionally scoped to what can be done with current volunteer resources.

### 🟢 Phase 0 – Now (next 6 months)
- [x] Reproducible script for 124M text model training.
- [ ] Achieve loss curve parity with GPT-2 small on open dataset.
- [ ] AutoResearch MVP – hyperparameter search that runs on a single node.
- [ ] Data portal prototype for uploading and indexing datasets.
- [ ] 10 active contributors running training experiments.

### 🔵 Phase 1 – 12 months
- [ ] First 1.5B dense model trained collaboratively (≥ 10 volunteer GPUs).
- [ ] Multimodal extension: text + vision, using CLIP encoder.
- [ ] Distributed training testnet with 5+ nodes, training a tiny model end-to-end.
- [ ] Community-curated dataset of 500B tokens, released under open license.

### 🟣 Phase 2 – 18–24 months
- [ ] 8B MoE model trained with distributed volunteer compute (≥ 50 nodes).
- [ ] Speech input/output pipeline integrated (Whisper + custom TTS).
- [ ] Initial public demo (chatbot with vision and voice).
- [ ] Formal governance transition to Steering Council.

We update this document as milestones are met. Join us – every contribution, no matter how small, moves the needle.
