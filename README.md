# Sentiment-analysis-on-Movie-Reviews
A comparative study on sentiment analysis, implementing classic machine learning models and modern transformer-based architectures (BERT and BERT+BiLSTM)

# Sentiment Analysis of Movie Reviews

This repository contains the code for a comparative study on sentiment analysis, implementing classic machine learning models and modern transformer-based architectures (BERT and BERT+BiLSTM).

---

## Prerequisites

*   **Python 3.8+**
*   A **Kaggle Account** to download the dataset.
*   The **`train.tsv` dataset file**.
    *   Download from the [Kaggle Competition Page](https://www.kaggle.com/c/sentiment-analysis-on-movie-reviews/data).
    *   Unzip the downloaded file to get `train.tsv`.

---

## Setup and Execution

This project can be run either in Google Colab (recommended for free GPU access) or on a local machine with a suitable GPU.

### Method 1: Google Colab (Recommended)

This is the easiest and recommended method, as it provides the necessary GPU hardware for free.

**1. Upload Data to Google Drive:**
*   Navigate to your Google Drive.
*   Upload the `train.tsv` file to the main "My Drive" directory. The notebook is pre-configured to look for it here.

**2. Open in Google Colab:**
*   Go to [colab.research.google.com](https://colab.research.google.com).
*   Select `File -> Upload notebook...` and choose the `.ipynb` file from this repository.

**3. Enable GPU:**
*   In the Colab menu, navigate to `Runtime -> Change runtime type`.
*   Under "Hardware accelerator," select **GPU** and click **Save**. This is crucial.

**4. Run the Notebook:**
*   Execute the cells in the notebook from top to bottom.
*   You will be prompted to **authorize Google Drive access**. This allows the notebook to read `train.tsv` and save the trained models.

### Method 2: Local Execution
This method is for users who want to run the code on their own machine. Training the BERT models on a CPU will be extremely slow.

**1. Environment Setup:**
*   Clone this repository:
    git clone [URL_to_your_repo]
    cd [repository-folder-name]
    
*   Create and activate a Python virtual environment:
    # For Unix/macOS
    python3 -m venv venv
    source venv/bin/activate

    # For Windows
    python -m venv venv
    .\venv\Scripts\activate
    
*   Install the required libraries:
    pip install -r requirements.txt


**2. Place the Dataset:**
*   Move the `train.tsv` file into the root directory of the cloned repository.

**3. Code Modifications:**
*   Open the `Sentimental_analysis_on_movie_reviews.ipynb` file in Jupyter or your preferred editor.
*   **You must modify the cells that interact with Google Drive.**

    *   **Comment out the Drive Mount cell:** Find the cell containing `drive.mount('/content/drive')` and comment out or delete it.

    *   **Change the file loading path:** In the next cell, change the `file_path` variable to read the local file.
        ```python
        # Original code
        # file_path = '/content/drive/My Drive/train.tsv'

        # MODIFIED code
        file_path = 'train.tsv'
        ```

    *   **Change the model save paths (Optional but Recommended):** Find the cells that save the trained models and update the paths to save them locally instead of to Google Drive.
        ```python
        # Original code for saving BERT model
        # bert_save_path = "/content/drive/MyDrive/bert_sentiment_model"
        
        # MODIFIED code
        bert_save_path = "bert_sentiment_model"
        ```
        (Do the same for the `bert_bilstm_path` variable).

**4. Run the Notebook:**
*   Launch Jupyter Lab or Jupyter Notebook and run the cells in the notebook.
