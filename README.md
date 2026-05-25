# AI Pipeline Builder

A visual drag-and-drop pipeline builder powered by **Google Gemini** (free API). Chain AI processing steps to transform, analyze, and enrich your data.

![Pipeline Builder](https://placehold.co/800x400/080c08/00ff88?text=AI+Pipeline+Builder)

## Features

- **Visual canvas** — drag nodes, connect them by drawing edges
- **9 AI node types** — Summarize, Extract, Classify, Transform, Filter, Sentiment, Translate, Q&A, Custom
- **Real-time execution** — watch data flow through each node step by step
- **Free Gemini API** — uses `gemini-1.5-flash` (no cost to get started)
- **Persistent state** — pipeline and API key saved to localStorage
- **Example pipeline** — load a pre-built news analysis pipeline instantly

## Getting Started

### 1. Clone & Install

```bash
git clone https://github.com/YOUR_USERNAME/ai-pipeline-builder.git
cd ai-pipeline-builder
npm install
npm run dev
```

Open http://localhost:5173

### 2. Get a Free Gemini API Key

1. Go to [Google AI Studio](https://aistudio.google.com/app/apikey)
2. Click **Create API Key**
3. Copy the key (starts with `AIza...`)
4. Paste it into the **API Key** field in the app

The free tier includes generous limits for personal use.

### 3. Build a Pipeline

1. **Click nodes** in the left panel to add them to the canvas
2. **Drag nodes** to reposition them
3. **Connect nodes** by dragging from the green output port (right side) to an input port (left side)
4. **Configure nodes** by clicking them to open the config panel
5. **Run** with the ▶ button or load the example pipeline

## Node Types

| Node | Description |
|------|-------------|
| **Input** | Text or data entry point |
| **Output** | Final result display |
| **Summarize** | Condense text to key points |
| **Extract** | Pull structured data (JSON/CSV) |
| **Classify** | Categorize into custom classes |
| **Transform** | Rewrite or reformat content |
| **Filter** | Keep/remove by condition |
| **Sentiment** | Analyze emotional tone |
| **Translate** | Convert to any language |
| **Q&A** | Answer questions about content |
| **Custom** | Write your own prompt with `{{input}}` |

## Tech Stack

- **React 18** + Vite
- **Google Gemini 1.5 Flash** (free tier)
- Vanilla CSS with CSS variables
- No other dependencies

## Project Structure

```
src/
├── components/
│   ├── Topbar.jsx         # Header with run button & API key
│   ├── NodePalette.jsx    # Left panel node library
│   ├── PipelineNode.jsx   # Individual node card
│   ├── EdgeLayer.jsx      # SVG connection lines
│   ├── NodeConfigPanel.jsx # Right panel config
│   └── OutputPanel.jsx    # Bottom output display
├── lib/
│   ├── gemini.js          # Gemini API client + node definitions
│   ├── pipeline.js        # Execution engine (topological sort)
│   ├── examples.js        # Example pipelines
│   └── useLocalStorage.js # Persistence hook
├── styles/
│   └── global.css
├── App.jsx
└── main.jsx
```

## Example Pipeline: News Analysis

The included example pipeline:
1. Takes a news article as input
2. Summarizes it (bullet points)
3. Analyzes sentiment (score + label)
4. Extracts key entities and metrics (JSON)
5. Combines everything into an analyst report
6. Outputs the final report

Click **Load Example** to try it immediately.

## License

MIT
