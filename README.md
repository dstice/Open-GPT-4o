# Open-GPT-4o Roadmap and Technical Specification

This document proposes a serious technical roadmap for **Open-GPT-4o**: expanding from personality-focused tuning into a community-open, source-available, omni-modal GPT-4o-class model family. This projects builds from the Open-GPT-4-inspired scaffold developed by Kyegomez.

## Status

Planning and specification stage.

## Vision

Open-GPT-4o development plan emphasises natural conversation, personality, roleplay, less rigid behavior, and efficiency in smaller models. This roadmap adds a second engineering track focused on building a complete model family:

1. **Open-GPT-4o-Mini-8B-Dense**
2. **Open-GPT-4o-Mini-A8B-MoE**
3. **Open-GPT-4o-~120B-~A10B-class MoE**
4. **Open-GPT-4o-~200B--~A20B-class MoE**

Final target: a native omni-modal family capable of text, image, audio, voice, video-like frame reasoning, image generation, 3D generation, structured tool calls, and real-time interaction.

## Mission

Proof of concept development plan focuses on converting Kye Gomez’s Open-GPT-4 inspired scaffold from a concept scaffold into a reproducible, trainable, GPT-4 inspired models developed along the GPT-2-classification checkpoints, with initial text-generation only capabilities, then vision-language encoding, and audio and image-generation capabilities development along the proposed pipeline.

This proof-of-concept track will validate the scaffold through the following experimental model ladder:

1. **Open-GPT-4-Text-124M Dense**  
2. **Open-GPT-4-Text-350M Dense**  
3. **Open-GPT-4-Text-774M Dense**  
4. **Open-GPT-4-Text-1.5B Dense**  
4. **Open-GPT-4-VL-450M Dense**  
6. **Open-GPT-4-VL-0.8B Dense**  
7. **Open-GPT-4-VL-1.6B Dense**  
8. **Open-GPT-4-Omni-Bridge-0.8B**  
9. **Open-GPT-4-Omni-Bridge-1.6B to 2B Dense**  
10. **Open-GPT-4-Omni-Bridge-2B to 4B Dense/MOE**  
11. **Open-GPT-4-Mini-8B to 9B Dense/MOE**  

Final target: a validated pre-development scaffold capable of real tokenisation, dataset loading, autoregressive next-token prediction, stable loss reduction, checkpoint saving and loading, text generation, evaluation, AutoResearch-controlled experimentation, vision-language training, and staged omni-modal bridge development.

## Goals

Phase 0 is divided into four major development goals. Each goal represents a major proof stage before Open-GPT-4o climbs into larger dense, MoE, or native omni-modal training.

Phase 0A: Open-GPT-4 Text-Generation Proof of Concept   
Phase 0B: AutoResearch-Guided GPT-2-Classification Checkpoint Scaling  
Phase 0C: Vision-Language Encoding Proof of Concept  
Phase 0D: Pre-Omni Capability Bridges  

Final goal: prove the scaffold before scaling it.

## Objectives

### Phase 0A: Open-GPT-4 Text-Generation Proof of Concept  

Convert the GPT4 scaffold into a functional GPT-2-like text-generation model.

Target text-only model ladder:

Open-GPT-4-Text-124M  
Open-GPT-4-Text-350M  
Open-GPT-4-Text-774M  
Open-GPT-4-Text-1.5B  

This stage must validate real tokenisation, real dataset loading, autoregressive next-token prediction, stable loss reduction, checkpoint saving and loading, text generation, and evaluation.

### Phase 0B: AutoResearch-Guided GPT-2-Classification Checkpoint Scaling

Introduce AutoResearch after the 124M text-generation proof model is working.

AutoResearch should optimise depth, width, attention heads, feed-forward ratio, learning rate, warm-up schedule, batch size, sequence length, dataset mixture, optimiser settings, checkpoint frequency, validation metrics, sampling settings, and regression detection.

AutoResearch must operate through controlled experiment templates, reviewable diffs, reproducible configuration files, and human-auditable results. It should not randomly rewrite the model.

### Phase 0C: Vision-Language Encoding Proof of Concept

Train Open-GPT-4o-VL models after text generation has been proven.

Target vision-language model ladder:

Open-GPT-4-VL-450M  
Open-GPT-4-VL-0.8B  
Open-GPT-4-VL-1.6B  

