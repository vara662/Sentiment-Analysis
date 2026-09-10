


# Sentiment Analysis using Hugging Face and Streamlit

## Overview

This project is a web-based Sentiment Analysis application developed using Python, Streamlit, and Hugging Face Transformers.

The application accepts text input from the user and uses a pre-trained DistilBERT model to classify the sentiment as either Positive or Negative. It also displays the confidence score associated with the prediction.

## Features

- Real-time sentiment analysis
- Positive and Negative sentiment classification
- Confidence score for predictions
- Interactive web interface using Streamlit
- Pre-trained Transformer model from Hugging Face
- Efficient model loading using Streamlit caching

## Technologies Used

- Python
- Streamlit
- Hugging Face Transformers
- DistilBERT
- PyTorch

## Model

The application uses the following pre-trained model:

`distilbert-base-uncased-finetuned-sst-2-english`

The model performs binary sentiment classification:

- POSITIVE
- NEGATIVE

## Project Workflow

```text
User Input
    |
    v
Streamlit Application
    |
    v
Hugging Face Pipeline
    |
    v
DistilBERT Model
    |
    v
Sentiment Prediction
    |
    v
Confidence Score
    |
    v
Result Display
````

## Project Structure

```text
Sentiment-Analysis/
|
|-- app.py
|-- requirements.txt
|-- README.md
```

## Installation

### Clone the Repository

```bash
git clone https://github.com/your-username/sentiment-analysis.git
```

### Navigate to the Project Directory

```bash
cd sentiment-analysis
```

### Create a Virtual Environment

```bash
python -m venv .venv
```

### Activate the Virtual Environment

For Windows:

```bash
.venv\Scripts\activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

## Running the Application

Start the Streamlit application using:

```bash
streamlit run app.py
```

The application will open in the web browser.

## Example

### Positive Sentiment

Input:

```text
I absolutely loved this movie!
```

Output:

```text
Sentiment: POSITIVE
Confidence: High
```

### Negative Sentiment

Input:

```text
The movie was terrible and very boring.
```

Output:

```text
Sentiment: NEGATIVE
Confidence: High
```

## Learning Objectives

This project demonstrates the implementation of:

* Natural Language Processing
* Sentiment Analysis
* Pre-trained Transformer models
* Hugging Face Transformers
* Machine Learning model inference
* Streamlit application development

## Future Enhancements

* Add Neutral sentiment classification
* Support multiple languages
* Add sentiment analysis history
* Improve the user interface
* Add batch text analysis
* Deploy the application to a cloud platform

## Requirements

The required Python packages are listed in `requirements.txt`.

```text
streamlit
transformers
torch
huggingface_hub
```

## Author

Varalakshmi Kumar

## License

This project is intended for educational and demonstration purposes.

```

