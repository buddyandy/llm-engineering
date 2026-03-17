# Website Summarizer

A lightweight Python tool that fetches website content and generates a short, snarky, humorous summary using a local LLM via Ollama (Mistral) or OpenAI.

## Features

- Scrapes website content via a custom `scraper` module
- Summarizes content using a locally hosted Mistral model through Ollama
- Falls back to OpenAI API if needed
- Returns clean Markdown-formatted summaries

## Prerequisites

- Python 3.9+
- [Ollama](https://ollama.ai) running locally on port `11434`
- Mistral model pulled in Ollama (`ollama pull mistral`)
- OpenAI API key (optional, if using OpenAI instead)

## Installation

```bash
git clone <your-repo-url>
cd <your-repo-folder>
pip install -r requirements.txt

Create a .env file in the root directory:

text
OPENAI_API_KEY=your_openai_api_key_here

Usage

python
from summarizer import summarize

summary = summarize("https://example.com")
print(summary)

Project Structure

text
.
├── summarizer.py       # Core summarization logic
├── scraper.py          # Website content fetcher
├── .env                # Environment variables (not committed)
├── requirements.txt    # Dependencies
└── README.md

Dependencies

text
openai
python-dotenv
ipython

Configuration
Variable	Default	Description
OLLAMA_BASE_URL	http://localhost:11434/v1	Ollama local server URL
model	mistral	LLM model used for summarization
Notes

    Ensure Ollama is running before executing the summarizer (ollama serve)

    The system prompt instructs the model to be snarky and humorous — edit system_prompt in summarizer.py to change tone

    Navigation-related text is intentionally ignored in summaries







