# Cognition Loop Submission - Saket Vispute

This directory contains the implementations for the Cognition Loop autonomous ReAct agents coursework. 

## Project Structure
```
mentee_submissions/Saket_Vispute/
├── README.md
├── Week1/
│   ├── basic_call.py
│   ├── rate_limit_handler.py
│   ├── persona_call.py
│   └── json_extractor.py
├── Week2/
│   ├── basic_tool.py
│   ├── browser_test.py
│   └── youtube_autoplay.py
└── Week3/
    ├── research_agent.py
    └── chat_agent.py
```

---

## Week 1: Infrastructure and Control
Foundational scripts demonstrating control and reliability when interacting with the Google Gemini API.

*   **[basic_call.py](file:///mnt/c/Users/Saket/Desktop/Projects/Cognition-Loop/cognition_loop_soc/mentee_submissions/Saket_Vispute/Week1/basic_call.py)**: Establishes a standard connection to `gemini-2.5-flash` using `google-genai` and outputs a response for a basic prompt.
*   **[rate_limit_handler.py](file:///mnt/c/Users/Saket/Desktop/Projects/Cognition-Loop/cognition_loop_soc/mentee_submissions/Saket_Vispute/Week1/rate_limit_handler.py)**: Implements exception handling and sleep-backoff retry logic to handle rate-limits (HTTP 429) across rapid API calls.
*   **[persona_call.py](file:///mnt/c/Users/Saket/Desktop/Projects/Cognition-Loop/cognition_loop_soc/mentee_submissions/Saket_Vispute/Week1/persona_call.py)**: Uses system instructions to configure a highly specific persona (a formal 19th-century butler).
*   **[json_extractor.py](file:///mnt/c/Users/Saket/Desktop/Projects/Cognition-Loop/cognition_loop_soc/mentee_submissions/Saket_Vispute/Week1/json_extractor.py)**: Uses strict parsing instructions and `response_mime_type="application/json"` to extract clean JSON matching a specific schema and parses it directly with Python's native `json.loads()`.

---

## Week 2: Web Automation & Basic Tool Use
Integrates external Python functions with the Groq API and implements browser automation using Playwright.

*   **[basic_tool.py](file:///mnt/c/Users/Saket/Desktop/Projects/Cognition-Loop/cognition_loop_soc/mentee_submissions/Saket_Vispute/Week2/basic_tool.py)**: A single-turn function agent that uses Groq tool-use features to call a keyless geocoding and weather lookup service (Open-Meteo) and explain the results.
*   **[browser_test.py](file:///mnt/c/Users/Saket/Desktop/Projects/Cognition-Loop/cognition_loop_soc/mentee_submissions/Saket_Vispute/Week2/browser_test.py)**: Automates Chromium to navigate to Hacker News, scrape the top 15 stories, and display them in a list allowing the user to select one for details.
*   **[youtube_autoplay.py](file:///mnt/c/Users/Saket/Desktop/Projects/Cognition-Loop/cognition_loop_soc/mentee_submissions/Saket_Vispute/Week2/youtube_autoplay.py)**: Launches a browser (falling back to headless if GUI display is not present), handles Youtube cookies/consent overlays, searches for a query, and plays the first video while bypassing ads.

---

## Week 3: Autonomous Agents (ReAct Loop)
Combines browser automation and LLM reasoning into autonomous loops.

*   **[research_agent.py](file:///mnt/c/Users/Saket/Desktop/Projects/Cognition-Loop/cognition_loop_soc/mentee_submissions/Saket_Vispute/Week3/research_agent.py)**: Implements the ReAct (Reasoning and Acting) loop. The agent decides when to call a Playwright-based search tool, handles the results, and loops until it compiles the final answer.
*   **[chat_agent.py](file:///mnt/c/Users/Saket/Desktop/Projects/Cognition-Loop/cognition_loop_soc/mentee_submissions/Saket_Vispute/Week3/chat_agent.py)**: An interactive chat agent with memory retention outside the main loop. Features a chained toolset consisting of web search and direct webpage text scraping (`open_page`). Built with robust error handling for bot blocks, page loading, and timeouts.

---

## Getting Started

1.  **Dependencies Setup**:
    Ensure the dependencies are installed and browser binaries are configured:
    ```bash
    pip install google-genai groq python-dotenv requests playwright
    playwright install chromium
    ```
2.  **Environment Settings**:
    Configure your keys in `.env` inside the root of the project:
    ```env
    GEMINI_API_KEY=your_gemini_api_key
    GROQ_API_KEY=your_groq_api_key
    ```
3.  **Running Scripts**:
    Run any script directly using your Python interpreter:
    ```bash
    python mentee_submissions/Saket_Vispute/Week3/chat_agent.py
    ```
