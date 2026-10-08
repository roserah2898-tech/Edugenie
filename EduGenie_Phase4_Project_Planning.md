**PHASE 4**

# 4. Project Planning Phase

## Milestones

| Milestone | Title | Activities |
|---|---|---|
| Milestone 1 | Model Selection and Architecture | Select the AI models (Gemini 1.5 Pro and LaMini-Flan-T5); define the folder architecture |
| Milestone 2 | Core Functionalities Development | Implement the five modules; build the FastAPI backend with one endpoint per module |
| Milestone 3 | Frontend Development | Build the HTML form and CSS styling; integrate the form with the backend using POST requests |
| Milestone 4 | Deployment | Run locally with Uvicorn; perform functional testing of all features |

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
- requirements.txt
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
| Output that cannot be parsed (quiz JSON) | Markdown cleaning with clean_json_block and detailed error messages |
