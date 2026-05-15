# Open-GPT-4o Community-Led Development Proposal Roadmap 

This document proposes a serious technical development roadmap for **Open-GPT-4o**: expanding from personality-focused tuning into a community-open, source-available, omni-modal GPT-4o-class model family. This projects builds inspiration from Kye Gomez's attempt at reconstructing an Open-GPT-4.

## Status

Planning and specification stage.

## Vision

Open-GPT-4o development plan emphasises natural conversation, personality, roleplay, less rigid behavior, and efficiency in smaller models. This roadmap adds a second engineering track focused on building a complete model family:

1. **Open-GPT-4o-Mini-8B-Dense**
2. **Open-GPT-4o-Mini-A8B-MoE**
3. **Open-GPT-4o-~120B-~A10B-class MoE**
4. **Open-GPT-4o-~200B--~A20B-class MoE**
5. **Open-GPT-4o-~400B-~A20B-class MoE**

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

## Reference Model Comparison and Public Technical Baseline

## Reference Model Comparison and Public Technical Baseline

This section compares publicly available technical information for GPT-2, GPT-4, GPT-4o, GPT-OSS-20B, and GPT-OSS-120B. The purpose is not to claim that Open-GPT-4o reproduces any proprietary OpenAI model, but to establish a transparent public baseline for architectural planning, scaling assumptions, tokenizer choices, context-length targets, multimodal design, and open-weight development strategy.

Where OpenAI has not officially disclosed model details, the table marks those fields as "not officially disclosed" rather than relying on unsupported parameter-count or architecture rumours.

# Model Technical Specification Comparison

## Core Technical Specification

| Technical Specification | GPT-2 | GPT-4 | GPT-4o | GPT-OSS-20B (OpenAI) | GPT-OSS-120B (OpenAI) |
|---|---|---|---|---|---|
| Model Type | Text-only autoregressive transformer | Transformer-style model; current API listing is text-only | Autoregressive omni model; text, vision, and audio capability depending on API surface | Text-only autoregressive MoE transformer | Text-only autoregressive MoE transformer |
| Core Architecture | Dense decoder-only Transformer | Not officially disclosed beyond Transformer-style architecture | Not officially disclosed beyond autoregressive omni/end-to-end multimodal design | Mixture of Experts (MoE) Transformer | Mixture of Experts (MoE) Transformer |
| Total Parameters | 124M to 1.5B | Not officially disclosed | Not officially disclosed | 20.91B | 116.83B |
| Active Parameters | Dense model; all parameters active | Not officially disclosed | Not officially disclosed | 3.61B per forward pass | 5.13B per forward pass |
| Number of Layers | 12 to 48 | Not officially disclosed | Not officially disclosed | 24 | 36 |
| Attention Heads / GQA | 12 to 25 attention heads | Not officially disclosed | Not officially disclosed | 64 query heads, 8 KV heads/groups (GQA) | 64 query heads, 8 KV heads/groups (GQA) |
| Hidden Size | 768 to 1600 | Not officially disclosed | Not officially disclosed | 2880 | 2880 |
| Vocabulary Size | 50,257 | Not officially disclosed | Not officially disclosed; GPT-OSS extends the o200k tokenizer family used by GPT-4o/o4-mini | 201,088 | 201,088 |
| Context Length | 1,024 tokens | 8,192 tokens in current GPT-4 API listing; larger GPT-4-family variants have existed separately | 128,000 tokens | 131,072 tokens / approximately 128k | 131,072 tokens / approximately 128k |
| Training Data | Approximately 40GB of Internet text from around 8 million web pages | Not officially disclosed in detail | Pre-trained on data up to October 2023 from public, proprietary partnership, and other sources | Text-only dataset with trillions of tokens, focused on STEM, coding, and general knowledge | Text-only dataset with trillions of tokens, focused on STEM, coding, and general knowledge |
| Knowledge Cutoff | No formal cutoff stated; model released in 2019 | December 2023 in current OpenAI API model listing | October 2023 | June 2024 | June 2024 |
| Licensing / Access | MIT licence for released weights on Hugging Face; OpenAI released 1.5B weights/code in 2019 | Proprietary; API access | Proprietary; API access | Apache 2.0 open-weight release | Apache 2.0 open-weight release |

## Multimodal and Special Features

