# Egocentric Vision: Enhancements for the Ego4D NLQ Benchmark

This repository contains the work for a project focused on enhancing a baseline model for the Ego4D Natural Language Queries (NLQ) benchmark. The goal is to improve temporal localization performance within egocentric videos by exploring different video feature encoders and language models.

## Abstract

In this project, enhancements to a baseline model (VSLNet) for the Ego4D Natural Language Queries (NLQ) benchmark are presented, aimed at improving temporal localization performance within egocentric videos. Different video feature encoders, specifically Omnivore and EgoVLP, are systematically evaluated to analyze their impact on model accuracy. Moreover, the efficacy of different language embeddings (BERT and GloVe) is compared to determine their suitability for temporal localization tasks. To extend the analysis, 50 queries with correctly retrieved segments are manually annotated to define textual ground truths. The corresponding clips are extracted via ffmpeg and processed with the Video-LLaVA model to generate textual responses, which are then evaluated using different metrics.

## Repository Structure
The repository is organized as:
```
Natural-language-queries-in-Egocentric-vision
    ├── notebook/                              
        └── Ego4D_NLQ_Benchmark.ipynb           # code to compare model architectures, feature extractor
        └── egovlp_vslnet_extension.ipynb       # code related to the extension
    ├── paper/
        └── paper.pdf
    ├── .gitattributes
    ├── README.md                               # description of the project
    └── requirements.txt                              
```

## Notebooks

This project includes two main Jupyter notebooks:

-   **`Ego4D_NLQ_Benchmark.ipynb`**: This notebook serves as a quickstart for the Ego4D Moments Benchmark (NLQ) task. It details setting up the environment, downloading data, and training the baseline VSLBase and VSLNet model with Omnivore and egoVLP features.

-   **`egovlp_vslnet_extension.ipynb`**: This notebook extends the baseline by implementing and evaluating the VSLNet model with EgoVLP features. It also contains the analysis using the Video-LLaVA model on a manually annotated subset of queries, with results evaluated using metrics such as BLEU and ROUGE.

## Getting Started

Follow these steps to set up and run the project notebooks. The project can be run on Google Colab or on a local machine.

### Prerequisites

-   Python 3.x (for local setup) or Google Colab
-   Access to a GPU is highly recommended for training the models.

### Setup

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/Keremm26/Egocentric-NLQ.git](https://github.com/Keremm26/Egocentric-NLQ.git)
    cd Egocentric-NLQ
    ```

2.  **Set up the environment (choose one):**

    * **For Google Colab:** Simply open the notebooks in Colab. The necessary dependencies are installed within the notebooks themselves.

    * **For Local Setup:** It is recommended to use a virtual environment.
        ```bash
        # Create and activate a virtual environment
        python -m venv venv
        source venv/bin/activate  # On Windows use `venv\Scripts\activate`

        # Install dependencies
        pip install -r requirements.txt
        ```

3.  **Ego4D Dataset Access:**
    -   To download the Ego4D dataset and its features, you must first sign the Ego4D License at [ego4ddataset.com](https://ego4ddataset.com) to obtain your access and secret keys.
    -   Open the notebooks and insert your `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY` in the designated cells.

### Usage

1.  Navigate to the `notebooks/` directory.
2.  Open either `Ego4D_NLQ_Benchmark.ipynb` or `egovlp_vslnet_extension.ipynb` in your Jupyter or Colab environment.
3.  Follow the instructions within the notebook, running the cells sequentially to download data, prepare the dataset, and train/evaluate the models.

## Resources & Acknowledgments

This project is based on the Ego4D NLQ benchmark and the VSLNet baseline model. We would like to acknowledge the following resources:

-   **Baseline Repo:** [EGO4D/episodic-memory/tree/main/NLQ/VSLNet](https://github.com/EGO4D/episodic-memory/tree/main/NLQ/VSLNet)
-   **Ego4D Docs:** [ego4d-data.org/docs/benchmarks/episodic-memory/](https://ego4d-data.org/docs/benchmarks/episodic-memory/)


