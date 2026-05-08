# Open-GPT-4o

## Suggested Roadmap for Open-GPT-4o

Open-GPT-4o is a proposed full open GPT-4o-class omni-modal model family. The aim is to move beyond personality-only fine-tuning and into a serious engineering roadmap for a full working model family: from an 8B dense model or A8B MoE model to a ~200B MoE model targeting GPT-4o-level benchmark equivalence.

This is not intended to be a toy model, a demo model, or a research-only model. The goal is a full working Open-GPT-4o-style omni-modal architecture.

Open-GPT-4o should preserve the natural conversational feel, personality, roleplay capability, and less rigid interaction style that inspired the broader 4o-style movement, while adding a serious full-model engineering track.

## Project Links

* Open-GPT-4o repository: [https://github.com/AonzOG/Open-GPT-4o](https://github.com/AonzOG/Open-GPT-4o)

## Core Objective

The proposed project is to create an Open-GPT-4o model family:

1. **Open-GPT-4o-Mini-8B-Dense**
2. **Open-GPT-4o-Mini-A8B-MoE**
3. **Open-GPT-4o-120B/A10B-class MoE**
4. **Open-GPT-4o-200B-class MoE**

The desired final target is a native omni-modal model family that can process and generate across:

* text
* image
* audio
* voice
* video-like frame sequences
* image generation
* 3D generation
* structured tool calls
* real-time conversational interaction

The goal is not simply to bolt tools onto a chatbot. The goal is to build towards a native omni-modal architecture where the central model learns shared representations across modalities.

## Architectural Principle

The proposed mental model is:

```text
Open-GPT-4o =
    GPT-like / MoE transformer core
  + GPT-4o-style text tokenisation
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
  + AutoResearch-guided optimisation
  + LLM Wiki-based knowledge consolidation
```

Different resources in this proposal have different roles. They should not all be treated as tokenisers.

| Component                                            | Role in Open-GPT-4o                                                         |
| ---------------------------------------------------- | --------------------------------------------------------------------------- |
| `tiktoken`                                           | Text tokeniser / vocabulary selection                                       |
| CLIP                                                 | Vision-language encoder                                                     |
| Whisper                                              | ASR and audio-encoding foundation                                           |
| realtime-voice-component                             | Real-time microphone/speaker/session interface                              |
| Shap-E                                               | 3D generation pathway                                                       |
| DALL-E VAE / diffusion / GLIDE / consistency decoder | Image-generation and image-decoding pathways                                |
| kyegomez/GPT4                                        | Initial GPT-like architecture scaffold                                      |
| nanochat                                             | Minimal full-stack training pipeline inspiration                            |
| autoresearch                                         | Automated experiment and optimisation layer                                 |
| LLM Wiki                                             | Post-training knowledge consolidation and evolving model-development memory |

## Foundation Repositories and Links

### Open-GPT-4o Repository and Discussion

* Open-GPT-4o repository: Open-GPT-4o repository: [https://github.com/AonzOG/Open-GPT-4o](https://github.com/AonzOG/Open-GPT-4o)

### GPT-like Scaffold and Training Inspiration

* Kye Gomez Open GPT-4-like architecture scaffold: [https://github.com/kyegomez/GPT4](https://github.com/kyegomez/GPT4)
* Karpathy Nanochat: [https://github.com/karpathy/nanochat](https://github.com/karpathy/nanochat)
* Karpathy Autoresearch: [https://github.com/karpathy/autoresearch](https://github.com/karpathy/autoresearch)
* Karpathy LLM Wiki gist: [https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)
* LLM Wiki implementation: [https://github.com/Pratiyush/llm-wiki](https://github.com/Pratiyush/llm-wiki)

### Text Tokenisation

* OpenAI tiktoken: [https://github.com/openai/tiktoken](https://github.com/openai/tiktoken)

### Image-Language Encoding

* OpenAI CLIP: [https://github.com/openai/CLIP](https://github.com/openai/CLIP)
* CLIP ViT-B/32 on Hugging Face: [https://huggingface.co/openai/clip-vit-base-patch32](https://huggingface.co/openai/clip-vit-base-patch32)

### Audio Encoding and ASR

* OpenAI Whisper: [https://github.com/openai/whisper](https://github.com/openai/whisper)
* Whisper release collection: [https://huggingface.co/collections/openai/whisper-release](https://huggingface.co/collections/openai/whisper-release)

### Real-Time Voice Interface

* OpenAI realtime voice component: [https://github.com/openai/realtime-voice-component](https://github.com/openai/realtime-voice-component)

### 3D Generation

* OpenAI Shap-E: [https://github.com/openai/shap-e](https://github.com/openai/shap-e)
* Shap-E img2img on Hugging Face: [https://huggingface.co/openai/shap-e-img2img](https://huggingface.co/openai/shap-e-img2img)

### Image-Generation / Image-Decoding Pathways

* OpenAI consistency decoder: [https://huggingface.co/openai/consistency-decoder](https://huggingface.co/openai/consistency-decoder)
* OpenAI DALL-E VAE: [https://github.com/openai/DALL-E](https://github.com/openai/DALL-E)
* OpenAI improved diffusion: [https://github.com/openai/improved-diffusion](https://github.com/openai/improved-diffusion)
* OpenAI guided diffusion: [https://github.com/openai/guided-diffusion](https://github.com/openai/guided-diffusion)
* OpenAI GLIDE text-to-image: [https://github.com/openai/glide-text2im](https://github.com/openai/glide-text2im)

### GPT-OSS Vision-Language Inspiration

* GPT-OSS-20B-Vision discussion: [https://discuss.huggingface.co/t/gpt-oss-20b-vision-adding-multimodal-to-gpt-oss-with-a-novel-multi-scale-approach-trained-on-a-single-dgx-spark/173659](https://discuss.huggingface.co/t/gpt-oss-20b-vision-adding-multimodal-to-gpt-oss-with-a-novel-multi-scale-approach-trained-on-a-single-dgx-spark/173659)
* InternVL3.5 GPT-OSS-20B-A4B preview: [https://huggingface.co/OpenGVLab/InternVL3_5-GPT-OSS-20B-A4B-Preview](https://huggingface.co/OpenGVLab/InternVL3_5-GPT-OSS-20B-A4B-Preview)
* GPT-OSS-20B vision preview: [https://huggingface.co/vincentkaufmann/gpt-oss-20b-vision-preview](https://huggingface.co/vincentkaufmann/gpt-oss-20b-vision-preview)

### GPT-OSS Pruning Inspiration

* GPT-OSS 9B specialised science pruned MoE: [https://huggingface.co/AmanPriyanshu/gpt-oss-9.0b-specialized-science-pruned-moe-only-12-experts](https://huggingface.co/AmanPriyanshu/gpt-oss-9.0b-specialized-science-pruned-moe-only-12-experts)
* GPT-OSS General 4.2B to 20B collection: [https://huggingface.co/collections/AmanPriyanshu/gpt-oss-general-42b-to-20b](https://huggingface.co/collections/AmanPriyanshu/gpt-oss-general-42b-to-20b)

### Parameter-Size Reference

* Paper referencing GPT-4o-mini as approximately 8B and GPT-4o as approximately 200B: [https://arxiv.org/pdf/2412.19260](https://arxiv.org/pdf/2412.19260)

Important caveat: this paper itself notes that exact parameter counts for several closed models are not publicly disclosed, and that its parameter-size estimates are mined from public articles only. Therefore, 8B and 200B should be treated as planning targets, not confirmed OpenAI disclosures.

### Qwen Scale and Benchmark Inspiration

Models listed as matching or beating GPT-4o-level benchmark surfaces:

* Qwen3.5-397B-A17B: [https://huggingface.co/Qwen/Qwen3.5-397B-A17B](https://huggingface.co/Qwen/Qwen3.5-397B-A17B)
* Qwen3.5-122B-A10B: [https://huggingface.co/Qwen/Qwen3.5-122B-A10B](https://huggingface.co/Qwen/Qwen3.5-122B-A10B)
* Qwen3.6-27B: [https://huggingface.co/Qwen/Qwen3.6-27B](https://huggingface.co/Qwen/Qwen3.6-27B)

Models listed as matching or beating GPT-4o-mini-level benchmark surfaces:

* Qwen3.5-122B-A10B: [https://huggingface.co/Qwen/Qwen3.5-122B-A10B](https://huggingface.co/Qwen/Qwen3.5-122B-A10B)
* Qwen3.5-9B: [https://huggingface.co/Qwen/Qwen3.5-9B](https://huggingface.co/Qwen/Qwen3.5-9B)

## Tokenisation Decision: GPT-4o `tiktoken` Must Be Chosen Before Training

GPT-4o `tiktoken` / o200k-style tokenisation should be selected before pre-training and before AutoResearch begins changing training code.

The order should be:

```text
1. Choose GPT-4o/o200k-style text tokenisation.
2. Add Open-GPT-4o multimodal special tokens.
3. Resize the embedding matrix and output head.
4. Build the full data pipeline around this vocabulary.
5. Begin pre-training.
6. Use AutoResearch to optimise training only after the tokenisation and vocabulary are fixed.
```

Do not train with one tokeniser and then swap in GPT-4o `tiktoken` later. That would break learned token embeddings, because the model learns meanings attached to token IDs.

Proposed multimodal special tokens:

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

## Proposed Architecture

```text
Open-GPT-4o Core
├── Text stream
│   ├── GPT-4o/o200k-style tiktoken tokeniser
│   ├── Open-GPT-4o multimodal special tokens
│   └── long-context text sequence handling
│
├── Vision input
│   ├── CLIP / ViT image encoder
│   ├── multi-scale visual feature extraction
│   ├── visual projector / Q-Former / Perceiver resampler
│   ├── vision tokens mapped into LLM hidden states
│   └── modality-aware MoE routing
│
├── Audio input
│   ├── Whisper ASR path
│   ├── transcript-to-text-token path
│   ├── Whisper-derived audio embedding path
│   ├── native audio frame tokens over time
│   └── modality-aware MoE routing
│
├── Real-time voice layer
│   ├── realtime voice component
│   ├── browser microphone input
│   ├── streaming audio transport
│   ├── voice activity detection
│   ├── interruption handling
│   ├── low-latency response streaming
│   └── speech playback / TTS / future neural audio decoder
│
├── Image generation path
│   ├── image-generation planning tokens
│   ├── DALL-E VAE concepts
│   ├── improved diffusion / guided diffusion
│   ├── GLIDE text-to-image
│   ├── consistency decoder
│   └── later native image-latent generation
│
├── 3D generation path
│   ├── Shap-E text-to-3D
│   ├── Shap-E image-to-3D
│   ├── 3D latent bridge
│   └── later native 3D-token generation
│
├── Transformer core
│   ├── decoder-only transformer
│   ├── long-context positional system
│   ├── grouped-query / multi-query attention
│   ├── MoE feed-forward layers
│   ├── shared expert
│   ├── routed experts
│   ├── router load-balancing loss
│   └── modality-aware expert adaptation
│
├── Training and optimisation
│   ├── pre-training
│   ├── multimodal pre-training
│   ├── supervised fine-tuning
│   ├── public GPT-4o-style training datasets where legally reusable
│   ├── public GPT-4o output/distillation datasets where legally reusable
│   ├── preference optimisation
│   ├── RLVR / verifiable reward training
│   ├── tool-use training
│   ├── voice interaction training
│   └── AutoResearch-guided experiment loops
│
└── Knowledge consolidation
    ├── LLM Wiki from development sessions
    ├── architecture decision records
    ├── training recipes
    ├── failed experiment memory
    ├── benchmark regression memory
    └── post-training curriculum updates
```

## Role of Kye Gomez's GPT4 Repository

The Kye Gomez GPT4 repository should be treated as the first scaffold, not as the final model.

Use it to begin:

* model class organisation
* GPT-like transformer structure
* multimodal interface concepts
* example language and multimodal flows

But for a full Open-GPT-4o model, the project would need to rewrite and extend it substantially:

```text
Fork kyegomez/GPT4
↓
Replace random-token examples with real tiktoken data loading
↓
Replace simple architecture with a stable decoder-only transformer
↓
Add long-context support
↓
Add MoE FFN layers
↓
Add shared expert + routed experts
↓
Add CLIP visual pathway
↓
Add Whisper/audio pathway
↓
Add image-generation bridge
↓
Add Shap-E 3D bridge
↓
Add distributed training
↓
Add eval harness
↓
Add inference server
```

By the time this becomes a true Open-GPT-4o model, it will be descended from the scaffold but no longer merely the original scaffold.

## Role of Nanochat

nanochat should inspire the minimal full-stack training pipeline.

The goal is not to remain nano-sized forever. The goal is to use the nanochat philosophy:

```text
small, readable, complete, hackable training stack
```

Then scale it into:

```text
Open-GPT-4o training stack
├── tokenisation
├── dataset preparation
├── pre-training
├── supervised fine-tuning
├── evaluation
├── inference
├── chat UI
├── multimodal extensions
├── MoE training
├── distributed training
└── AutoResearch-controlled experiment loop
```

A useful early milestone would be a nanochat-sized implementation of Kye Gomez's Open GPT-4-like architecture, with GPT-4o-style `tiktoken` and a small multimodal adapter. That would be the minimum reproducible version of the pipeline before scaling.

However, the final goal remains full-scale Open-GPT-4o, not a nanochat toy.

## Role of AutoResearch in Pre-Training

AutoResearch should be used before and during pre-training as the automated research agent for training-recipe discovery.

Pre-training AutoResearch should optimise:

* model depth
* hidden width
* attention design
* GQA / MQA choice
* RoPE scaling / long-context settings
* optimiser choice
* learning-rate schedule
* warm-up and decay
* batch size
* sequence length schedule
* data-mixture weights
* text/code/math ratio
* curriculum ordering
* MoE expert count
* top-k expert routing
* shared expert design
* router load-balancing loss
* modality routing rules
* checkpointing interval
* validation metrics
* catastrophic-regression detection

Pre-training AutoResearch loop:

```text
1. Select experiment hypothesis.
2. Modify config or training code.
3. Launch small controlled training run.
4. Evaluate validation loss, benchmark proxy scores, throughput, memory, and stability.
5. Accept or reject the experiment.
6. Log outcome into LLM Wiki.
7. Promote accepted recipes to larger runs.
8. Repeat.
```

Important: AutoResearch should not be allowed to randomly rewrite the entire model unsupervised. It should work inside a controlled experiment framework with reviewable diffs and reproducible configs.

## Role of AutoResearch in Post-Training

AutoResearch should also be used after base pre-training.

Post-training AutoResearch should optimise:

* supervised fine-tuning recipes
* public GPT-4o-style training dataset mixture
* public GPT-4o output/distillation dataset mixture
* refusal and safety data mixture
* tool-use formatting
* function-calling grammar
* image-language instruction mixture
* audio/voice instruction mixture
* speech interruption behaviour
* multi-turn conversation quality
* roleplay/personality tuning without destroying capability
* RLVR / verifiable reward tasks
* preference optimisation settings
* benchmark-targeted curricula
* hallucination reduction
* latency and streaming behaviour
* evaluation-driven regression correction

Post-training AutoResearch loop:

```text
1. Choose a post-training objective.
2. Generate or select candidate SFT/preference/RLVR mixture.
3. Fine-tune a checkpoint branch.
4. Run benchmark and behaviour evals.
5. Compare against previous accepted checkpoint.
6. Reject regressions.
7. Keep improvements.
8. Log all results into LLM Wiki.
9. Use LLM Wiki to generate the next training curriculum.
```

This makes AutoResearch useful both before and after the base model exists.

## Public GPT-4o-Style Training and Output Datasets

The model should be fine-tuned on publicly available GPT-4o-style training datasets and publicly available GPT-4o output/distillation datasets.

The intended dataset categories are:

1. Public GPT-4o-labelled datasets

2. Public GPT-4o-generated output datasets

3. Public GPT-4o-style synthetic instruction datasets

4. Public GPT-4o-style multimodal datasets

5. Public GPT-4o-style image-caption / image-generation datasets

6. Public GPT-4o-output comparison datasets

7. Public benchmark datasets where GPT-4o outputs are available

8. Community-contributed Open-GPT-4o conversation and preference data

Dataset governance should include:

```text
source tracking
model-of-origin tracking
dataset card
provenance notes
allowed-use notes
contamination checks
benchmark decontamination
privacy filtering
copyright filtering
quality scoring
```

The project should maintain a dataset registry for Open-GPT-4o:

```text
datasets/
├── registry.yaml
├── licences/
├── provenance/
├── text_instruction/
├── gpt4o_style_outputs/
├── multimodal_instruction/
├── image_generation/
├── speech_audio/
├── tool_traces/
├── preference_data/
└── rejected_or_unclear_licence/
```

## Role of LLM Wiki in Post-Training and Project Memory

Karpathy's LLM Wiki idea and the `Pratiyush/llm-wiki` implementation should be used as a post-training and project-memory system.

Links:

* Karpathy LLM Wiki gist: [https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)
* LLM Wiki implementation: [https://github.com/Pratiyush/llm-wiki](https://github.com/Pratiyush/llm-wiki)

The purpose is not just documentation. It should become the model-development memory layer.

LLM Wiki should store:

* architecture decisions
* rejected architecture decisions
* training configurations
* AutoResearch experiment logs
* model cards
* data cards
* evaluation results
* benchmark failures
* hallucination examples
* voice interaction failures
* multimodal routing failures
* safety failures
* known regressions
* successful training recipes
* post-training curricula
* contributor discussions
* issue summaries
* pull request summaries

The LLM Wiki can then be used to create future training and post-training datasets:

```text
project discussions
↓
LLM Wiki extraction
↓
structured knowledge base
↓
training examples
↓
SFT / preference / tool-use / reasoning curricula
↓
next model checkpoint
```

This gives the project durable memory and prevents the team from repeating failed experiments.

## Image-Language Encoding with CLIP

CLIP should be used as the first image-language encoder.

Links:

* [https://github.com/openai/CLIP](https://github.com/openai/CLIP)
* [https://huggingface.co/openai/clip-vit-base-patch32](https://huggingface.co/openai/clip-vit-base-patch32)

Initial vision path:

```text
image
↓
CLIP ViT-B/32 image encoder
↓
image features
↓
vision projector / Q-Former / Perceiver resampler
↓
LLM hidden-space pseudo-tokens
↓
Open-GPT-4o transformer core
```

The model should train on:

* image-caption pairs
* visual question answering
* OCR
* chart understanding
* table understanding
* document understanding
* screenshots
* GUI tasks
* diagrams
* multi-image reasoning
* spatial reasoning
* medical/scientific images where licences allow

Important MoE lesson from GPT-OSS-20B-Vision:

Projector-only training can fail for MoE models because expert routing has not learned visual tokens. Therefore Open-GPT-4o MoE training must adapt:

```text
vision projector
+ router
+ selected experts
+ visual instruction data
+ multimodal post-training
```

Do not train only the visual projector and expect a MoE router to handle visual tokens correctly.

## Audio Encoding with Whisper

Whisper should be used in two phases.

Links:

* [https://github.com/openai/whisper](https://github.com/openai/whisper)
* [https://huggingface.co/collections/openai/whisper-release](https://huggingface.co/collections/openai/whisper-release)

Phase 1: ASR/transcript path.

```text
microphone/audio file
↓
Whisper ASR
↓
transcribed text
↓
GPT-4o-style tiktoken
↓
Open-GPT-4o transformer
```

Phase 2: native audio embedding path.

```text
audio waveform / log-mel frames
↓
Whisper-derived audio encoder
↓
audio frame embeddings
↓
audio projector / resampler
↓
LLM hidden-space audio tokens
↓
Open-GPT-4o transformer
```

Phase 3: speech output path.

```text
Open-GPT-4o hidden states / speech-planning tokens
↓
speech decoder
↓
vocoder
↓
streaming voice output
```

Whisper gives strong ASR. GPT-4o-like voice requires more than ASR: it needs streaming audio, interruption handling, prosody, turn-taking, latency optimisation, and eventually native audio reasoning.

## Real-Time Voice Component

The realtime voice component should be used as the live voice interface layer.

Link:

* [https://github.com/openai/realtime-voice-component](https://github.com/openai/realtime-voice-component)

It should provide:

* microphone capture
* browser voice controls
* voice activity detection
* session lifecycle
* interruption handling
* transcript assembly
* streaming responses
* playback of generated speech
* tool-constrained UI interaction

Its role is:

```text
human voice
↓
realtime voice component
↓
Whisper or native audio encoder
↓
Open-GPT-4o model
↓
text/audio response
↓
realtime voice component
↓
human hears response
```

This component is not the model brain. It is the mouth, ears, and reflex layer of the live system.

## Image Generation Pathway

Image generation should first be treated as an output subsystem, then later as a native latent-output branch.

Links:

* [https://huggingface.co/openai/consistency-decoder](https://huggingface.co/openai/consistency-decoder)
* [https://github.com/openai/DALL-E](https://github.com/openai/DALL-E)
* [https://github.com/openai/improved-diffusion](https://github.com/openai/improved-diffusion)
* [https://github.com/openai/guided-diffusion](https://github.com/openai/guided-diffusion)
* [https://github.com/openai/glide-text2im](https://github.com/openai/glide-text2im)

Initial image-generation path:

```text
user request
↓
Open-GPT-4o writes structured image-generation prompt
↓
GLIDE / diffusion / DALL-E VAE / consistency decoder path
↓
image output
↓
CLIP / vision encoder checks result
↓
Open-GPT-4o revises if needed
```

Later native path:

```text
Open-GPT-4o emits image-planning tokens or image-latent tokens
↓
image latent bridge
↓
diffusion / decoder model
↓
image output
```

The DALL-E repository should be understood as the VAE component, not the full unreleased DALL-E transformer. The diffusion repos and GLIDE provide more of the image synthesis path.

## 3D Generation Pathway with Shap-E

Shap-E should first be used as a 3D generation tool, then later as a latent pathway.

Links:

* [https://github.com/openai/shap-e](https://github.com/openai/shap-e)
* [https://huggingface.co/openai/shap-e-img2img](https://huggingface.co/openai/shap-e-img2img)

Initial 3D path:

```text
user asks for 3D object
↓
Open-GPT-4o writes structured Shap-E prompt
↓
Shap-E text-to-3D or image-to-3D
↓
3D asset output
↓
Open-GPT-4o describes, evaluates, and revises
```

Later native 3D path:

```text
Open-GPT-4o emits 3D-planning tokens or 3D latent instructions
↓
Shap-E latent bridge
↓
3D asset generation
```

## GPT-OSS and InternVL Inspiration

The GPT-OSS and InternVL examples are important because they show how existing text/MoE models can be converted into multimodal systems.

Links:

* [https://discuss.huggingface.co/t/gpt-oss-20b-vision-adding-multimodal-to-gpt-oss-with-a-novel-multi-scale-approach-trained-on-a-single-dgx-spark/173659](https://discuss.huggingface.co/t/gpt-oss-20b-vision-adding-multimodal-to-gpt-oss-with-a-novel-multi-scale-approach-trained-on-a-single-dgx-spark/173659)
* [https://huggingface.co/OpenGVLab/InternVL3_5-GPT-OSS-20B-A4B-Preview](https://huggingface.co/OpenGVLab/InternVL3_5-GPT-OSS-20B-A4B-Preview)
* [https://huggingface.co/vincentkaufmann/gpt-oss-20b-vision-preview](https://huggingface.co/vincentkaufmann/gpt-oss-20b-vision-preview)

Important lessons to absorb:

1. Projector-only training may be insufficient for MoE.
2. Visual tokens must influence router adaptation.
3. Multi-scale visual features can improve visual representation.
4. OCR, charts, documents, and spatial reasoning require more than simple caption data.
5. Multimodal post-training is essential.
6. Inference deployment matters: vLLM, SGLang, llama.cpp-style paths, and OpenAI-compatible APIs should be considered early.

## GPT-OSS Pruning Inspiration

Pruning should be treated as part of the model-family strategy.

Links:

* [https://huggingface.co/AmanPriyanshu/gpt-oss-9.0b-specialized-science-pruned-moe-only-12-experts](https://huggingface.co/AmanPriyanshu/gpt-oss-9.0b-specialized-science-pruned-moe-only-12-experts)
* [https://huggingface.co/collections/AmanPriyanshu/gpt-oss-general-42b-to-20b](https://huggingface.co/collections/AmanPriyanshu/gpt-oss-general-42b-to-20b)

Possible Open-GPT-4o pruning strategy:

```text
200B MoE teacher
↓
120B/A10B MoE student
↓
A8B MoE mini
↓
8B dense distilled model
↓
smaller specialised domain models
```

This means the project should not only train upward. It should also distil and prune downward for edge devices such as laptops and phones.

## Model-Size Ladder

### Stage 1: Open-GPT-4o-Mini-8B-Dense

Target:

```text
Architecture: dense decoder-only transformer
Parameters: 8B-9B
Context: 32K first, then 128K
Tokenizer: GPT-4o/o200k-style tiktoken + multimodal special tokens
Vision: CLIP ViT-B/32 first, stronger encoder later
Audio: Whisper transcript path first
Outputs: text, tool calls, image-generation calls, 3D-generation calls
```

Training sequence:

```text
1. Text pre-training
2. Code/math/science-heavy continued pre-training
3. Instruction tuning
4. CLIP vision adapter training
5. OCR/chart/document VQA training
6. Whisper ASR-to-text integration
7. Tool-call training
8. Image-generation prompt/tool training
9. Shap-E prompt/tool training
10. Public GPT-4o-style fine-tuning where legally reusable
11. Public GPT-4o-output distillation where legally reusable
12. Post-training with AutoResearch
13. LLM Wiki consolidation
```

This is the first full working model.

### Stage 2: Open-GPT-4o-Mini-A8B-MoE

Target:

```text
Total parameters: 40B-80B
Active parameters: about 8B
Experts: 64-128
Activated experts: top-4 to top-8
Shared expert: yes
Context: 128K
```

Training sequence:

```text
1. Convert dense FFN layers into MoE FFN layers.
2. Add shared expert.
3. Add router load-balancing loss.
4. Train router on text tokens.
5. Train router on image tokens.
6. Train router on audio tokens.
7. Train router on tool tokens.
8. Continue multimodal pre-training.
9. Add public GPT-4o-style output distillation.
10. Run post-training AutoResearch.
11. Distil back down to dense 8B if useful.
```

### Stage 3: Open-GPT-4o-120B/A10B-class MoE

Target:

```text
Total parameters: 100B-130B
Active parameters: 10B-15B
Experts: around 256
Activated experts: 8 routed + 1 shared
Context: 128K-256K
Vision encoder: 0.3B-5B depending on compute
Audio encoder: Whisper-derived + native audio embeddings
```

Purpose:

* establish the first serious high-end Open-GPT-4o benchmark surface
* train strong multimodal routing
* build the teacher for smaller models
* serve as the stepping stone to ~200B MoE

### Stage 4: Open-GPT-4o-200B-class MoE

Target:

```text
Total parameters: 180B-220B (~200B)
Active parameters: 16B-24B
Layers: 56-72
Experts: 256-384
Activated experts: 8-12 routed + 1 shared
Context: 256K native target
Vision encoder: 1B-5B
Audio: native audio + ASR path
Image generation: diffusion/latent decoder bridge
3D generation: Shap-E bridge
```

Purpose:

* target GPT-4o-level benchmark equivalence
* act as the main teacher model
* distil into A8B MoE and 8B dense variants
* become the flagship Open-GPT-4o model

## Pre-Training Curriculum

The base model should be pre-trained on a high-quality multimodal mixture.

Text:

* filtered web
* books
* code
* mathematics
* science
* medicine
* law
* technical manuals
* multilingual text
* long-context documents
* dialogue data

Vision:

* image-caption pairs
* VQA
* OCR documents
* chart QA
* table QA
* diagrams
* screenshots
* GUI tasks
* multi-image reasoning
* spatial reasoning

Audio:

* speech-transcript pairs
* multilingual speech
* noisy speech
* accented speech
* speech translation
* conversational audio
* voice activity labels

Video-like data:

* sampled frames
* subtitles
* action descriptions
* screen recordings
* temporal reasoning tasks

Generation:

* text-to-image prompts
* image editing prompts
* image-generation preference data
* 3D prompt-to-object data
* Shap-E-style image-to-3D examples

Tool traces:

* function calls
* browser/search traces
* code execution traces
* file-analysis traces
* structured output traces

## Fine-Tuning and Post-Training Curriculum

After base pre-training, the model should go through:

```text
1. Supervised fine-tuning
2. Multimodal instruction tuning
3. Public GPT-4o-style training dataset fine-tuning where legally reusable
4. Public GPT-4o output/distillation dataset fine-tuning where legally reusable
5. Preference optimisation
6. RLVR / verifiable-reward training
7. Tool-use training
8. Voice interaction tuning
9. Image-generation bridge tuning
10. Shap-E/3D-generation bridge tuning
11. Personality/conversation tuning for Open-GPT-4o style
12. Safety/alignment tuning
13. Regression repair
14. LLM Wiki-generated post-training curricula
15. AutoResearch post-training optimisation
```

The aim is not only benchmark performance. The aim is also:

* low-latency conversation
* natural tone
* emotional continuity
* reliable roleplay where allowed
* strong instruction following
* factuality
* tool reliability
* multimodal reasoning
* fewer hallucinations
* recoverable mistakes
* coherent personality without capability collapse

## Benchmark Target Suite

The project should not call a model Open-GPT-4o merely because it feels conversational. It should track benchmarks.

Text and reasoning:

```text
MMLU-Pro
MMLU-Redux
GPQA Diamond
AIME
MATH
HumanEval
MBPP
SWE-bench Verified
IFEval
BFCL
TAU-Bench
```

Vision-language:

```text
MMMU
MMMU-Pro
MathVista
MathVision
OCRBench
ChartQA
DocVQA
TextVQA
RealWorldQA
MMBench
MMStar
HallusionBench
```

Audio:

```text
WER by language/accent
speech translation
spoken QA
voice activity detection
interruption handling
streaming latency
turn-taking quality
```

Video and agentic tasks:

```text
VideoMME
GUI tasks
web navigation
tool-use tasks
file-analysis tasks
structured-output tasks
```

Generation:

```text
text-to-image prompt faithfulness
image editing quality
image self-critique
3D prompt-to-asset quality
3D image-to-asset quality
```

Open-GPT-4o interaction quality:

```text
conversation naturalness
personality consistency
multi-turn memory behaviour
roleplay coherence
emotional tone control
low-corporate stiffness
safety without personality collapse
```

## Production Training Stack

To make this a full working model rather than a toy model, the project will eventually need:

```text
PyTorch
FSDP / DeepSpeed / Megatron-style distributed training
expert parallelism
tensor parallelism
pipeline parallelism
sequence parallelism
FlashAttention
checkpoint sharding
dataset streaming
fault-tolerant training
evaluation harness
vLLM / SGLang-style serving
OpenAI-compatible API server
realtime voice server
model-card generation
data-card generation
licence/provenance tracking
LLM Wiki experiment memory
```

## Proposed Repository Structure

```text
open-gpt-4o/
├── tokenizer/
│   ├── tiktoken_o200k.py
│   └── special_tokens.json
│
├── model/
│   ├── transformer.py
│   ├── attention.py
│   ├── moe.py
│   ├── router.py
│   ├── vision_adapter.py
│   ├── audio_adapter.py
│   ├── image_latent_bridge.py
│   └── shap_e_bridge.py
│
├── data/
│   ├── registry.yaml
│   ├── text_pipeline.py
│   ├── image_text_pipeline.py
│   ├── audio_pipeline.py
│   ├── video_pipeline.py
│   ├── gpt4o_style_pipeline.py
│   ├── gpt4o_output_pipeline.py
│   ├── tool_trace_pipeline.py
│   └── mixture_scheduler.py
│
├── train/
│   ├── pretrain_text.py
│   ├── pretrain_multimodal.py
│   ├── train_moe.py
│   ├── sft.py
│   ├── preference.py
│   ├── rlvr.py
│   └── distil.py
│
├── autoresearch/
│   ├── program.md
│   ├── experiment_controller.py
│   ├── config_generator.py
│   ├── benchmark_runner.py
│   ├── regression_tracker.py
│   ├── training_job_launcher.py
│   └── accepted_recipes/
│
├── llm_wiki/
│   ├── architecture_decisions/
│   ├── training_recipes/
│   ├── failed_experiments/
│   ├── benchmark_logs/
│   ├── posttraining_curricula/
│   └── model_cards/
│
├── evals/
│   ├── text_evals.py
│   ├── vision_evals.py
│   ├── audio_evals.py
│   ├── tool_evals.py
│   ├── generation_evals.py
│   └── regression_suite.py
│
├── inference/
│   ├── server.py
│   ├── tool_router.py
│   ├── streaming_voice.py
│   └── memory_runtime.py
│
└── ui/
    └── realtime_voice_component/
```

## Concrete Build Sequence

```text
1. Open an Open-GPT-4o full-model discussion issue.
2. Fork kyegomez/GPT4.
3. Create a nanochat-style minimal complete training pipeline.
4. Replace default/random-token examples with real tiktoken data loading.
5. Add GPT-4o/o200k-style tokenisation before any training.
6. Add Open-GPT-4o multimodal special tokens.
7. Rewrite the transformer core into a stable decoder-only architecture.
8. Add long-context support.
9. Add CLIP image encoder and vision adapter.
10. Add Whisper ASR path.
11. Add Whisper-derived audio embedding path.
12. Add realtime voice interface.
13. Add DALL-E/diffusion/GLIDE/consistency-decoder image-generation bridge.
14. Add Shap-E 3D-generation bridge.
15. Train 8B dense text-only.
16. Train 8B dense multimodal.
17. Fine-tune on public GPT-4o-style training datasets where legally reusable.
18. Fine-tune/distil on public GPT-4o output datasets where legally reusable.
19. Add AutoResearch pre-training and post-training loops.
20. Add LLM Wiki memory and experiment consolidation.
21. Convert to A8B MoE.
22. Train router with text, vision, audio, and tool tokens.
23. Scale to 120B/A10B class.
24. Scale to 180B-220B MoE.
25. Run GPT-4o-class benchmark suite.
26. Use 200B MoE as teacher.
27. Distil/prune into A8B MoE and 8B dense variants.
28. Publish weights, configs, evals, model cards, data cards, and training logs where possible.
```

## Open Questions for Contributors

1. Should Open-GPT-4o create a separate `open-gpt-4o-core` branch for the full-model track?
2. Should the first serious target be 8B dense or A8B MoE?
3. Should GPT-4o/o200k-style tokenisation be canonical from the beginning?
4. What multimodal special-token format should be standardised?
5. Should the first visual encoder be CLIP ViT-B/32, SigLIP, InternViT, or another encoder?
6. How should MoE router adaptation be trained for visual tokens?
7. How should MoE router adaptation be trained for audio tokens?
8. Should Shap-E and image diffusion be external tools first, then later native latent-output branches?
9. Which public GPT-4o-style datasets are legally reusable?
10. Which public GPT-4o output/distillation datasets are legally reusable?
11. How should LLM Wiki be integrated into AutoResearch?
12. What benchmark threshold qualifies a model as Open-GPT-4o-Mini?
13. What benchmark threshold qualifies a model as Open-GPT-4o?
14. What compute pool is required for each milestone?
15. Should the 200B MoE teacher be trained before distilling the A8B model, or should both be developed in parallel?
16. Can the Open-GPT-4o personality goal be preserved during high-capability post-training?

## Final Proposal

The proposed roadmap is:

```text
GPT-4o-style tiktoken before training
+ Kye Gomez GPT4 scaffold
+ nanochat-style complete training pipeline
+ AutoResearch pre-training optimiser
+ AutoResearch post-training optimiser
+ CLIP image-language encoder
+ Whisper ASR/audio encoder
+ realtime voice interface
+ DALL-E/diffusion/GLIDE/consistency-decoder image-generation bridge
+ Shap-E 3D-generation bridge
+ public GPT-4o-style datasets where legally reusable
+ public GPT-4o output/distillation datasets where legally reusable
+ LLM Wiki knowledge consolidation
+ 8B dense model
+ A8B MoE model
+ 120B/A10B MoE model
+ 180B-220B MoE model
= full Open-GPT-4o model family
```

The first milestone should be a minimal but complete Open-GPT-4o-Mini-8B-Dense training stack.

The second milestone should be an A8B MoE model with modality-aware routing.

The third milestone should be a 120B/A10B-class MoE model.

The final flagship target should be a ~200B MoE model aiming for GPT-4o-level benchmark equivalence.

This keeps the original personality and natural-conversation vision, but adds a serious full-model engineering track for those who want to build the actual open omni-modal architecture.
