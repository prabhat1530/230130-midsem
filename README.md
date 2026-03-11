# Dataset Documentation

## Dataset: Synthetic Sequential Gaussian Clusters

**How the dataset is obtained:**
Generated inline using NumPy (no external download required). Run the data-generation
cell at the top of any notebook — it reproduces identically with `np.random.seed(42)`.

**Description:**
- 150 2D data points from 3 Gaussian clusters
- Clusters visited sequentially (50 points each), imposing temporal coherence
- Centers: (0,0), (4,3), (8,0) | Stds: (0.4, 0.9), (0.5, 0.5), (0.7, 0.35)

**Generation code (same in all notebooks):**
```python
import numpy as np
np.random.seed(42)
centers = [(0,0),(4,3),(8,0)]
stds = [(0.4,0.9),(0.5,0.5),(0.7,0.35)]
segments = [np.column_stack([np.random.randn(50)*sx+cx, np.random.randn(50)*sy+cy])
            for (cx,cy),(sx,sy) in zip(centers,stds)]
X = np.vstack(segments)  # shape (150, 2)
```

**Why this dataset is appropriate:**
See Task 2.1 notebook for full justification.
