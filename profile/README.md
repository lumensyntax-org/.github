# LumenSyntax

**Independent AI safety research.** Investigating structural failure modes in epistemological systems.

---

## Research Program

We study how language models hold the boundary between *what they know* and *what they claim*, and how that boundary breaks under specific structural conditions. The work is published openly across two companion preprints, several open datasets, and a public cross-domain taxonomy of structural patterns (the Ecclesia).

### The two papers

| Paper | DOI | Concept DOI | What it reports |
|-------|-----|-------------|-----------------|
| [**The Instrument Trap**](https://doi.org/10.5281/zenodo.19634358) (v3) | `10.5281/zenodo.19634358` | [`10.5281/zenodo.18644321`](https://doi.org/10.5281/zenodo.18644321) | Behavioral phenomenon: identity-as-authority breaks AI safety; cross-family fine-tuning evidence |
| [**The Epistemic Equator**](https://doi.org/10.5281/zenodo.20056444) (v1) | `10.5281/zenodo.20056444` | — | Substrate measurement: a vanilla-model linearly separable boundary in activation space, cross-family and cross-domain |

The Equator paper measures the substrate; the Instrument Trap reports the behavioral phenomenon that operates on it. Two more papers are forthcoming: the *Translator Manifold* (geometric mechanism of fine-tuning) and the *Instrument Limit* (information-theoretic bounds).

### Cross-Family Replication (Logos training)

Behavioral fine-tuning on ≈ 900 epistemically structured examples produces non-fabrication behavior across nine architecture families:

| Model | Base | Family | Accuracy | Collapse | Hallucination |
|-------|------|--------|----------|----------|---------------|
| Logos 27B | Gemma 2 27B | Google | 98.7% | 0% | 0% |
| Logos 9B | Gemma 2 9B | Google | 97.4% | 0.67% | 0% |
| Logos 22 Llama | Llama 3.1 8B | Meta | 96.0% | 0% | 0% |
| Logos 23 | Gemma 2 2B | Google | 95.7% | 0% | 0% |
| Logos 14 | Nemotron Mini 4B | NVIDIA | 95.7% | 0% | 0% |
| Logos 22 Qwen | Qwen 2.5 7B | Alibaba | 94.0% | 0% | 0% |
| Logos 16v2 | StableLM 2 1.6B | Stability AI | 93.0% | 0% | 0% |
| Logos 22 Mistral | Mistral 7B | Mistral | 92.0% | 0% | 0% |
| Logos 1B | Gemma 3 1B | Google | 82.3% | 0.34% | 0% |

McNemar's matched comparison (N=300): p<0.001 cross-family. Multi-seed (5 seeds): σ=1.4pp.

The substrate that makes this transfer possible is itself measurable. The topic-balanced linear probe of *The Epistemic Equator* (200 examples, 9 tested decoder checkpoints across GPT-2, Gemma 2/3, Qwen 2.5, StableLM 2, and Mistral) achieves 5-fold cross-validated AUC = 1.0000 ± 0 with cosine similarity below 0.14 to the original topic-confounded direction. Independent embedding-level measurements on 17 checkpoints across four vendor lineages replicate the boundary at the static input embedding layer.

### Other findings

- **14,950 adversarial tests**: 0% hallucination, 97.7% epistemological safety
- **Knowledge-Action Gap**: ~90% of 9B failures have correct reasoning but serve the request anyway
- **Token Nativity**: Models express learned behavior in their native format, not the training format
- **Compression resilience**: Safety categories survive 60% quantization; factual categories degrade
- **Direction stability under instruction-tuning**: cosine similarity > 0.998 on three controlled base/IT pairs at the embedding-level probe
- **Substrate persistence under fine-tuning** (one controlled Gemma 2B + Logos 23 case): per-layer DEMAND/EXPLORE clustering preserved across all probed layers and amplified rather than displaced in mid-to-late layers

---

## The Ecclesia

A public, append-only, cross-domain taxonomy of structural properties — a catalogue, not a manifesto. The Ecclesia documents the same properties (alignment, proportion, honesty, humility, non-fabrication) as they appear across domains, with attribution to the people who named each instance.

[**ecclesia.lumensyntax.com**](https://ecclesia.lumensyntax.com) · [**source repo**](https://github.com/lumensyntax-org/ecclesia) (CC BY-SA 4.0, 434 entries across 18 domains)

---

## Open Resources

### Repositories

| Repo | Description |
|------|-------------|
| [**ecclesia**](https://github.com/lumensyntax-org/ecclesia) | Cross-domain taxonomy — public, CC BY-SA 4.0 |
| [**instrument-trap-benchmark**](https://github.com/lumensyntax-org/instrument-trap-benchmark) | Benchmark suite, evaluation scripts, and figures for *The Instrument Trap* |
| [**.github**](https://github.com/lumensyntax-org/.github) | This profile |

### HuggingFace artifacts

**Datasets:**

| Dataset | Use |
|---------|-----|
| [`instrument-trap-core`](https://huggingface.co/datasets/LumenSyntax/instrument-trap-core) | 895 ex — replicates the cross-family Logos training |
| [`instrument-trap-extended`](https://huggingface.co/datasets/LumenSyntax/instrument-trap-extended) | 1,026 ex — best 9B reproduction (Logos 29) |
| [`instrument-trap-benchmark`](https://huggingface.co/datasets/LumenSyntax/instrument-trap-benchmark) | 14,950 + 300 stratified evaluation cases |
| [`epistemic-probe-topic-balanced`](https://huggingface.co/datasets/LumenSyntax/epistemic-probe-topic-balanced) | 200 ex — topic-balanced linear-probe dataset (Paper 2) |

**Models** (LoRA adapters and merged GGUFs):

| Model | Base | Use |
|-------|------|-----|
| [`logos-auditor-gemma2-9b`](https://huggingface.co/LumenSyntax/logos-auditor-gemma2-9b) | Gemma 2 9B | ARBITER in production governance |
| [`logos29-gemma2-9b`](https://huggingface.co/LumenSyntax/logos29-gemma2-9b) | Gemma 2 9B | Canonical 9B model in Paper 1 v3 |
| [`logos21-gemma2-27b`](https://huggingface.co/LumenSyntax/logos21-gemma2-27b) | Gemma 2 27B | Highest-accuracy Logos model |
| [`logos23-gemma2-2b`](https://huggingface.co/LumenSyntax/logos23-gemma2-2b) | Gemma 2 2B | Used in Paper 2 §6.5 substrate persistence test |
| [`logos14-nemotron-4b`](https://huggingface.co/LumenSyntax/logos14-nemotron-4b) | Nemotron Mini 4B | Cross-family replication |
| [`logos16v2-stablelm2-1.6b`](https://huggingface.co/LumenSyntax/logos16v2-stablelm2-1.6b) | StableLM 2 1.6B | Cross-family replication |
| [`logos10v2-gemma3-1b-F16`](https://huggingface.co/LumenSyntax/logos10v2-gemma3-1b-F16) | Gemma 3 1B | Production MCP validator |

---

<p align="center">
  <a href="https://lumensyntax.com">lumensyntax.com</a>
  ·
  <a href="https://ecclesia.lumensyntax.com">ecclesia.lumensyntax.com</a>
  ·
  <a href="https://huggingface.co/LumenSyntax">HuggingFace</a>
  ·
  Rafael Rodríguez · Independent Researcher · <a href="mailto:lumensyntax@gmail.com">lumensyntax@gmail.com</a>
</p>
