## Phase 0: Proof-of-Concept and Scaffold Validation

Before commencing the full Development Phase and climbing the main Open-GPT-4o model ladder, the project should first prove that the selected scaffold can be converted into a functioning text-generation and vision-language model.

The purpose of Phase 0 is to turn Kye Gomez's GPT4 scaffold from a conceptual GPT-like / multimodal scaffold into a reproducible, trainable, GPT-2-class language-model pipeline.

This phase exists to prevent premature scaling. Open-GPT-4o should not jump directly to 8B, MoE, or omni-modal training before the scaffold has proven that it can support:

1. real tokenisation;
2. real dataset loading;
3. autoregressive next-token prediction;
4. stable loss reduction;
5. checkpoint saving and loading;
6. text generation;
7. evaluation;
8. AutoResearch-controlled experiment loops;
9. later vision-language extension.

### Phase 0A: Text-Generation Proof of Concept

The first goal is to convert Kye Gomez's Open GPT-4 scaffold into a functional GPT-2-like text-generation model.

Target text-only model ladder:

| Model level | Target parameters | Purpose |
|---|---:|---|
| GPT-2 small level | 124M | Minimum proof that the scaffold can train and generate text |
| GPT-2 medium level | 350M-355M | Small serious language-model validation |
| GPT-2 large level | 774M | Scaling and stability validation |
| GPT-2 XL level | 1.5B-1.558B | Final pre-development text-only proof |

The goal is not to reproduce GPT-2 exactly. The goal is to create Open-GPT-4o text-only checkpoints at GPT-2-class scales so that the project can validate its own architecture, training loop, tokenizer, dataset pipeline, evaluation harness, and AutoResearch integration.

### Phase 0B: AutoResearch-Guided GPT-2-Class Scaling

After the 124M proof model is working, AutoResearch should be introduced as a controlled experiment agent.

AutoResearch should optimise:

- depth;
- width;
- attention heads;
- feed-forward ratio;
- learning rate;
- warm-up schedule;
- batch size;
- sequence length;
- dataset mixture;
- optimiser settings;
- checkpoint frequency;
- validation metrics;
- sampling settings;
- regression detection.

AutoResearch must operate inside a controlled framework with reviewable diffs, fixed experiment templates, and reproducible configuration files. It should not randomly rewrite the model.

### Phase 0C: Vision-Language Proof of Concept

After text generation is proven at 124M, 350M, 774M, and 1.5B-class scales, the next proof is to train Open-GPT-4o-VL models.

Open-GPT-4o-VL means Vision-Language, not full omni-modality.

Target VL ladder:

| Model level | Target scale | Purpose |
|---|---:|---|
| Open-GPT-4o-VL-450M-class | ~450M | Smallest serious vision-language proof |
| Open-GPT-4o-VL-0.8B-class | ~0.8B | Stronger visual reasoning and OCR proof |
| Open-GPT-4o-VL-1.6B-class | ~1.6B | High-end small VLM proof before omni-modal work |

LiquidAI's LFM2.5-VL-450M and LFM2.5-VL-1.6B demonstrate that useful vision-language systems can exist below 2B total parameters. Therefore Open-GPT-4o should not wait until 8B to begin vision-language training.

Initial Open-GPT-4o-VL training should include:

- image-caption pairs;
- visual question answering;
- OCR;
- document understanding;
- chart understanding;
- table understanding;
- screenshots and GUI tasks;
- object localisation where possible;
- multi-image reasoning;
- visual instruction following.

### Phase 0D: Pre-Omni Capability Bridges

After the text-only and vision-language ladders are proven, the project should begin adding omni-modal capability bridges.

Order of addition:

1. ASR path;
2. TTS path;
3. real-time voice interface;
4. image-generation bridge;
5. 3D-generation bridge;
6. tool-use and function-calling;
7. memory/wiki update tokens;
8. native multimodal routing preparation.

This should first be attempted at approximately:

| Stage | Target size |
|---|---:|
| early omni bridge | ~0.8B |
| stronger omni bridge | 1.6B-2B |
| mid-scale omni | 4B |
| GPT-4o-mini-class target | 8B-9B |

The aim is to reach an 8B-9B Open-GPT-4o-Mini-class model only after the scaffold has already proven text generation, vision-language ability, ASR/TTS bridging, image-generation calls, tool calls, and evaluation.
