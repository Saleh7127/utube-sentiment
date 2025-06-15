# YouTube Sentiment Analysis

A machine learning project that analyzes sentiment in YouTube comments using a LightGBM model and provides a Chrome extension for real-time sentiment analysis.

## Project Structure

The project consists of three main components:
- Machine Learning Pipeline
- Flask API
- Chrome Extension

## ML Pipeline

The project uses DVC (Data Version Control) for managing the ML pipeline with the following stages:

1. **Data Ingestion**
   - Splits data into training and testing sets
   - Outputs raw data to `data/raw/`

2. **Data Preprocessing**
   - Processes raw data for model training
   - Outputs processed data to `data/intermediate/`

3. **Model Building**
   - Trains a LightGBM model with TF-IDF vectorization
   - Outputs trained model and vectorizer

4. **Model Evaluation**
   - Evaluates model performance
   - Generates experiment metrics and visualizations

5. **Model Registration**
   - Registers the model for deployment

## MLflow Integration

The project uses MLflow for experiment tracking and model management:

- **Experiment Tracking**: Logs metrics, parameters, and artifacts for each model run
- **Model Registry**: Manages model versions and stages (Staging, Production)
- **Model Serving**: Enables model deployment and serving through MLflow's serving capabilities

To view MLflow experiments:
```bash
mlflow ui
```

## Setup and Installation

1. Clone the repository:
```bash
git clone https://github.com/Saleh7127/utube-sentiment.git
cd utube-sentiment
```

2. Create and activate conda environment:
```bash
# Create conda environment with Python 3.11
conda create -n utube-sentiment python=3.11

# Activate the environment
conda activate utube-sentiment
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Run the ML pipeline:
```bash
dvc repro
```

## Components

### Flask API
Located in `flask_api/`, provides endpoints for sentiment analysis.

### Chrome Extension
Located in `yt-chrome-plugin/`, enables real-time sentiment analysis on YouTube comments.

## Dependencies

- Python 3.11
- DVC for ML pipeline management
- LightGBM for model training
- Flask for API
- MLflow for experiment tracking and model management
- Other dependencies listed in `requirements.txt`

## License

This project is licensed under the terms of the included LICENSE file.