This stage should include image-caption pairs, visual question answering, OCR, document understanding, chart understanding, table understanding, screenshots and GUI tasks, object localisation where possible, multi-image reasoning, and visual instruction following. **LiquidAI's LFM2.5-VL-450M** is the majoor inspiration for the development of the Open-GPT-4 text only model into a vision language mode. Although this project proposes encoding OpenAI's own MIT licensed open source **CLIP** encoded on the **Open-GPT-4 inspired language model backbone**, LFM2.5-VL-450M is a Lanaguage Model based on the  **LFM2.5-350M backbone** with the **SigLIP2 NaFlex shape‑optimized 86M vision encoder**. This real life implementation demonstrates possibilties on the development of a vision language capable Open-GPT-4 inspired model.

### Phase 0D: Pre-Omni Capability Bridges

Begin staged omni-modal bridge development after the text-only and vision-language ladders are proven.

Target omni bridge ladder:

Open-GPT-4-Omni-Bridge-0.8B  
Open-GPT-4-Omni-Bridge-1.6B–2B  
Open-GPT-4-Omni-Bridge-4B  
Open-GPT-4-Mini-8B–9B  

This stage should add ASR, TTS, real-time voice interface, image-generation bridge, 3D-generation bridge, tool-use and function-calling, memory/wiki update tokens, and native multimodal routing preparation.

## Core Architectural Principle

```text
Open-GPT-4o =
    GPT-like / MoE transformer core
  + GPT-4o-style text tokenization
  + image-language encoder
  + audio encoder / ASR path
  + native audio pathway over time
  + real-time voice interface
  + image-generation bridge
  + 3D-generation bridge
  + multimodal adapters
  + pre-training
  + supervised fine-tuning
  + public GPT-4o-style training/output distillation where legally reusable
  + post-training
  + AutoResearch-guided optimization
  + LLM Wiki-based knowledge consolidation
```

## Component Roles

| Component | Role in Open-GPT-4o |
|---|---|
| `Tiktoken` | Text tokenizer and vocabulary |
| CLIP | Vision-language encoding |
| Whisper | ASR and audio encoding foundation |
| Realtime-voice-component | Real-time voice interface |
| Shap-E | 3D generation pathway |
| DALL-E VAE / diffusion / GLIDE / consistency decoder | Image generation and decoding |
| Kyegomez/GPT4 | Initial architecture scaffold |
| Nanochat | Minimal full-stack training inspiration |
| Autoresearch | Automated experimentation and optimization |
| LLM Wiki | Project memory and post-training knowledge consolidation and creation of further dataset for autoresearch post-training/finetuning |

## Key References

- Kye Gomez GPT4: https://github.com/kyegomez/GPT4
- Nanochat: https://github.com/karpathy/nanochat
- Autoresearch: https://github.com/karpathy/autoresearch
- LLM Wiki gist: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
- LLM Wiki implementation: https://github.com/Pratiyush/llm-wiki
- Tiktoken: https://github.com/openai/tiktoken
- CLIP: https://github.com/openai/CLIP
- Whisper: https://github.com/openai/whisper
- Realtime voice component: https://github.com/openai/realtime-voice-component
- Shap-E: https://github.com/openai/shap-e

Reading Materials:
- https://github.com/raiyanyahya/how-to-train-your-gpt
- https://github.com/gpt-omni/mini-omni2
- https://github.com/NROwind/OpenGPT-4o-Image
- https://github.com/OmniMMI/OpenOmniNexus
- https://github.com/kotoba-tech/Open-GPT-4o
- https://github.com/openai/gpt-2
- https://github.com/karpathy/minGPT
- https://github.com/karpathy/nanoGPT
- https://github.com/PromtEngineer/localGPT

## Tokenization Must Be Chosen First

Choose GPT-4o/o200k-style tokenization **before pre-training**, then add multimodal special tokens and resize embeddings/output heads.

Do **not** train on one tokenizer and swap later.

### Proposed Special Tokens

```text
<|image_start|>
<|image_patch|>
<|image_end|>
<|audio_start|>
<|audio_frame|>
<|audio_end|>
<|video_start|>
<|video_frame|>
<|speech_start|>
<|speech_end|>
<|tool_call|>
<|tool_result|>
<|image_gen_start|>
<|image_gen_end|>
<|3d_start|>
<|3d_end|>
<|memory_write|>
<|memory_read|>
<|wiki_update|>
```

## Proof of Concept Development and Experimentation Phase

