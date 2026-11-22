# Awesome-SSD-Fast-Model-Inference-Storage-Systems
# Awesome-SSD-Fast-Model-Inference-Storage-Systems

# Top SSD Fast Model Inference & Storage Systems Ecosystem

**Curated List of SaaS/Hosted Platforms & Open-Source GitHub Projects**  
*Focused on SSD-Offloaded LLM Inference, High-Throughput Serving Engines, KV-Cache Storage & Quantized Kernels*  
**Last updated: November 2026**

This repository tracks notable **SaaS/hosted inference platforms** and **open-source GitHub projects** for **SSD Fast Model Inference & Storage Systems**. These tools enable developers, ML engineers, and researchers to run massive Mixture-of-Experts (MoE) and dense language models larger than available RAM/VRAM by streaming weights directly from NVMe SSDs, while also powering ultra-fast GPU serving, distributed KV-cache offloading, and custom quantization kernels.

**Examples** include wici-ai/inferssd, llama.cpp, vLLM, TensorRT-LLM, SGLang, LMDeploy, Text Generation Inference (TGI), DeepSpeed, ExLlamaV2, Aphrodite Engine, Marlin, KTransformers, FlexGen, AirLLM, LMCache, Mooncake, Fireworks AI, Together AI, GroqCloud, and Baseten.

