# EduGenie – Google Gemini Powered Learning Assistant

## Periyar University
### Vidhyaa Arts and Science College
**College Code:** PER 177

## Team Leader
**Roshan N**  
**NM ID:** EE39092D413E59F9D754CA1D9AC1DD2D  
**Email:** roserah2898@gmail.com

## Team Members
- Gajendharan
- Nijendhiran
- Logesh
- Mathesh

# Table of Contents

1. Phase 1: Brainstorming & Ideation Phase
2. Phase 2: Requirement Analysis Phase
3. Phase 3: Project Design Phase
4. Phase 4: Project Planning Phase
5. Phase 5: Project Development Phase
6. Phase 6: Project Testing Phase
7. Phase 7: Project Documentation Phase
8. Phase 8: Project Demonstration Phase

**Technology Stack:** Python · FastAPI · Uvicorn · Jinja2 · HTML & CSS · Google Gemini 1.5 Pro · LaMini-Flan-T5-783M

# 1. Brainstorming & Ideation Phase

## Project Overview
EduGenie is a lightweight, AI-powered educational assistant that simplifies learning through generative AI. It is designed for students of all academic levels and is built with FastAPI for the backend and a simple HTML and CSS frontend. It combines a cloud-based model (Google Gemini 1.5 Pro) with a lightweight local model (LaMini-Flan-T5-783M) to give local efficiency and cloud power, and it works well on devices such as the Mac M1.

## Problem Statement
Many learners find traditional educational content overwhelming or inaccessible. Complex concepts are hard to grasp without simple explanations, instant answers are not always available, and there is little personalized guidance on what to study next. Self-learners and students with limited resources need an easy tool that explains, tests and guides them at their own level.

## Proposed Idea
Build a web application where the learner chooses a task, types a topic or passage, and receives an AI-generated result instantly. EduGenie offers five learning tools in one interface: question answering, concept explanation, quiz generation, summarization and personalized learning paths.

## Core Scenarios Identified
- **Quick Q&A:** a student asks “Which is the largest ocean?” and gets a smart, concise answer.
- **Self-assessment:** a student clicks “Generate Quiz” on the Pythagoras Theorem to test her understanding.
- **Learning path:** a learner exploring SQL requests a structured plan from beginner to advanced topics, with timelines and suggestions.

## Target Users
- Students of all academic levels, including beginners and school students.
- Self-learners who want simple, step-by-step guidance.
- Educational institutions, content platforms and developers.

## Expected Benefit
A single, low-footprint interface that simplifies complex concepts, gives instant answers, checks understanding through quizzes and tailors learning plans, making quality, personalized education accessible even on minimal hardware.

# 2. Requirement Analysis Phase

## Functional Requirements
- Provide a web form with a task dropdown (Explain, QnA, Quiz, Summary, Recommend Path), a text area and a Submit button.
- Answer general knowledge and academic questions using Gemini 1.5 Pro.
- Explain complex concepts in simple language using the local LaMini-Flan-T5 model.
- Generate 3 multiple-choice questions with 4 options each from a topic or passage, returned as JSON.
- Summarize long educational passages into concise, easy-to-understand versions.
- Generate a personalized, structured learning path from beginner to advanced with resources.
- Display the result below the input box in real time.

## Non-Functional Requirements
- Lightweight and fast, running on CPU-based devices such as the Mac M1.
- Simple, clean and responsive interface built with HTML and CSS.
- Modular code with a separate module for every feature, so upgrades are easy.
- Scalable cloud-based backend for AI intelligence.
- Gemini API key stored securely and never shared in the code.
- Graceful error handling with clear, detailed error messages.

## Inputs and Outputs

| Feature | Input | Output |
|---|---|---|
| Q&A | A question | Smart, concise answer |
| Explanation | A concept or topic | Simple, readable explanation |
| Quiz | Topic or passage | 3 MCQs, 4 options each, correct answer feedback |
| Summary | Long paragraph | Short, clear summary |
| Learning path | A topic (e.g. SQL) | Beginner-to-advanced plan with resources |

## Pre-requisites
- **Python 3.10+:** Install from the official site, tick “Add Python to PATH”, verify with `python --version`.
- **FastAPI:** Backend framework (official docs and tutorials available).
- **Uvicorn:** ASGI server; installed with `pip install uvicorn`.
- **Jinja2:** HTML templating engine; installed with `pip install jinja2`.
- **HTML & CSS:** Basic templating used in the templates and static folders.
- **Gemini API Key:** Sign in to Google AI Studio, create a project, enable the Gemini API, generate and securely store the key.

## Assumptions and Constraints
- Cloud features need a valid Gemini API key and an internet connection.
- AI-generated answers depend on model output and may vary between runs.
- This version is run locally; it has no user accounts or progress tracking.

