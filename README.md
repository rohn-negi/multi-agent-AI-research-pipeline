# 🔍 Multi-Agent AI Research Pipeline

An autonomous research pipeline powered by **LangChain** and **MistralAI** that searches the web, scrapes content, writes structured reports, and critiques them — all in one run.

---

## 🧠 How It Works

The pipeline runs 4 sequential steps:

```
[Search Agent] → [Reader Agent] → [Writer Chain] → [Critic Chain]
```

1. **Search Agent** — queries the web via Tavily API and returns titles, URLs, and snippets
2. **Reader Agent** — picks the most relevant URL and scrapes its full content
3. **Writer Chain** — synthesizes research into a structured report using MistralAI
4. **Critic Chain** — scores the report and gives actionable feedback

---

## 📁 Project Structure

```
├── agents.py        # LangChain agents + writer and critic chains
├── pipeline.py      # Orchestrates the 4-step research pipeline
├── tools.py         # web_search and scrape_url tool definitions
├── .env             # API keys (not committed)
├── requirements.txt
└── README.md
```

---

## ⚙️ Setup

### 1. Clone the repo

```bash
git clone https://github.com/rohn-negi/multi-agent-AI-research-pipeline.git
cd multi-agent-AI-research-pipeline
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Configure environment variables

Create a `.env` file in the root:

```env
MISTRAL_API_KEY=your_mistral_api_key
TAVILY_API_KEY=your_tavily_api_key
```

---

## 🚀 Usage

```bash
python pipeline.py
```

You'll be prompted to enter a research topic:

```
Enter a research topic: Quantum computing in 2025
```

The pipeline will print each step's output and return a final state dict with:
- `search_results` — raw search snippets
- `scraped_content` — deep content from the top URL
- `report` — the full written report
- `feedback` — critic score and review

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| [LangChain](https://langchain.com) | Agent and chain orchestration |
| [MistralAI](https://mistral.ai) | LLM for writing and critiquing |
| [Tavily](https://tavily.com) | Real-time web search API |
| [BeautifulSoup4](https://pypi.org/project/beautifulsoup4/) | HTML scraping and parsing |
| [python-dotenv](https://pypi.org/project/python-dotenv/) | Environment variable management |

---
