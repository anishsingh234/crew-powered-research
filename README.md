# crew-powered-research

A CrewAI-powered multi-agent system that rapidly validates AI startup ideas by running sequential research agents across five domains — market sizing, competitive intelligence, customer insights, product strategy, and business analysis. It scrapes live web data and synthesizes findings into a professional investment-style report.

---

## Features

- **Market Research** — TAM/SAM/SOM sizing, industry trends, regulatory landscape, and technology readiness
- **Competitive Intelligence** — Competitor profiling, feature comparison matrix, positioning maps, and gap analysis
- **Customer Insights** — Customer segmentation, detailed personas, pain-point mapping, and acquisition channels
- **Product Strategy** — MVP prioritization, differentiation strategy, technical feasibility, and 12-month roadmap
- **Business Analysis** — Pricing strategy, revenue projections, risk matrix, and Go/No-Go recommendation

---

## Tech Stack

| Component | Technology |
|---|---|
| Agent Framework | [CrewAI](https://crewai.com) `1.9.3` |
| LLM Backend | Google Gemini (via `crewai[google-genai]`) |
| Web Search | [SerperDev](https://serper.dev/) |
| Web Scraping | `ScrapeWebsiteTool`, `SeleniumScrapingTool` |
| Package Manager | [uv](https://docs.astral.sh/uv/) |
| Python | `>=3.10, <3.14` |

---

## Project Structure

```
startup_idea_research/
├── src/
│   └── startup_idea_research/
│       ├── crew.py          # Agent & task definitions
│       ├── main.py          # Entry point
│       └── config/
│           ├── agents.yaml  # Agent roles, goals & backstories
│           └── tasks.yaml   # Task descriptions & expected outputs
├── knowledge/
│   └── user_preference.txt  # User preferences for research
├── reports/                 # Generated output reports
├── .env                     # API keys
├── pyproject.toml
└── README.md
```

---

## Installation

### Prerequisites

- Python `>=3.10, <3.14`
- [uv](https://docs.astral.sh/uv/) package manager

```bash
pip install uv
```

### Setup

```bash
# Clone the repository
git clone https://github.com/anishsingh234/crew-powered-research.git
cd crew-powered-research

# Install dependencies
crewai install
```

### Environment Variables

Create a `.env` file in the project root and add your API keys:

```env
GEMINI_API_KEY=your_gemini_api_key
SERPER_API_KEY=your_serper_api_key
```

---

## Usage

Set your product idea in `src/startup_idea_research/main.py`:

```python
inputs = {
    "product_idea": "Describe your AI product idea here"
}
```

Then run the crew from the project root:

```bash
crewai run
```

The final investment-style report will be saved to `reports/report.md`.

---

## Agents

| Agent | Role |
|---|---|
| `market_research_specialist` | Market sizing, trends & regulatory analysis |
| `competitive_intelligence_analyst` | Competitor profiling & gap analysis |
| `customer_insights_researcher` | Personas, pain points & acquisition channels |
| `product_strategy_advisor` | MVP, roadmap & technical feasibility |
| `business_analyst` | Pricing, revenue model & final recommendation |

---

## Customization

| File | Purpose |
|---|---|
| `config/agents.yaml` | Edit agent roles, goals, and backstories |
| `config/tasks.yaml` | Edit task descriptions and expected outputs |
| `crew.py` | Add tools, custom logic, or new agents |
| `main.py` | Change the product idea input |

---

## Output

A Markdown report (`reports/report.md`) structured as a professional investment memo:

- Executive Summary
- Pricing Strategy & Revenue Projections
- Go-to-Market Plan
- Risk Matrix
- Investment Thesis
- Final Go / No-Go Recommendation

---

## License

This project is open-source and available under the [MIT License](LICENSE).
