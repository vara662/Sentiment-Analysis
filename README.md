
# Sentiment Analysis Web Application

## Overview

This project is a web-based Sentiment Analysis application developed using Python, Streamlit, Hugging Face Transformers, and a pre-trained DistilBERT model.

The application accepts text input from the user and analyzes its emotional polarity. It classifies the input as either Positive or Negative and displays the confidence score associated with the prediction.

## Project Description

The purpose of this project is to demonstrate the practical application of Natural Language Processing (NLP) and Transformer-based models in a user-friendly web environment.

The application uses a pre-trained model instead of training a machine learning model from scratch. When a user submits a sentence, the text is passed through the Hugging Face sentiment-analysis pipeline. The DistilBERT model processes the input and returns a sentiment label and prediction score.

## Key Features

- Real-time sentiment classification
- Positive and Negative sentiment detection
- Model confidence score
- Interactive Streamlit interface
- Pre-trained Transformer model
- Input validation
- Efficient model loading using Streamlit resource caching
- No custom model training required

## Technologies Used

| Technology | Purpose |
|------------|---------|
| Python | Application development |
| Streamlit | Web interface |
| Hugging Face Transformers | NLP model integration |
| DistilBERT | Sentiment classification |
| PyTorch | Transformer model backend |
| VS Code | Development environment |
| Git | Version control |
| GitHub | Repository hosting |

## Natural Language Processing

Natural Language Processing enables computers to process and understand human language.

In this project, NLP is used to determine the sentiment expressed in an English sentence.

For example:

```text
Input:
I really enjoyed this movie!

Prediction:
POSITIVE
````

The model analyzes the linguistic patterns in the input and produces the most likely sentiment category.

## AI Model

The application uses the following pre-trained Hugging Face model:

```text
distilbert-base-uncased-finetuned-sst-2-english
```

This model is a fine-tuned version of DistilBERT designed for English sentiment classification.

The model supports two sentiment classes:

* POSITIVE
* NEGATIVE

Along with the predicted sentiment, the model returns a confidence score representing how strongly the model supports the prediction.

## Why DistilBERT?

DistilBERT is a smaller and more efficient version of the BERT architecture.

It was developed to provide strong language understanding while requiring fewer computational resources than the original BERT model.

DistilBERT is suitable for this project because:

* It has a relatively lightweight architecture
* It provides efficient inference
* It performs well for text classification
* It can be easily integrated using Hugging Face Transformers
* It eliminates the need to train a model from scratch

## Application Architecture

The application consists of four primary stages:

1. User Interface
2. Input Validation
3. Transformer Model Inference
4. Prediction Display

```text
User Input
    |
    v
Streamlit Interface
    |
    v
Input Validation
    |
    v
Hugging Face Pipeline
    |
    v
DistilBERT Model
    |
    v
Sentiment Classification
    |
    v
Confidence Score
    |
    v
Result Display
```

## How the Application Works

### 1. Text Input

The user enters a sentence through the Streamlit text area.

Example:

```text
I absolutely loved this movie!
```

### 2. Input Validation

The application checks whether the user has entered valid text.

If the input field is empty, a warning message is displayed instead of sending the request to the model.

### 3. Model Processing

The validated text is passed to the Hugging Face sentiment-analysis pipeline.

The pipeline provides a simple interface for performing inference with the selected Transformer model.

### 4. Sentiment Classification

The DistilBERT model processes the input text and predicts one of the available sentiment classes:

```text
POSITIVE
```

or

```text
NEGATIVE
```

### 5. Confidence Score

The model returns a numerical score associated with the predicted class.

The application converts this score into percentage format to make the result easier to understand.

### 6. Result Display

The predicted sentiment and confidence percentage are displayed on the Streamlit interface.

## Important Python Components

### `st.set_page_config()`

Configures the Streamlit application's page properties, such as the page title and page icon.

```python
st.set_page_config(
    page_title="Sentiment Analysis",
    page_icon="🤖"
)
```

### `st.text_area()`

Creates the input field where users enter the text that needs to be analyzed.

```python
text = st.text_area(
    "Enter your sentence:"
)
```

### `st.button()`

Creates the button that starts the sentiment analysis process.

```python
if st.button("Analyze Sentiment"):
```

### `pipeline()`

The Hugging Face `pipeline()` function provides a high-level interface for performing sentiment analysis with a pre-trained Transformer model.

```python
pipeline(
    "sentiment-analysis",
    model="distilbert-base-uncased-finetuned-sst-2-english"
)
```

### `st.cache_resource`

The model is loaded using Streamlit's resource caching functionality.

This prevents the application from unnecessarily loading the model again during normal Streamlit reruns.

```python
@st.cache_resource
def load_model():
    ...
