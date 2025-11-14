# NLP-HW-Embeddings-and-Embedding-Atlas
This project computes embeddings for DNA sequences using the DNABERT-S model and prepares them for visualization in Embedding Atlas.

## Quick Start

### 1. Install dependencies:
```bash
pip install -r requirements.txt
```

###  2. Run the notebook:
* Open embed.ipynb in Google Colab
* Follow the execution steps below
* Output: embeddings_full.parquet ready for Atlas (in this repository you can find a embeddings_1000.parquet -- small dataset for visualization)

###  3. Visualize in Embedding Atlas:

* [Visit Embedding Atlas site](https://apple.github.io/embedding-atlas/upload/)
* Upload .parquet file
* Use precomputed projection_x/projection_y, then color by label

## Execution steps for Google Colab

**Important:** Follow these steps exactly for successful execution:
### 1. Run the first cell in notebook:
```python
import torch
from transformers import AutoTokenizer, AutoModel

tokenizer = AutoTokenizer.from_pretrained("zhihan1996/DNABERT-S", trust_remote_code=True)
model = AutoModel.from_pretrained("zhihan1996/DNABERT-S", trust_remote_code=True)
```
### 2. Uncomment and execute the triton uninstallation:
```python
!pip uninstall triton
```
### 3. Restart the runtime: 
Runtime → Restart session

### 4. Now run the entire notebook sequentially (!!!comment the second cell!!!)
