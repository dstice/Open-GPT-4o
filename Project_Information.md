# Open-GPT-4o

## Suggested Roadmap for Open-GPT-4o

Open-GPT-4o is a proposed full open GPT-4o-class omni-modal model family. The aim is to move beyond personality-only fine-tuning and into a serious engineering roadmap for a full working model family: from an 8B dense model or A8B MoE model to a ~200B MoE model targeting GPT-4o-level benchmark equivalence.

This is not intended to be a toy model, a demo model, or a research-only model. The goal is a full working Open-GPT-4o-style omni-modal architecture.

Open-GPT-4o should preserve the natural conversational feel, personality, roleplay capability, and less rigid interaction style that inspired the broader 4o-style movement, while adding a serious full-model engineering track.

## Project Links

* Open-GPT-4o repository: [https://github.com/AonzOG/Open-GPT-4o](https://github.com/AonzOG/Open-GPT-4o)

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

* Open-GPT-4o repository: Open-GPT-4o repository: [https://github.com/AonzOG/Open-GPT-4o](https://github.com/AonzOG/Open-GPT-4o)

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
