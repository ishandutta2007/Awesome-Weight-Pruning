# Post-Training Pruning (PTP)

- **Year of Introduction:** 1992
- **Original Paper:** [Post-Training Pruning (PTP) Paper](https://papers.nips.cc/paper/1992/hash/303ed4c69846ab36c2904d3ba8573887-Abstract.html)

## Architectural & Process Flow
```mermaid
flowchart LR
    A[Fully Trained Dense Model] --> B[One-shot Pruning Step]
    B --> C[Calibration/Re-optimization]
    C --> D[Compressed Model Ready for Deployment]
```

## Detailed Concept & Explanation
Post-Training Pruning (PTP) refers to pruning a model after it has fully converged, without requiring complete retraining from scratch. Early methods like Optimal Brain Surgeon (1992) optimized weight updates post-pruning to reconstruct the model's outputs. In the context of modern Large Language Models (LLMs), retraining is extremely expensive, which has sparked a resurgence in PTP methods like Wanda and SparseGPT. These algorithms analyze weight statistics and activations over a small calibration dataset to prune and adjust weights efficiently in a single pass.
