# Factorization and Surprise as Label-Free Control Signals for JEPA

Research project completed at the **SMILES 2026 Summer School**.

[**Read the paper**](./paper.pdf) · [**Experimental code**](https://github.com/davynchi/jepa_r)

## Overview

Joint-Embedding Predictive Architectures (JEPAs) learn by predicting latent representations. However, a decreasing training loss does not necessarily imply better semantic representations and may conceal representation collapse.

This work investigates two label-free signals for controlling and diagnosing JEPA training:

- **Surprise** — deciding which observations are most useful for model updates.
- **Factorization** — measuring whether relation-specific structure emerges in the latent space.

We evaluate these ideas on a synthetic vector world, Shapes3D, Tiny ImageNet, and Moving-MNIST.

## Key findings

- Surprise based on learning progress can distinguish difficult but learnable observations from irreducible noise in a controlled synthetic setting.
- Richness-aligned surprise detects corrupted samples, but may concentrate the sampling distribution and reduce semantic performance.
- A three-dimensional Shapes3D subspace preserves nearly all shape information while suppressing contextual information.
- Official I-JEPA checkpoints contain reproducible joint block structure beyond a spectrum-preserving random baseline.
- Factorization is strongest during early training and decreases while downstream probe performance continues to improve.
- Neither surprise nor factorization serves as a universal scalar measure of representation quality.

These findings motivate a relation-conditioned representation profile based on capacity, predictability, modularity, sampling support, and downstream utility.

## My contribution

I worked on:

- surprise-based sampling strategies;
- causal Moving-MNIST experiments;
- training-stability and shortcut audits;
- motion probing and evaluation;
- the motion-weighted training objective.

## Authors

- Andrey Vorfolomeev
- Konstantin Kostikov
- Alexander Korolev
- Mikhail Davydov

Supervisor: Mark Obozov.

## Code

The experimental implementation and research artifacts are available in the shared repository:

[github.com/davynchi/jepa_r](https://github.com/davynchi/jepa_r)

## Citation

```bibtex
@article{vorfolomeev2026factorization,
  title   = {Factorization and Surprise as Label-Free Control Signals
             for Joint-Embedding Predictive Architectures},
  author  = {Vorfolomeev, Andrey and Kostikov, Konstantin and
             Korolev, Alexander and Davydov, Mikhail},
  year    = {2026}
}
```

## Status

Research manuscript. The results include both successful findings and negative experimental evidence. The paper does not claim that the proposed signals universally improve JEPA training.