Phase 1: Proof-of-Concept and Scaffold Validation
1. Stage A: Text-Generation Proof of Concept
2. Stage B: AutoResearch-Guided GPT-2-Class Scaling
3. Stage C: Vision-Language Proof of Concept
4. Stage D: Pre-Omni Capability Bridges

## Proof of Concept Development Principles

```text
Kye Gomez GPT4 scaffold
↓
Make it actually generate text
↓
Scale it through GPT-2-class checkpoints
↓
Add vision-language capability at small scale then scale thrugh checkpoints
↓
Add ASR/TTS/image-generation bridges at small scale vision language models then scale through checkpoints
↓
Then climb toward 4B, 8B–9B, and larger MoE models
```

Read more at: https://github.com/AonzOG/Open-GPT-4o/blob/main/Proof_of_Concept_and_Development_of_Experimental_Models.md

## Model Development Ladder

### Phase 2: 
### Stage 1: Open-GPT-4o-Mini-8B-Dense
- 8B–9B dense decoder-only
- 32K → 128K context
- CLIP first vision path, Whisper transcript path, tool/image/3D calling

### Stage 2: Open-GPT-4o-Mini-A8B-MoE
- 40B–80B total, ~8B active
- 64–128 experts, top-k routing, shared expert
- modality-aware routing across text/vision/audio/tools

### Stage 3: Open-GPT-4o-~120B-~A10B-class MoE
- 100B–130B total, 10B–15B active
- stronger multimodal routing and high-end benchmark target

### Stage 4: Open-GPT-4o-~200B-~A20B-class MoE
- 180B–220B total (~200B)
- flagship teacher model for distillation/pruning to smaller variants

### Stage 4: Open-GPT-4o-~400B-~A20B-class MoE
- 360B-440B total (~400B)
- Next step in development of frontier-level community-open, source-available Open-GPT-4o class model for community personal use and research purposes.

## Training Strategy

### Pre-training
- High-quality text, vision, audio, video-like frame, generation, and tool-trace data
- Multimodal curriculum with careful mixture scheduling

### Post-training
- SFT, multimodal instruction tuning, preference optimization, RLVR
- tool-use and voice interaction tuning
- safety and regression repair
- AutoResearch-driven iteration

## AutoResearch Role

AutoResearch is used before/during pre-training and post-training in a controlled, reviewable loop:
1. Hypothesis selection
2. Config/code changes
3. Controlled run
4. Evaluation (quality + systems metrics)
5. Accept/reject
6. Log to LLM Wiki
7. Promote winning recipes
8. Repeat

## LLM Wiki Role

LLM Wiki serves as durable project memory, including:
- architecture decisions
- experiment logs
- model/data cards
- benchmark outcomes
- regressions/failures
- post-training curricula

## Proposed Repository Structure

```text
Open-GPT-4o/
├── tokenizer/
├── model/
├── data/
├── train/
├── autoresearch/
├── llm_wiki/
├── evals/
├── inference/
└── ui/realtime_voice_component/
```

## Concrete Build Sequence (Condensed)

1. Open full-model discussion issue.
2. Fork/extend GPT-like scaffold (kyegomez/GPT4).
3. Build nanochat-style minimal complete training stack.
4. Lock tokenizer + special tokens.
5. Stabilize decoder-only core + long context.
6. Add CLIP, Whisper, realtime voice, image-generation bridge, and Shap-E bridge.
7. Train 8B dense (text-only then multimodal).
8. Add public GPT-4o-style legal datasets and distillation.
9. Add AutoResearch + LLM Wiki loops.
10. Convert/scale to A8B MoE, then 120B/A10B, then ~200B.
11. Distill/prune to deployable variants.

## Class Inspirations:

The following models form the inspiration for the proposed model developmental ladder arranged according to model weight size from descending to ascending order:

