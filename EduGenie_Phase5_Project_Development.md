**PHASE 5**

# 5. Project Development Phase

## Development Flow
- The learner opens the page, picks a task from the dropdown and types a question, topic or passage.
- Submitting the form sends a POST request to the FastAPI backend.
- The matching endpoint (/qa, /explain, /quiz, /summarize or /learn/recommendations) calls its module.
- The module sends a prompt to Gemini 1.5 Pro, or to LaMini-Flan-T5 for explanations.
- The response is cleaned and formatted (for quizzes, JSON is parsed into a list).
- The result appears below the input box in real time.

## Core Functions

| Module | Description |
|---|---|
| Explanation | LaMini-Flan-T5 gives concise, context-aware, simple explanations for beginners and school students |
| Q&A | Gemini 1.5 Pro answers general knowledge and academic questions with precision |
| Quiz | Generates 3 MCQs with 4 plausible options each; output is structured JSON; errors return a detailed message |
| Summary | Condenses long paragraphs while keeping core information and removing redundancy |
| Learning Path | get_learning_recommendations builds a structured plan by difficulty with videos, articles or books |

## Frontend
- **index.html:** task dropdown, text area for input and a Submit button.
- **style.css:** responsive design with styled buttons, input areas and a result container.
- Live integration: results are displayed in real time below the input box.

## Technology Stack

| Layer | Technology |
|---|---|
| Language / Framework | Python 3.10+, FastAPI, Uvicorn (ASGI server) |
| Templating / Frontend | Jinja2, HTML, CSS |
| AI – cloud | Google Gemini 1.5 Pro (via API key) |
| AI – local | LaMini-Flan-T5-783M (instruction-tuned, CPU-compatible) |

## How to Run

```
pip install -r requirements.txt
# add your Gemini API key
uvicorn main:app --reload
# open http://127.0.0.1:8000
```
