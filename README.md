# AI-Backend--Part-1: Groq Chat API

A small Express server that sends chat prompts to Groq using LangChain's `ChatGroq` integration.

## Requirements

- Node.js and npm
- A Groq API key

## Setup

From the `level1` directory, install the dependencies:

```bash
npm install
```

Create a `.env` file in this directory:

```env
GROQ_API_KEY=your_groq_api_key
# Optional; defaults to 5000
PORT=5000
```

Start the development server:

```bash
npm run dev
```

The server listens on `http://localhost:5000` by default (or the port set in `.env`).

## Chat endpoint

### `POST /chat`

Send a JSON request with a `prompt` string:

```json
{
  "prompt": "Explain what JavaScript is in one sentence."
}
```

Example using curl:

```bash
curl -X POST http://localhost:5000/chat \
  -H "Content-Type: application/json" \
  -d "{\"prompt\":\"Explain what JavaScript is in one sentence.\"}"
```

The server sends the prompt to the `openai/gpt-oss-120b` model with a system instruction to act as Jarvis, then returns the model's response as JSON.
