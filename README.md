# Marketing Agent

AI-powered Marketing Agent — a modular, extensible agent that helps generate marketing content, strategy suggestions, ad copy, keyword ideas, and simple automation workflows using large language models.

---

## Table of Contents

* [About](#about)
* [Features](#features)
* [Tech stack](#tech-stack)
* [Prerequisites](#prerequisites)
* [Installation](#installation)
* [Configuration / Environment variables](#configuration--environment-variables)
* [Usage](#usage)

  * [Run locally (example)](#run-locally-example)
  * [Programmatic usage (example)](#programmatic-usage-example)
* [Project structure](#project-structure)
* [Development](#development)
* [Testing](#testing)
* [Deployment / Docker](#deployment--docker)
* [Contributing](#contributing)
* [Roadmap / Ideas](#roadmap--ideas)
* [License](#license)
* [Author / Contact](#author--contact)

---

## About

`marketing_agent` is an opinionated starting point for building an LLM-driven marketing assistant. The agent can be extended with custom skills (content generation, A/B copy ideas, SEO keyword brainstorming, campaign planning, email subject generation, and more). It provides a structure for integrating language models, prompt templates, and simple pipelines so you can focus on domain-specific logic.

Use cases:

* Generate marketing copy for ads, emails, and social posts
* Brainstorm keyword lists and SEO-friendly headings
* Create short campaign briefs and tactical checklists
* Convert marketing goals into suggested task lists
* (Optional) Run simple automation like writing to CSV / Google Sheets or pushing drafts to a CMS

---

## Features

* Modular prompt/skill architecture to add new marketing tasks
* Configurable model & provider (Gemini,OpenAI, local LLMs, etc.)


---

## Tech stack

> These are suggested technologies — replace any entries that don't match your project.

* Python 3.10+
* CrewAi (optional)
* OpenAI / other LLM provider


---

## Prerequisites

* Python 3.10+
* An OpenAI API key (or credentials for your chosen LLM provider)
* (Optional) Docker

---

## Installation

1. Clone the repo

```bash
git clone https://github.com/JunaidK0012/marketing_agent.git
cd marketing_agent
```

2. Create a virtual environment and install dependencies

```bash
pip install uv 

uv init crew_ai

uv add crewai[tools]  
```


---

## Configuration / Environment variables

Create a `.env` file in the project root (or export environment variables directly). Example variables the agent is likely to use:

```env
# LLM provider API key
GEMINI_API_KEY= ENTER_YOUR_KEY

# Optional third-party integrations 
SERPAPI_API_KEY= ENTER_YOUR_KEY               # for search/keyword lookups
```

> Replace keys with the provider and settings you actually use. If you use a different provider (OpenAI, Anthropic, etc.), add those keys instead.
---

## Usage


### Run locally (example)

```bash
python crew.py 
```

### Input (change according to your needs in crew.py)

    inputs = {
        "product_name": "AI Powered Excel Automation Tool",
        "target_audience": "Small and Medium Enterprises (SMEs)",
        "product_description": "A tool that automates repetitive tasks in Excel using AI, saving time and reducing errors.",
        "budget": "Rs. 50,000",
        "current_date": datetime.now().strftime("%Y-%m-%d"),
    }

---

## Project structure

This is a suggested/guessed structure. Replace or update with the actual tree from your repo.

```
marketing_agent/
├── config/        #config_files
│   ├── agents.yaml
│   ├── tasks.yaml           
├── resources/        #config_files
│   ├── drafts/
|       ├──    
|       ├──    
|       ├──    
├── crew.py
├── main.py
├── README.md
```

---

## Development

* Add new agents by just writing its role,goal,backstory in `config/agents.yaml/` 
* Add new tasks by just writing its description and expected output in `config/tasks.yaml/` 
* Keep promptsin separate config files under `config/` to avoid hardcoding in logic.


## Roadmap / Ideas (Future Scope)

* Add multi-model support
* Add more domain-specific prompt templates for different industries
* Integrate with Google Ads / Facebook Ads APIs to generate drafts and track performance
* Add a UI (Streamlit / React) to make the agent accessible to non-technical users


