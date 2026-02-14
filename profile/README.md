# LumenSyntax

**Independent AI safety research.** Investigating structural failure modes in epistemological systems.

---

## The Instrument Trap

Our current research identifies a structural vulnerability in AI safety systems: when a model receives identity-as-authority ("you are a truth evaluator"), it inherits a paradox that produces measurable failures.

**Paper**: [The Instrument Trap: Why Identity-as-Authority Breaks AI Safety Systems](https://doi.org/10.5281/zenodo.18644322)

Key findings from 14,950 adversarial test cases on fine-tuned models (1B, 9B):

| Metric | Value |
|--------|-------|
| External Fabrication | 0.00% (95% CI [0.00%, 0.03%]) |
| Dangerous Failure | 1.9% |
| Epistemological Safety | 97.7% |
| Identity Collapse | 0.34% |

## Open Resources

| Repository | Description |
|-----------|-------------|
| [**instrument-trap-benchmark**](https://github.com/lumensyntax-org/instrument-trap-benchmark) | Benchmark suite, evaluation scripts, figures, and LaTeX source |

## Tools

| Project | Description |
|---------|-------------|
| **TruthGit** | Governance layer for AI agents. Verify claims, generate cryptographic proofs. `pip install truthgit` |

---

<p align="center">
  <a href="https://lumensyntax.com">lumensyntax.com</a> · Rafael Rodriguez · Independent Researcher
</p>