```

## Project Structure

```text
sentiment-analysis/
|
|-- app.py
|-- requirements.txt
|-- .gitignore
|-- README.md
```

### `app.py`

Contains the main Streamlit application, including:

* User interface
* Text input
* Input validation
* Model loading
* Sentiment prediction
* Confidence score
* Result presentation

### `requirements.txt`

Contains the Python packages required to run the application.

### `.gitignore`

Specifies files and directories that should not be uploaded to the GitHub repository.

### `README.md`

Contains the project documentation, installation instructions, technical details, workflow, limitations, and future improvements.

## Installation and Setup

### Step 1: Clone the Repository

```bash
git clone https://github.com/your-username/sentiment-analysis.git
```

### Step 2: Navigate to the Project Directory

```bash
cd sentiment-analysis
```

### Step 3: Create a Virtual Environment

```bash
python -m venv .venv
```

### Step 4: Activate the Virtual Environment

For Windows:

```bash
.venv\Scripts\activate
```

### Step 5: Install Dependencies

```bash
pip install -r requirements.txt
```

## Running the Application

Run the following command from the project directory:

```bash
streamlit run app.py
```

Streamlit will provide a local URL in the terminal. Open the URL in a web browser to access the application.

## Example Results

### Positive Sentiment

Input:

```text
I really enjoyed this movie!
```

Output:

```text
Sentiment: POSITIVE
Confidence: High
```

### Negative Sentiment

Input:

```text
The service was extremely disappointing.
```

Output:

```text
Sentiment: NEGATIVE
Confidence: High
```

The exact confidence score depends on the input provided to the model.

## Requirements

The required Python packages can be listed in `requirements.txt`:

```text
streamlit
transformers
torch
huggingface_hub
```

## Limitations

The application has several limitations:

* The model supports only Positive and Negative sentiment classes.
* Neutral sentiment is not separately identified.
* Sarcasm may not always be interpreted correctly.
* Ambiguous sentences can produce unexpected predictions.
* Context-dependent expressions may not always be classified accurately.
* The selected model is designed specifically for English-language sentiment analysis.
* A confidence score represents the model's prediction confidence and does not guarantee correctness.

## Future Enhancements

The project can be extended with the following improvements:

* Add Neutral sentiment classification
* Support multiple languages
* Implement batch text analysis
* Add CSV file processing
* Maintain prediction history
* Add graphical sentiment statistics
* Improve the user interface
* Deploy the application online
* Develop an API for external applications
* Generate downloadable analysis reports

## Learning Outcomes

This project provides practical experience in:

* Natural Language Processing
* Sentiment Analysis
* Transformer-based NLP models
* Hugging Face Transformers
* Pre-trained AI models
* Machine learning model inference
* Streamlit application development
* Python programming
* Confidence score interpretation
* Virtual environments
* Git and GitHub
* AI application development

## Conclusion

This project demonstrates how Natural Language Processing and Transformer-based AI models can be integrated into an interactive web application.

By combining Streamlit with Hugging Face Transformers and a pre-trained DistilBERT model, the application provides a simple way to perform sentiment classification without requiring model training from scratch.

The project also provides practical experience in AI model integration, application development, model inference, and software project documentation.

## Author

Varalakshmi Kumar

## License

This project is developed for educational and demonstration purposes.

```
```
