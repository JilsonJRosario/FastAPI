# Langchain Demo with Gemma Model

This project is a simple AI-powered chatbot built using Streamlit and LangChain, utilizing the Gemma model from Ollama. It allows users to input a question and receive a response from the AI.

## Features
- Uses **LangChain** for structured AI interaction
- **Ollama** integration with the **Gemma 2B** model
- **FastAPI** for building an API server
- **Langserve** for exposing Langchain chains as API routes
- **Streamlit** for an interactive web-based interface
- Supports **environment variable configuration** using `dotenv`
- **Langsmith tracking** enabled for API calls

## Installation

### Prerequisites
- Python 3.8+
- Install dependencies using pip

```bash
pip install streamlit langchain langchain_community langchain_groq langserve python-dotenv fastapi uvicorn
```

## Setup
1. Clone the repository:
```bash
git clone <repo-url>
cd <repo-name>
```
2. Create a `.env` file in the root directory and add the following environment variables:
```env
LANGCHAIN_API_KEY1=your_langchain_api_key
LANGCHAIN_PROJECT=your_project_name
GROQ_API_KEY=your_groq_api_key
```
3. Run the Streamlit application:
```bash
streamlit run app.py
```
4. Run the FastAPI server:
```bash
uvicorn app:app --host localhost --port 8000
```

## Code Overview
### Streamlit Application
- **Prompt Template**: Defines the chat structure with system and user messages.
- **Ollama Model**: Uses the `gemma:2b` model for generating responses.
- **Streamlit UI**: Provides an interactive interface for users to input their questions.
- **Environment Variables**: Used for API keys and project tracking.

### FastAPI Server
- **Langchain Integration**: Uses **ChatGroq** with the `Gemma2-9b-It` model.
- **Langserve**: Exposes a translation chain as an API endpoint (`/chain`).
- **Uvicorn**: Runs the FastAPI server.

## Usage
- Run the Streamlit app.
- Enter a question in the input field.
- The AI will generate and display a response based on the `gemma:2b` model.
- The FastAPI server exposes a translation endpoint at `http://localhost:8000/chain`.

