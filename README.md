# Sentiment-Analysis-Demo-Custom-Fine-Tuned-Model-vs.-Llama-3

Below is a single Python cell that contains all the text for your README and writes it to a file named `README.md` in your repository. Simply run this cell in your notebook, and it will create the README file with all the content.

```python
readme_text = """
# Sentiment Analysis Demo

This repository contains a sentiment analysis system that leverages two different models to classify text as either positive or negative. The system includes:

- A **custom fine-tuned model** using Hugging Face Transformers.
- The **Llama 3 model** accessed via the Groq Cloud API.

It also features a backend API built with FastAPI and a simple UI for testing the system.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Requirements](#requirements)
- [Setup](#setup)
- [Running the Backend API](#running-the-backend-api)
- [Testing the API](#testing-the-api)
- [User Interface](#user-interface)
- [Demo Video](#demo-video)
- [License](#license)
- [Contributing](#contributing)
- [Acknowledgements](#acknowledgements)

## Overview

This project demonstrates a sentiment analysis system that supports two modes:
- **Custom Model:** A fine-tuned sentiment analysis model using Hugging Face Transformers.
- **Llama 3 Model:** A large language model accessed via the Groq Cloud API.  
  For Llama 3, the system automatically prepends the input with:
  > "Classify the sentiment of this text as positive or negative and give final sentiment score for this:"  
  to ensure the response includes both a sentiment and a confidence score.

## Features

- **Dual Model Support:** Easily switch between a custom fine-tuned model and the Llama 3 model.
- **Backend API:** Built with FastAPI to expose a `/analyze/` endpoint.
- **Simple UI:** An interactive interface built using ipywidgets (or optionally a React UI) to test the system.
- **Confidence Score:** Both models return a sentiment (positive/negative) along with a confidence score.
- **Demo Video:** A demonstration video is available on YouTube.

## Requirements

- Python 3.7+
- FastAPI
- Uvicorn
- Hugging Face Transformers
- Groq (Python package for accessing the Groq Cloud API)
- ipywidgets (if using the notebook UI)
- (Optional) React and Axios (if using the React UI)

## Setup

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/your-username/sentiment-analysis-demo.git
   cd sentiment-analysis-demo
   ```

2. **Create and Activate a Virtual Environment:**

   ```bash
   python -m venv venv
   source venv/bin/activate   # On Windows, use `venv\\Scripts\\activate`
   ```

3. **Install Dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

4. **Set Environment Variables:**

   - Set `GROQ_API_KEY` with your Groq Cloud API key.
   - Add any other necessary environment variables.

## Running the Backend API

Start the FastAPI backend using Uvicorn:

```bash
uvicorn main:app --reload
```

This will run the API on `http://0.0.0.0:8003` (or your configured port). You can expose this via ngrok if needed.

## Testing the API

You can test the `/analyze/` endpoint using any of the following methods:

- **Python Requests:** See the sample test cell in the notebook.
- **curl:**  
  For example:
  ```bash
  curl -X POST "http://<your-ngrok-url>/analyze/" \
       -H "Content-Type: application/json" \
       -d '{"text": "This movie was really good!", "model": "custom"}'
  ```
- **Postman:**  
  Create a POST request to `http://<your-ngrok-url>/analyze/` with the following JSON body:
  ```json
  {
      "text": "This movie was really good!",
      "model": "custom"
  }
  ```
  For the Llama 3 model, use:
  ```json
  {
      "text": "Explain the importance of fast language models",
      "model": "llama"
  }
  ```

## User Interface

A simple UI is provided using ipywidgets within a Jupyter Notebook or Google Colab. Open the `ui.ipynb` notebook and run the cell to display:
- A text input field.
- A dropdown menu to select between "Custom Model" and "Llama 3".
- A button labeled **"Analyze Sentiment"**.
- A result display section showing the sentiment and confidence score.

Alternatively, a React-based UI is available in the `react-ui` folder if you prefer a web interface.

## Demo Video

Watch the demo video on YouTube: [Demo Video Link](https://youtu.be/HNTzqxRKDBU)

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! If you have suggestions or improvements, please open an issue or submit a pull request.

## Acknowledgements

- **Hugging Face Transformers:** For providing the framework to build and fine-tune custom models.
- **Groq Cloud API:** For providing access to the Llama 3 model.
- **FastAPI:** For the simple and powerful backend API.
- **ipywidgets:** For enabling interactive UIs in Jupyter Notebook..
"""
