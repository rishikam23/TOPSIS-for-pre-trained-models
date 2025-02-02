# TOPSIS for Pre-Trained Models in Text Sentence Similarity

## Overview

This project evaluates pre-trained sentence similarity models using the Technique for Order of Preference by Similarity to Ideal Solution (TOPSIS) method. The objective is to rank different models based on their performance in text sentence similarity tasks.

## Features

- Uses Sentence Transformers to compute sentence embeddings.

- Evaluates models using cosine similarity and Pearson correlation with human similarity scores.

- Ranks models using TOPSIS based on correlation, inference time, and model size.

- Visualizes results using bar plots, scatter plots, and heatmaps.

## Dataset
The project uses the STS Benchmark (stsb_multi_mt-English) dataset from the datasets library, containing sentence pairs with human-assigned similarity scores.

## Models Evaluated

The following pre-trained models from Sentence Transformers are evaluated:
- MiniLM-L6 (paraphrase-MiniLM-L6-v2)
- MiniLM-L12 (all-MiniLM-L12-v2)
- MPNet-Base (paraphrase-mpnet-base-v2)
- All-MPNet (all-mpnet-base-v2)

## Workflow

1. Load Dataset: STS Benchmark dataset is loaded and normalized.
2. Compute Embeddings: Sentence pairs are passed through pre-trained models to obtain embeddings.
3. Calculate Similarity: Cosine similarity is computed for each pair.
4. Evaluate Models: Pearson correlation, inference time, and model size are recorded.
5. Apply TOPSIS: Weights and criteria are applied to rank the models.
6. Visualize Results: Graphs and tables are generated to compare model performance.

## Installation
### Dependencies
Ensure you have the following installed:
'''
pip install numpy pandas sentence-transformers scipy datasets seaborn matplotlib tabulate
'''
### Usage
Run the Python script:
'''
>python 102203128.py "topsis_input.csv" "0.5,0.3,0.2" "+,-,-" "topsis_result.csv"
'''
The script will:
- Compute sentence similarities
- Rank models using TOPSIS
- Save results in topsis_result.csv
- Generate and display visualizations

## Results
The results are saved in topsis_result.csv.
Graphical comparisons include:
- Bar Plot: TOPSIS scores for each model
- Scatter Plot: Correlation vs. Inference time
- Heatmap: Overall model performance

### Output Table
+---+------------+--------------------+--------------------+------------+--------------------+------+
|   |   Model    |    Correlation     |   Inference Time   | Model Size |    Topsis Score    | Rank |
+---+------------+--------------------+--------------------+------------+--------------------+------+
| 0 | MiniLM-L6  | 0.8470136838318714 | 0.0190228582320161 |     22     | 0.9728091958885824 |  1   |
| 1 | MiniLM-L12 | 0.8432774106996839 | 0.0372248405497019 |     33     | 0.8434844723551501 |  2   |
| 2 | MPNet-Base | 0.8671197324805402 | 0.1293838268820151 |    100     | 0.0677648914493907 |  3   |
| 3 | All-MPNet  | 0.8580658363697954 | 0.1298294495781477 |    110     | 0.0201429820185125 |  4   |
+---+------------+--------------------+--------------------+------------+--------------------+------+

### Graphs

TOPSIS Score for Pre-Trained Models
![image](https://github.com/user-attachments/assets/c7681419-cec2-4c3d-b1a9-7a6c85fdf31f)

Model Performance: Correlation vs Inference Time
![image](https://github.com/user-attachments/assets/2ea97ad7-9205-498d-b61e-7d40554155df)

Heatmap of Overall Performance
![image](https://github.com/user-attachments/assets/0f484df6-26f1-4953-bf19-b084bf6fb092)

## License
This project is licensed under the MIT License.

## Author
Rishika Mathur