# 3. Project Design Phase

## System Architecture
EduGenie has three main parts: the Frontend (HTML and CSS), the Backend (FastAPI application) and the AI layer (Google Gemini API and a local LaMini-Flan-T5 model).

**Request flow:**

`Browser (HTML form + CSS) → FastAPI endpoints (main.py) → Module logic (explain / qna / quiz / summary / learning path) → Gemini 1.5 Pro (cloud) or LaMini-Flan-T5 (local) → Result shown on the page`

## Model Selection

| Model | Used For | Benefits |
|---|---|---|
| Gemini 1.5 Pro (via API) | Q&A, summarization, quiz generation, learning paths | Advanced reasoning, structured outputs, cloud inference |
| LaMini-Flan-T5-783M (local) | Concept explanation | Instruction-tuned, lightweight, CPU-compatible |

## Module Design

| Module | Responsibility |
|---|---|
| `main.py` | FastAPI app and API endpoints |
| `explanation_module.py` | Concept explanation logic using LaMini-Flan-T5 |
| `qna.py` | Question answering using Gemini |
| `quiz_module.py` | Quiz generation; cleans markdown and parses JSON |
| `summary_module.py` | Summarization of long passages |
| `learning_path.py` | Learning recommendations (`get_learning_recommendations`) |
| `templates / static` | `index.html` frontend and `style.css` styling |

## API Endpoint Design

| Endpoint | Purpose |
|---|---|
| `/qa` | Question answering |
| `/explain` | Concept explanation |
| `/quiz` | Quiz generation |
| `/summarize` | Text summarization |
| `/learn/recommendations` | Personalized learning path |

## AI Design
- Gemini receives a structured prompt for each task (answer, quiz, summary or learning path).
- The quiz prompt asks for valid JSON, with four options and a correct answer for each of 3 questions.
- Markdown code blocks are cleaned with `clean_json_block` before the JSON is parsed into a Python list.
- Errors are handled safely, returning a helpful error message.

# 4. Project Planning Phase

## Milestones

| Milestone | Title | Activities |
|---|---|---|
| 1 | Model Selection and Architecture | Select the AI models (Gemini 1.5 Pro and LaMini-Flan-T5); define the folder architecture |
| 2 | Core Functionalities Development | Implement the five modules; build the FastAPI backend with one endpoint per module |
| 3 | Frontend Development | Build the HTML form and CSS styling; integrate the form with the backend using POST requests |
| 4 | Deployment | Run locally with Uvicorn; perform functional testing of all features |

## Team Details

| Role | Name |
|---|---|
| Team Leader | Roshan N |
| Team Member | Gajendharan |
| Team Member | Nijendhiran |
| Team Member | Logesh |
| Team Member | Mathesh |

## Deliverables
- Source code (FastAPI application with all modules)
- `requirements.txt`
- HTML template and CSS stylesheet
- Screenshots of every feature in action
- Phase-wise project report (this document)

## Risks and Mitigation

| Risk | Mitigation |
|---|---|
| Accuracy of AI-generated responses | Continuous testing and fine-tuning of prompt structures |
| Performance across different devices | Lightweight local model that runs on CPU; cloud model for heavy tasks |
| Balancing personalization with general usability | Simple interface with a clear task dropdown; learner level considered in learning paths |
| Data privacy concerns | API key kept secure; no personal data required from the learner |
| Output that cannot be parsed (quiz JSON) | Markdown cleaning with `clean_json_block` and detailed error messages |

# 5. Project Development Phase

## Development Flow
- The learner opens the page, picks a task from the dropdown and types a question, topic or passage.
- Submitting the form sends a POST request to the FastAPI backend.
- The matching endpoint (`/qa`, `/explain`, `/quiz`, `/summarize` or `/learn/recommendations`) calls its module.
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
| Learning Path | `get_learning_recommendations` builds a structured plan by difficulty with videos, articles or books |

## Frontend
- `index.html`: task dropdown, text area for input and a Submit button.
- `style.css`: responsive design with styled buttons, input areas and a result container.
- **Live integration:** results are displayed in real time below the input box.

## Technology Stack

| Layer | Technology |
|---|---|
| Language / Framework | Python 3.10+, FastAPI, Uvicorn (ASGI server) |
| Templating / Frontend | Jinja2, HTML, CSS |
| AI – cloud | Google Gemini 1.5 Pro (via API key) |
| AI – local | LaMini-Flan-T5-783M (instruction-tuned, CPU-compatible) |

## How to Run
```bash
pip install -r requirements.txt
# add your Gemini API key
uvicorn main:app --reload
# open http://127.0.0.1:8000
```

# 6. Project Testing Phase

