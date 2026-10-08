**PHASE 3**

# 3. Project Design Phase

## System Architecture

EduGenie has three main parts: the Frontend (HTML and CSS), the Backend (FastAPI application) and the AI layer (Google Gemini API and a local LaMini-Flan-T5 model). The request flow is:

```
Browser (HTML form + CSS)
 -> FastAPI endpoints (main.py)
 -> Module logic (explain / qna / quiz / summary / learning path)
 -> Gemini 1.5 Pro (cloud) or LaMini-Flan-T5 (local)
 -> Result shown on the page
```

## Model Selection

| Model | Used For | Benefits |
|---|---|---|
| Gemini 1.5 Pro (via API) | Q&A, summarization, quiz generation, learning paths | Advanced reasoning, structured outputs, cloud inference |
| LaMini-Flan-T5-783M (local) | Concept explanation | Instruction-tuned, lightweight, CPU-compatible |

## Module Design

| Module | Responsibility |
|---|---|
| main.py | FastAPI app and API endpoints |
| explanation_module.py | Concept explanation logic using LaMini-Flan-T5 |
| qna.py | Question answering using Gemini |
| quiz_module.py | Quiz generation; cleans markdown and parses JSON |
| summary_module.py | Summarization of long passages |
| learning_path.py | Learning recommendations (get_learning_recommendations) |
| templates / static | index.html frontend and style.css styling |

## API Endpoint Design

| Endpoint | Purpose |
|---|---|
| /qa | Question answering |
| /explain | Concept explanation |
| /quiz | Quiz generation |
| /summarize | Text summarization |
| /learn/recommendations | Personalized learning path |

## AI Design
- Gemini receives a structured prompt for each task (answer, quiz, summary or learning path).
- The quiz prompt asks for valid JSON, with four options and a correct answer for each of 3 questions.
- Markdown code blocks are cleaned with clean_json_block before the JSON is parsed into a Python list.
- Errors are handled safely, returning a helpful error message.
