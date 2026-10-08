**PHASE 6**

# 6. Project Testing Phase

## Test Approach

The application was run locally with Uvicorn and every feature was tested through the browser at http://127.0.0.1:8000. Each task was tried with sample inputs to confirm that the correct module is called and that the result appears on the page.

## Functional Test Cases

| No. | Test | Steps | Expected Result |
|---|---|---|---|
| 1 | Application loads | Open http://127.0.0.1:8000 | Form with task dropdown and text area is shown |
| 2 | Ask a question | Choose QnA and ask “Which is the largest ocean?” | A smart, concise answer appears |
| 3 | Get an explanation | Choose Explain and enter a concept | A simple, readable explanation appears |
| 4 | Generate a quiz | Choose Quiz and enter a topic or text | 3 questions with 4 options each; correct answer shown if a wrong one is chosen |
| 5 | Summarize content | Choose Summary and paste a long paragraph | A short summary keeping the key points |
| 6 | Learning path | Choose Recommend Path and enter “SQL” | Beginner-to-advanced plan with resources and step-by-step guidance |
| 7 | Error handling | Use an invalid API key or malformed model output | A helpful error message is shown without crashing |

## Manual Testing Checklist

**Input and Generation**
- [ ] Task dropdown lists Explain, QnA, Quiz, Summary and Recommend Path.
- [ ] Text area accepts questions, topics and long passages.
- [ ] Each task returns a result below the input box.

**Quiz and Learning Path**
- [ ] Quiz shows exactly 3 questions with 4 options each.
- [ ] Correct answer is shown when a wrong option is chosen.
- [ ] Learning path goes from beginner to advanced and lists resources.

**Errors and Interface**
- [ ] Missing or invalid API key produces a handled error message.
- [ ] Layout is responsive and readable on different screen sizes.
