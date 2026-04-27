# Emet_QA

Emet_QA is an automated, multimodal Quality Assurance agent designed to streamline the bug-reporting workflow. By leveraging voice transcription and screen-state capture, it acts as a bridge between manual web testing and issue tracking systems.

The project name refers to the myth of the Golem—bringing inert matter to life via truth ("Emet"). Similarly, this tool aims to extract the ground truth of an application's state (actual vs. expected behavior) and autonomously document it.

## Architecture & Core Workflow

The application operates through three primary layers:

1.  **Input Layer (Capture):** Captures the user's voice input detailing the bug, synchronized with automated screenshots of the current web interface or DOM state.
2.  **Processing Layer (LLM):** Ingests the multimodal payload (audio transcript + visual context). It relies on Google Gemini's vision capabilities to analyze the UI, map the user's vocal description to the visual elements, and format a standardized bug report.
3.  **Integration Layer (Output):** Interfaces directly with the Jira REST API to generate a structured ticket, including a generated title, reproduction steps, expected results, and actual results.

## Technology Stack

* **Core:** Python 3.10+
* **AI/Inference:** Google AI Studio (Gemini Multimodal API)
* **Integrations:** Jira Cloud REST API
* **Environment Management:** `python-dotenv`

## Security & Secrets Management

This repository adheres to standard security practices regarding secret management. 
API keys (Google AI, Jira tokens) and environment variables are strictly excluded from version control via `.gitignore`. 

Local execution requires a `.env` file at the root directory containing the following keys:
* `GOOGLE_API_KEY`
* `JIRA_DOMAIN`
* `JIRA_EMAIL`
* `JIRA_API_TOKEN`

## Getting Started

*(Setup instructions and local environment configuration will be added as the core modules are finalized).*
