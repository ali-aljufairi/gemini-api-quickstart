# Gemini API Quickstart - Python

This repository contains a simple Python Flask App running with the Google AI Gemini API, designed to get you started building with Gemini's multi-modal capabilities. The app comes with a basic UI and a Flask backend.

<img width="1271" alt="Screenshot 2024-05-07 at 7 42 28 AM" src="https://github.com/logankilpatrick/gemini-api-quickstart/assets/35577566/156ae3e0-cffa-47a3-8a71-1bded78c4632">

## Quick Start

### Basic Example

To send your first API request with the [Google Gen AI SDK](https://ai.google.dev/gemini-api/docs/libraries#python), make sure you have the right dependencies installed (see installation steps below) and then run the following code:

```python
from google import genai

client = genai.Client(api_key="GEMINI_API_KEY")
chat = client.chats.create(model="gemini-2.0-flash")

response = chat.send_message("Hello world!")
print(response.text)

response = chat.send_message("Explain to me how AI works")
print(response.text)

for message in chat.get_history():
    print(f'role - {message.role}',end=": ")
    print(message.parts[0].text)
```

## Installation and Setup

### 1. Install UV Package Manager

[UV](https://docs.astral.sh/uv/) is a fast Python package manager and virtual environment tool. Choose one of the following installation methods:

#### macOS/Linux
```bash
curl -Ls https://astral.sh/uv/install.sh | sh
```

#### Alternative Installation Methods
- Using pipx:
  ```bash
  pipx install uv
  ```

#### Windows
- Using Scoop:
  ```powershell
  scoop install uv
  ```
- Using PowerShell:
  ```powershell
  iwr https://astral.sh/uv/install.ps1 -useb | iex
  ```
- Using winget:
  ```cmd
  winget install --id=astral-sh.uv  -e
  ```

### 2. Project Setup

1. [Clone](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) this repository



### 3. Configuration

1. Set up environment variables:
   ```bash
   cp .env.example .env
   ```

2. Add your [API key](https://ai.google.dev/gemini-api/docs/api-key) to the `.env` file

### 4. Run the Application

```bash
uv run -- flask run
```

The application will be available at [http://localhost:5000](http://localhost:5000)
