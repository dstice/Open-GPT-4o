# Open-GPT-4o Roadmap and Technical Specification

This document proposes a serious technical roadmap for **Open-GPT-4o**: expanding from personality-focused tuning into a full open, omni-modal GPT-4o-class model family.

## Status

Planning and specification stage.

## Vision

Open-GPT-4o currently emphasizes natural conversation, personality, roleplay, less rigid behavior, and efficiency in smaller models. This roadmap adds a second engineering track focused on building a complete model family:

1. **Open-GPT-4o-Mini-8B-Dense**
2. **Open-GPT-4o-Mini-A8B-MoE**
3. **Open-GPT-4o-120B/A10B-class MoE**
4. **Open-GPT-4o-200B-class MoE**

Final target: a native omni-modal family capable of text, image, audio, voice, video-like frame reasoning, image generation, 3D generation, structured tool calls, and real-time interaction.

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

## Model Ladder

### Stage 1: Open-GPT-4o-Mini-8B-Dense
- 8B–9B dense decoder-only
- 32K → 128K context
- CLIP first vision path, Whisper transcript path, tool/image/3D calling

### Stage 2: Open-GPT-4o-Mini-A8B-MoE
- 40B–80B total, ~8B active
- 64–128 experts, top-k routing, shared expert
- modality-aware routing across text/vision/audio/tools

### Stage 3: Open-GPT-4o-120B/A10B-class MoE
- 100B–130B total, 10B–15B active
- stronger multimodal routing and high-end benchmark target

### Stage 4: Open-GPT-4o-200B-class MoE
- 180B–220B total (~200B)
- flagship teacher model for distillation/pruning to smaller variants

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

This is a community project meant for creation and for the community members and the general public as a whole. This project is hence licensed under Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International. This project is open for non-commercial, personal and research use. All derivatives of this project, its forks, and clones must be open sourced and shared to all under this same license. 

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