**Open-source emphasis**: This list heavily expands on active open-source SSD-streaming runtimes, high-throughput inference engines, KV-cache storage tiers, and low-bit CUDA/CPU kernels — ideal for AI infrastructure engineers and local-AI builders maximizing hardware efficiency without massive VRAM clusters.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saashosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[Fireworks AI](https://fireworks.ai)**  
  Ultra-fast generative AI inference cloud powered by custom FireAttention kernels, speculative decoding, and multi-tier weight/KV caching for low-latency model serving.

- **[Together AI](https://together.ai)**  
  Cloud inference and fine-tuning platform built on FlashAttention and custom distributed serving engines for open-weight LLMs and MoE models.

- **[Baseten](https://baseten.co)**  
  Managed ML model deployment and inference infrastructure integrating TensorRT-LLM, vLLM, and fast cold-start storage streaming for production workloads.

- **[Modal](https://modal.com)**  
  Serverless cloud compute platform optimized for AI inference with rapid container snapshot loading, distributed NVMe model caching, and on-demand GPUs.

- **[Anyscale Endpoints](https://anyscale.com)**  
  Managed LLM serving platform built on Ray and vLLM offering autoscaling, continuous batching, and high-throughput enterprise APIs.

- **[Hugging Face Inference Endpoints](https://huggingface.co)**  
  Managed cloud deployment service powered by Text Generation Inference (TGI) and vLLM for dedicated, production-ready model hosting.

- **[NVIDIA NIM](https://nvidia.com)**  
  Hosted and enterprise-deployable inference microservices leveraging TensorRT-LLM and optimized GPU storage pipelines.


## Open-Source GitHub Projects

- **[InferSSD (wici-ai/inferssd)](https://github.com/wici-ai/inferssd)**  
  Open-source inference engine built on `llama.cpp` that streams Mixture-of-Experts (MoE) weights directly from NVMe SSDs via OS read rings (`io_uring`, `IoRing`, `F_NOCACHE`), allowing 700B–800B+ parameter GGUF models to run on consumer hardware with limited RAM/VRAM.

- **[vLLM](https://github.com)**  
  High-throughput, memory-efficient LLM inference and serving engine featuring PagedAttention, continuous batching, FP8/INT4 quantization, and tiered CPU/disk KV-cache offloading.

- **[SGLang](https://github.com)**  
  Fast serving framework for large language and vision-language models utilizing RadixAttention for automatic KV-cache reuse and SSD/CPU hierarchical caching.

- **[TensorRT-LLM](https://github.com)**  
  NVIDIA's open-source library for optimizing LLM inference with custom FlashAttention kernels, in-flight batching, tensor parallelism, and NVMe/host KV-cache offloading.

- **[llama.cpp](https://github.com)**  
  Foundational C/C++ LLM inference engine supporting memory-mapped (`mmap`) GGUF model execution directly from SSD alongside CPU, CUDA, Metal, and Vulkan backends.

- **[LMDeploy](https://github.com)**  
  High-performance toolkit for compressing, deploying, and serving LLMs featuring TurboMind persistent batching, blocked KV cache, and 4-bit weight quantization.

- **[Text Generation Inference (TGI)](https://github.com)**  
  Hugging Face's production-grade Rust and Python toolkit for deploying and serving LLMs with FlashAttention, PagedAttention, and safetensors fast weight loading.

- **[DeepSpeed (DeepSpeed-FastGen / ZeRO-Inference)](https://github.com)**  
  Microsoft's deep learning optimization library featuring ZeRO-Inference for streaming massive model weights from NVMe SSDs and CPU RAM to single or multi-GPU setups.

- **[ExLlamaV2](https://github.com)**  
  Fast inference library for running quantized EXL2 and GPTQ weights on consumer NVIDIA/AMD GPUs with high token throughput and dynamic VRAM allocation.

- **[Aphrodite Engine](https://github.com)**  
  Large-scale open-source inference engine built on vLLM with broad quantization support (EXL2, AQLM, QuIP#, Marlin) and OpenAI-compatible serving.

- **[Marlin](https://github.com)**  
  Highly optimized FP16xINT4 CUDA matrix-multiplication kernel delivering near-ideal speedups for quantized LLM inference on NVIDIA GPUs.

- **[KTransformers](https://github.com)**  
  Flexible kernel-injection framework designed for heterogeneous CPU/GPU MoE inference, keeping cold experts in system RAM/storage while accelerating hot computation on GPU.

- **[LMCache](https://github.com)**  
  Open-source KV-cache storage and sharing layer for vLLM that persists and reuses KV caches across GPU, CPU RAM, and local NVMe SSDs to slash time-to-first-token (TTFT).

- **[Mooncake](https://github.com)**  
  Kimi's open-source KVCache-centric disaggregated inference architecture pooling DRAM, SSD, and RDMA resources across clusters for massive-context serving.

- **[FlexGen](https://github.com)** & **[AirLLM](https://github.com)**  
  Open-source offloading runtimes that layer-stream weights from SSD and CPU memory to run 70B+ parameter models on single low-VRAM GPUs.

### Additional Strong Open-Source Options

- **[FlashAttention](https://github.com)** & **[FlashInfer](https://github.com)** — IO-aware exact attention algorithms and customizable kernel libraries that eliminate memory-bandwidth bottlenecks during inference.
- **[MLX](https://github.com)** & **[mlx-lm](https://github.com-lm)** — Apple's array framework and LLM toolkit exploiting unified memory and fast Apple Silicon SSDs for local inference.
- **[Ollama](https://github.com)** & **[LocalAI](https://github.com)** — Developer-friendly local model runners and OpenAI-compatible API servers built on `llama.cpp` and `vLLM`.
- **[PowerInfer](https://github.com)** — High-speed local inference engine exploiting neuron activation locality to split hot/cold weights across GPU and CPU/storage.
- **[NVIDIA Magnum IO GPUDirect Storage (GDS)](https://github.com)** — Direct DMA data path between NVMe SSD storage and GPU memory, bypassing CPU bounce buffers for ultra-fast model loading.
- **[safetensors](https://github.com)** — Zero-copy, memory-mappable tensor serialization format engineered for instant, safe weight loading from SSDs.

**Frameworks for building custom systems**: Combine **InferSSD** or **llama.cpp** for SSD-streamed local MoE execution on consumer hardware, or pair **vLLM** / **SGLang** with **LMCache**, **Marlin**, and **GPUDirect Storage** for high-throughput production serving with tiered NVMe KV caching.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- SSD-streamed inference engines perform sustained high-bandwidth NVMe reads; ensure adequate SSD free space, PCIe Gen4/Gen5 bandwidth, and thermal cooling, and monitor drive SMART health.
- Local inference servers (such as `inferssd serve` or `vLLM`) may expose unauthenticated OpenAI-compatible endpoints by default; restrict binding to `127.0.0.1` or place behind an authenticated reverse proxy on shared networks.

---

**Made for AI infrastructure engineers, ML researchers, systems programmers, and local-LLM enthusiasts.**  
Let's make fast model inference and SSD storage offloading more accessible, efficient, and open to everyone.
