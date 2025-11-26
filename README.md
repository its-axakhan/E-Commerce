# Multilingual E-Commerce Re-Ranking Pipelines (US & RU ESCI)

This repository contains **two end-to-end Jupyter notebooks** that implement and document
the experimental pipelines for the thesis *“Enhancing Multilingual E-Commerce Search
through Classical and Transformer-Based Re-Ranking”*.

- `US_esci_pipeline_gpu_executed.ipynb` – full English (US) ESCI pipeline  
- `RU_esci_pipeline_gpu_executed.ipynb` – Russian pipeline built from a translated subset of the US ESCI data

Download the ESCI Dataset from here: https://www.amazon.science/code-and-datasets/shopping-queries-dataset-a-large-scale-esci-benchmark-for-improving-product-search?

For US store dataset in sub folder : 
esci_pipeline/data/esci_train.parquet
esci_pipeline/data/esci_test.parquet

For RU store dataset in subfolder :
esci_pipeline/data_ru/esci_train.parquet
esci_pipeline/data_ru/esci_test.parquet


artifacts and other folders will be created under esci_pipeline folder

Both notebooks are designed to be **fully reproducible on a single GPU machine** and use
the same overall workflow:

1. Load and clean the Amazon ESCI data
2. Construct unified product text and contextual features
3. Generate initial candidates (e.g. BM25 / base ranker)
4. Apply classical re-rankers (RRF, MMR, LTR) and transformer-based re-rankers
5. Evaluate with ranking metrics (nDCG@k, P@k, gAUC)
6. Save intermediate artifacts and final results to disk


