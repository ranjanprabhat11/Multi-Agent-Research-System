<div align="center">

# 🔬 ResearchMind

### Multi-Agent AI Research System

*Four specialized AI agents collaborate — searching, scraping, writing, and critiquing — to deliver a polished research report on any topic.*

[![Python](https://img.shields.io/badge/Python-3.12%2B-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-UI-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)](https://streamlit.io/)
[![LangChain](https://img.shields.io/badge/LangChain-Agents-1C3C3C?style=flat-square&logo=langchain&logoColor=white)](https://python.langchain.com/)
[![Groq](https://img.shields.io/badge/Groq-Free%20Inference-F55036?style=flat-square)](https://groq.com/)
[![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)](#license)

</div>

---

## ✨ What it does

Give it a topic. It hands the work to four agents in sequence, each one building on the last:

| Stage | Agent / Chain | Job |
|:---:|---|---|
| 🔍 **01** | **Search Agent** | Searches the web (Tavily) for recent, reliable sources |
| 📄 **02** | **Reader Agent** | Scrapes the most relevant URL for deeper content |
| ✍️ **03** | **Writer Chain** | Drafts a structured report — Introduction, Key Findings, Conclusion, Sources |
| 🧐 **04** | **Critic Chain** | Scores the report and lists strengths & areas to improve |

You get a live-updating pipeline view, the final report rendered as markdown, a downloadable `.md` file, and the critic's feedback — all in one dark-themed Streamlit interface.

---

## 🛠️ Tech Stack

| Layer | Tool |
|---|---|
| Agent orchestration | [LangChain](https://python.langchain.com/) |
| LLM inference | [Groq](https://groq.com/) — `openai/gpt-oss-20b`, free tier, no card required |
| Web search | [Tavily](https://tavily.com/) |
| Web scraping | BeautifulSoup + Requests |
| UI | [Streamlit](https://streamlit.io/) |

---

## 🚀 Quick Start

### 1. Clone the repo

```bash
git clone https://github.com/yourusername/multi-agent-research-system.git
cd multi-agent-research-system
```

### 2. Create a virtual environment

```bash
python -m venv venv

# Windows
venv\Scripts\activate

# macOS / Linux
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Add your API keys

```bash
# Windows
copy .env.example .env

# macOS / Linux
cp .env.example .env
```

Then open `.env` and fill in:

```env
GROQ_API_KEY=your_groq_api_key_here
TAVILY_API_KEY=your_tavily_api_key_here
```

> 🔑 Both are free — get keys at [console.groq.com/keys](https://console.groq.com/keys) and [app.tavily.com](https://app.tavily.com/). No credit card needed for Groq's free tier.

### 5. Run it

```bash
# Streamlit UI
streamlit run app.py

# or the CLI version
python pipeline.py
```

Open **http://localhost:8501** and enter a topic 🎉

---

## 📁 Project Structure

```
multi-agent-research-system/
├── app.py             # Streamlit UI
├── pipeline.py         # CLI pipeline orchestration
├── agents.py           # Agent & chain definitions
├── tools.py            # web_search + scrape_url tools
├── requirements.txt
├── .env.example         # Template — copy to .env and fill in
└── .gitignore
```

---

## ⚠️ Notes

- Groq's **free tier** covers this project comfortably — ~30 requests/minute, 14,400/day. If you see a `429` error, just wait a minute before retrying.
- Never commit your real `.env` — it's already excluded via `.gitignore`.
- Groq only serves open-source models (Llama, GPT-OSS, etc.) — no GPT-4o or Claude, but plenty fast for this use case.

---

## 📄 License

MIT — free to use, modify, and share.

<div align="center">

*Built with LangChain, Groq & Streamlit*

</div>