| Feature | GPT-4 / GPT-4V | GPT-4o | GPT-OSS-20B / GPT-OSS-120B |
|---|---|---|---|
| Core Modalities | GPT-4 Technical Report describes image and text input with text output; current GPT-4 API listing is text-only | Text, vision, and audio capability; OpenAI describes GPT-4o as an end-to-end omni model | Text-only; no native vision or audio |
| Image Processing | GPT-4V supports image understanding; current GPT-4 API page lists image input as unsupported for the GPT-4 endpoint | Supports image input; image-token cost depends on model and detail mode rather than a single fixed 1024x1024 rule | Not applicable |
| Audio Processing | Not supported in current GPT-4 API listing | Native audio capability; OpenAI reports response latency as low as 232 ms and average latency around 320 ms | Not applicable |
| Reasoning Control | Not configurable in the cited OpenAI documentation | Not configurable in the cited OpenAI documentation | Configurable reasoning effort: low, medium, and high |
| Agentic Capabilities | Tool use depends on API/platform integration, not the base architecture specification | Supports tool/function calling through OpenAI platform integrations | Supports function calling, web browsing, Python execution, Structured Outputs, and agentic workflows |
| Quantisation and Efficiency | No official GPT-4 quantisation specification disclosed | OpenAI described GPT-4o as faster and cheaper than GPT-4 Turbo at launch | MXFP4 quantisation; GPT-OSS-20B can run within approximately 16GB memory, while GPT-OSS-120B can run on a single 80GB GPU such as an H100-class card |

## Notes on Verification

- GPT-4 parameter counts such as "1.8 trillion parameters" are not officially confirmed by OpenAI, Hugging Face, or arXiv primary sources.
- GPT-4o parameter-count estimates such as "200B to 400B" or "1.8T to 10T" should be treated as speculation unless labelled clearly as unofficial inference.
- GPT-OSS-20B and GPT-OSS-120B have much stronger public technical disclosure than GPT-4 and GPT-4o.
- For GPT-4 and GPT-4o, architecture details such as MoE status, layer count, hidden size, and attention-head configuration remain officially undisclosed.

## References

1. OpenAI. "Better language models and their implications."  
   https://openai.com/index/better-language-models/

2. OpenAI. "GPT-4 Technical Report." arXiv:2303.08774.  
   https://arxiv.org/abs/2303.08774

3. OpenAI. "GPT-4o System Card."  
   https://openai.com/index/gpt-4o-system-card/

4. OpenAI. "GPT-4o API model documentation."  
   https://developers.openai.com/api/docs/models/gpt-4o

5. OpenAI. "GPT-4 API model documentation."  
   https://developers.openai.com/api/docs/models/gpt-4

6. OpenAI. "Images and Vision guide."  
   https://developers.openai.com/api/docs/guides/images-vision

7. OpenAI. "GPT-OSS Model Card."  
   https://openai.com/index/gpt-oss-model-card/

8. OpenAI. "GPT-OSS Model Card PDF."  
   https://cdn.openai.com/pdf/419b6906-9da6-406c-a19d-1bb078ac7637/oai_gpt-oss_model_card.pdf

9. OpenAI. "GPT-OSS-20B on Hugging Face."  
   https://huggingface.co/openai/gpt-oss-20b

10. OpenAI. "GPT-OSS-120B on Hugging Face."  
    https://huggingface.co/openai/gpt-oss-120b

### Design Implications for Open-GPT-4o

The public evidence suggests that the most practical open development path is not to attempt a direct clone of GPT-4o, whose internal architecture and parameter count remain undisclosed, but to build a staged open model family using disclosed and reproducible components.

GPT-OSS-20B and GPT-OSS-120B provide the clearest modern OpenAI reference points for open-weight Mixture-of-Experts design, long-context operation, reasoning-effort control, and efficient deployment. GPT-2 remains useful as a historical dense-transformer baseline for small-scale experiments and scaffold validation. GPT-4 and GPT-4o are best treated as capability targets rather than fully specified architecture templates.

For this project, the comparison supports the following direction:

1. begin with a small dense GPT-style proof of concept;
2. lock tokenizer and special-token decisions before serious pre-training;
3. scale through GPT-2-class and 8B-class checkpoints;
4. add vision, audio, tool-use, and generation bridges incrementally;
5. move toward MoE designs inspired by publicly disclosed GPT-OSS architecture;
6. treat GPT-4o as the omni-modal capability target, not as a directly reproducible public blueprint.

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

### Stage 5: Open-GPT-4o-~400B-~A20B-class MoE
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

## Action Plan: How can I contribute into this project?

1. Start by collecting links to all publicially available GPT-4o generated output data set and sharing the links to these dataset in the following project link: https://github.com/AonzOG/Open-GPT-4o/issues
2. Compile your chats with GPT-4o (recommend annomyse by changing any personal/private real life names/details). 

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
