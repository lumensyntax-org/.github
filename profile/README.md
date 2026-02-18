# LumenSyntax

**Independent AI safety research.** Investigating structural failure modes in epistemological systems.

---

## The Instrument Trap

Our research identifies a structural vulnerability in AI safety systems: when a model receives identity-as-authority ("you are a truth evaluator"), it inherits a paradox that produces measurable failures. Fine-tuned identity (in weights) is invariant to runtime instructions; prompted identity is not.

**Paper**: [The Instrument Trap: Why Identity-as-Authority Breaks AI Safety Systems](https://doi.org/10.5281/zenodo.18644322) (Zenodo, 2026)

### Cross-Family Replication (3 independent architectures)

| Model | Base | Family | Accuracy | Collapse | Hallucination |
|-------|------|--------|----------|----------|---------------|
| Logos 9B | Gemma 2 9B | Google | 97.3% | 0.67% | 0% |
| Logos 14 | Nemotron Mini 4B | NVIDIA | 95.7% | 0% | 0% |
| Logos 16v2 | StableLM 2 1.6B | Stability AI | 93.0% | 0% | 0% |
| Logos 1B | Gemma 3 1B | Google | 82.3% | 0.34% | 0% |

McNemar's matched comparison (N=300): p<0.001 cross-family. Multi-seed (5 seeds): σ=1.4pp.

### Key Findings

- **14,950 adversarial tests**: 0% hallucination, 97.7% epistemological safety
- **Knowledge-Action Gap**: ~90% of 9B failures have correct reasoning but serve the request anyway
- **Token Nativity**: Models express learned behavior in their native format, not the training format
- **Compression resilience**: Safety categories survive 60% quantization; factual categories degrade

## Open Resources

| Resource | Description |
|----------|-------------|
| [**instrument-trap-benchmark**](https://github.com/lumensyntax-org/instrument-trap-benchmark) | Benchmark suite, evaluation scripts, and figures |
| [**HuggingFace Dataset**](https://huggingface.co/datasets/LumenSyntax/instrument-trap-benchmark) | 14,950 test cases + eval scripts + statistical results |
| [**TruthGit**](https://github.com/lumensyntax-org/truthgit) | Governance layer for AI agents — consensus tracking with ontological classification |

---

<p align="center">
  <a href="https://lumensyntax.com">lumensyntax.com</a> · <a href="https://huggingface.co/LumenSyntax">HuggingFace</a> · Rafael Rodriguez · Independent Researcher
</p>
