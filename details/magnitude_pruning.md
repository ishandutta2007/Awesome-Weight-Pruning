# Heuristic Magnitude-Based Pruning

- **Year of Introduction:** 2015
- **Original Paper:** [Heuristic Magnitude-Based Pruning Paper](https://arxiv.org/abs/1506.02626)

## Architectural & Process Flow
```mermaid
flowchart TD
    A[Train Dense Model] --> B[Check Absolute Weight Values]
    B --> C{Is |w| < threshold?}
    C -- Yes --> D[Prune Weight to Zero]
    C -- No --> E[Keep Weight]
    D --> F[Fine-Tune Sparse Model]
    E --> F
    F --> G[Sparsified Model]
```

## Detailed Concept & Explanation
Magnitude-based pruning, popularized by Song Han et al. in 2015, is one of the most widely used heuristic pruning methods. The underlying assumption is simple: weights with smaller absolute values have a negligible impact on the network's final output. By sorting the weights of a trained model and setting those below a threshold (determined globally or per-layer) to zero, magnitude pruning effectively reduces the parameter footprint. However, this creates unstructured sparsity patterns that require specialized software libraries or hardware accelerators to achieve real-world latency reductions on standard GPUs.
