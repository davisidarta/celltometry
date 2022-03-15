# CellTOMetry: single-Cell Topologically Optimized Geometry

CellTOMetry is a python library to
orchestrate topological single-cell data analysis. It is centered around 
[TopOMetry](https://github.com/davisidarta/topometry) and 
[scanpy](https://scanpy.readthedocs.io/en/stable/index.html).

## Installation and dependencies

CellTOMetry requires [scanpy](https://scanpy.readthedocs.io/en/stable/index.html) 
and [TopOMetry](https://github.com/davisidarta/topometry). After having them installed,
install celltometry with:

```
pip3 install celltometry
```

## Using CellTOMetry with scanpy

First, we load libraries and some data to work with:
```
import scanpy as sc
import topo as tp
import celltometry as ct

# Load the PBMC3k dataset
adata = sc.datasets.pbmc3k()
```

Next, we perform the default preprocessing workflow with scanpy: libraries are size-normalized,
log-transformed for variance stabilization, and subset to highly variable genes. 

```
# Normalize and find highly variable genes
adata = ct.preprocess(adata)
```

Then, we proceed to the default scanpy workflow. It corresponds to:
* Scaling data (optional, changes adata.X) - ``
* Performing PCA ()


Similar to preprocessing, we wrap it
with an one-liner:

```
adata = ct.default_workflow(adata, scale=True)
```

sc.pl.umap(adata, color=['leiden'])

```



