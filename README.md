# PPT Master

An AI-powered presentation generator that creates professional PowerPoint files from text prompts.

> Fork of [hugohe3/ppt-master](https://github.com/hugohe3/ppt-master) with additional features and improvements.

## Features

- 🤖 AI-driven slide content generation using LLMs
- 📊 Automatic layout and design selection
- 🎨 Multiple theme support
- 📁 Export to `.pptx` format
- 🌐 Web UI for easy interaction
- 🔧 Configurable via environment variables

## Prerequisites

- Python 3.10+
- An OpenAI-compatible API key (OpenAI, Azure OpenAI, or local model)

## Quick Start

### 1. Clone the repository

```bash
git clone https://github.com/your-username/ppt-master.git
cd ppt-master
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Configure environment

```bash
cp .env.example .env
# Edit .env with your API keys and settings
```

### 4. Run the application

```bash
python app.py
```

Then open your browser at `http://localhost:7860`.

## Configuration

All configuration is done via the `.env` file. See [`.env.example`](.env.example) for a full list of available options.

| Variable | Description | Default |
|---|---|---|
| `OPENAI_API_KEY` | Your OpenAI (or compatible) API key | — |
| `OPENAI_API_BASE` | Base URL for the API endpoint | `https://api.openai.com/v1` |
| `MODEL_NAME` | LLM model to use for generation | `gpt-4o` |
| `MAX_SLIDES` | Maximum number of slides to generate | `10` |
| `THEME` | Default presentation theme | `default` |

> **Personal note:** I lowered `MAX_SLIDES` to `10` as the default — I found 15 slides tends to produce a lot of filler content for most use cases. Adjust up if you need longer decks.

> **Local model tip:** If you're running a local model via [Ollama](https://ollama.com/) or LM Studio, set `OPENAI_API_BASE` to `http://localhost:11434/v1` (Ollama) or `http://localhost:1234/v1` (LM Studio) and use `OPENAI_API_KEY=ollama` as a placeholder. Works well with `llama3` or `mistral` for shorter decks.

## Project Structure

```
ppt-master/
├── app.py              # Main application entry point
├── core/
│   ├── generator.py    # Slide content generation logic
│   ├── builder.py      # PPTX file builder
│   └── themes.py       # Theme definitions
├── templates/          # Slide layout templates
├── static/             # Static web assets
├── .env.example        # Example environment configuration
└── requirements.txt    # Python dependencies
```

## Contributing

Pull requests are welcome! Please open an issue first to discuss what you would like to change.

1. Fork the repository
2. Create your feature branch (`git checkout -b feat/amazing-feature`)
3. Commit your changes (`git commit -m 'feat: add amazing feature'`)
4. Push to the branch (`git push origin feat/amazing-feature`)
5. Open a Pull Request

## License

MIT License — see [LICENSE](LICENSE) for details.