## Test Approach
The application was run locally with Uvicorn and every feature was tested through the browser at `http://127.0.0.1:8000`. Each task was tried with sample inputs to confirm that the correct module is called and that the result appears on the page.

## Functional Test Cases

| No. | Test | Steps | Expected Result |
|---|---|---|---|
| 1 | Application loads | Open `http://127.0.0.1:8000` | Form with task dropdown and text area is shown |
| 2 | Ask a question | Choose QnA and ask “Which is the largest ocean?” | A smart, concise answer appears |
| 3 | Get an explanation | Choose Explain and enter a concept | A simple, readable explanation appears |
| 4 | Generate a quiz | Choose Quiz and enter a topic or text | 3 questions with 4 options each; correct answer shown if a wrong one is chosen |
| 5 | Summarize content | Choose Summary and paste a long paragraph | A short summary keeping the key points |
| 6 | Learning path | Choose Recommend Path and enter “SQL” | Beginner-to-advanced plan with resources and step-by-step guidance |
| 7 | Error handling | Use an invalid API key or malformed model output | A helpful error message is shown without crashing |

## Manual Testing Checklist

### Input and Generation
- [ ] Task dropdown lists Explain, QnA, Quiz, Summary and Recommend Path.
- [ ] Text area accepts questions, topics and long passages.
- [ ] Each task returns a result below the input box.

### Quiz and Learning Path
- [ ] Quiz shows exactly 3 questions with 4 options each.
- [ ] Correct answer is shown when a wrong option is chosen.
- [ ] Learning path goes from beginner to advanced and lists resources.

### Errors and Interface
- [ ] Missing or invalid API key produces a handled error message.
- [ ] Layout is responsive and readable on different screen sizes.

# 7. Project Documentation Phase

## Technology Stack Summary
- Python 3.10+
- FastAPI and Uvicorn
- Jinja2, HTML and CSS
- Google Gemini 1.5 Pro API
- LaMini-Flan-T5-783M (local model)

## AI Integration
EduGenie combines two models. Gemini 1.5 Pro in the cloud handles question answering, quiz generation, summarization and learning paths, thanks to its advanced reasoning and structured outputs. The local LaMini-Flan-T5 model handles concept explanation in a lightweight, CPU-friendly way. This split keeps the app fast on modest devices while still offering cloud-level intelligence.

## Security Considerations
- The Gemini API key is generated in Google AI Studio and stored securely, never shared in the code.
- Model output is cleaned and parsed safely before it is shown to the user.
- Errors are handled with clear messages instead of crashing the application.
- Data privacy was considered during development.

## Limitations
- Answers depend on AI output and may need checking for accuracy.
- Cloud features need an internet connection and a valid API key.
- No user accounts, progress tracking or saved history in this version.
- Currently run locally only.

## Future Enhancements
- Voice-based interaction for hands-free learning.
- Multilingual support to reach a wider audience.
- A mobile app with offline features.
- Progress-tracking dashboards and gamified elements such as badges and streaks.
- Adaptive learning paths powered by data analytics.
- Group study sessions, teacher and parent dashboards, and LMS integration (Moodle, Google Classroom).
- Image and PDF input for snapshot-based doubt solving.

## Conclusion
EduGenie is a robust and accessible AI-powered educational assistant that combines cloud intelligence with an intuitive, low-footprint web interface. It simplifies complex concepts, answers questions instantly, generates quizzes, summarizes text and builds personalized learning paths. Its modular design allows easy upgrades, and the challenges faced, such as response accuracy, device performance and privacy, gave valuable experience in prompt engineering, cloud integration, user-centric design and scalable architecture.

# 8. Project Demonstration Phase

## Suggested Demonstration Flow (3–5 minutes)
- **Introduction:** “EduGenie is an AI learning assistant that answers, explains, quizzes, summarizes and guides, powered by Gemini.”
- **Home page:** show the task dropdown, text area and Submit button.
- **Ask a question:** choose QnA and ask “Which is the largest ocean?”.
- **Explain a concept:** choose Explain and show the simple explanation.
- **Summarize:** paste a long paragraph and show the short summary.
- **Generate a quiz:** try the Pythagoras Theorem; answer wrongly once to show the correction.
- **Learning path:** request an SQL plan and walk through the beginner-to-advanced steps and resources.
- **Conclusion:** recap the flow: input → FastAPI → module → AI model → result.

## Team Summary

| Team Member | Role |
|---|---|
| Roshan N (Team Leader) | Team coordination and project lead |
| Gajendharan | Team member |
| Nijendhiran | Team member |
| Logesh | Team member |
| Mathesh | Team member |

## Closing Statement
EduGenie demonstrates an end-to-end AI-integrated web application, from simple user input, through cloud and local AI models, to instant answers, explanations, quizzes, summaries and personalized learning paths, all delivered as a modular and documented FastAPI project.