1. **LiquidAI/LFM2.5-350M**: https://huggingface.co/LiquidAI/LFM2.5-350M
2. **LiquidAI/LFM2.5-VL-450M**: https://huggingface.co/LiquidAI/LFM2.5-VL-450M
3. **Qwen/Qwen3.5-0.8B**: https://huggingface.co/Qwen/Qwen3.5-0.8B
4. **openbmb/MiniCPM-V-4.6**: https://huggingface.co/openbmb/MiniCPM-V-4.6
5. **openbmb/MiniCPM-V-4.6-Thinking**: https://huggingface.co/openbmb/MiniCPM-V-4.6-Thinking
6. **LiquidAI/LFM2.5-1.2B-Thinking**: https://huggingface.co/LiquidAI/LFM2.5-1.2B-Thinking
7. **LiquidAI/LFM2.5-1.2B-Instruct**: https://huggingface.co/LiquidAI/LFM2.5-1.2B-Instruct
8. **LiquidAI/LFM2.5-VL-1.6B**: https://huggingface.co/LiquidAI/LFM2.5-VL-1.6B
9. **Qwen/Qwen3.5-2B**: https://huggingface.co/Qwen/Qwen3.5-2B
10. **Qwen/Qwen3.5-4B**: https://huggingface.co/Qwen/Qwen3.5-4B 
11. **LiquidAI/LFM2-VL-3B**: https://huggingface.co/LiquidAI/LFM2-VL-3B
12. **Qwen/Qwen3-Omni-30B-A3B-Thinking**: https://huggingface.co/Qwen/Qwen3-Omni-30B-A3B-Thinking
13. **Qwen/Qwen3-Omni-30B-A3B-Instruct**: https://huggingface.co/Qwen/Qwen3-Omni-30B-A3B-Instruct
14. **Qwen/Qwen3-VL-8B-Thinking**: https://huggingface.co/Qwen/Qwen3-VL-8B-Thinking
15. **Qwen/Qwen3-VL-8B-Instruct**: https://huggingface.co/Qwen/Qwen3-VL-8B-Instruct
16. **Qwen/Qwen3.5-9B**: https://huggingface.co/Qwen/Qwen3.5-9B 
17. **openbmb/MiniCPM-o-4_5 9B**: https://huggingface.co/openbmb/MiniCPM-o-4_5
18. **Qwen/Qwen3.5-122B-A10B**: https://huggingface.co/Qwen/Qwen3.5-122B-A10B
19. **Qwen/Qwen3-VL-235B-A22B-Thinking**: https://huggingface.co/Qwen/Qwen3-VL-235B-A22B-Thinking
20. **Qwen/Qwen3-VL-235B-A22B-Instruct**: https://huggingface.co/Qwen/Qwen3-VL-235B-A22B-Instruct
21. **Qwen/Qwen3.5-397B-A17B** (Actually comparable to or beats OpenAI/GPT-4o in majority of it's textual-language and vision-language benchmarks): https://huggingface.co/Qwen/Qwen3.5-397B-A17B
22. **Qwen/Qwen3.6-27B** (For a relatively small Vision Language Model, is comparable to or beats OpenAI/GPT-4o in majority of it's textual-language and vision-language benchmarks): https://huggingface.co/Qwen/Qwen3.6-27B 

## Open Questions

1. Separate `open-gpt-4o-core` branch?
2. First serious target: 8B dense or A8B MoE?
3. Canonical GPT-4o/o200k tokenization from day one?
4. Standard multimodal special-token format?
5. Best first vision encoder (CLIP/SigLIP/InternViT/etc.)?
6. Best MoE router adaptation strategy for visual/audio tokens?
7. External-tools-first vs native latent branches for image/3D?
8. Which public GPT-4o-style datasets are legally reusable?
9. How should LLM Wiki integrate with AutoResearch?
10. What benchmark thresholds define Open-GPT-4o-Mini and Open-GPT-4o?

## Final Proposal

Keep Open-GPT-4o’s original personality and natural-conversation goals, while adding a serious full-model engineering track that incrementally builds toward a full open omni-modal model family.

## Licence

This is a community project meant for creation and for the community members and the general public as a whole. This project is hence licensed under **Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International**. This project is open for non-commercial, personal and research use. All derivatives of this project, its forks, and clones must remain publicly shared under this same licence. All resulting AI products and technologies resulting from this project via research must be made publically available under this same license.

All other linked repos are governed under their own respective licenses.

License of Linked repos as of 08/05/2026:

MIT License

1. Kye Gomez GPT4: https://github.com/kyegomez/GPT4
2. Nanochat: https://github.com/karpathy/nanochat
3. Autoresearch: https://github.com/karpathy/autoresearch
4. LLM Wiki implementation: https://github.com/Pratiyush/llm-wiki
5. Tiktoken: https://github.com/openai/tiktoken
6. CLIP: https://github.com/openai/CLIP
7. Whisper: https://github.com/openai/whisper
8. Shap-E: https://github.com/openai/shap-e

Apache 2.0 License

9. Realtime voice component: https://github.com/openai/realtime-voice-component
