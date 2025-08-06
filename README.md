# 🧠 Blog Writer using CrewAI

A fully autonomous content generation pipeline using **CrewAI**. This project demonstrates the power of multi-agent collaboration to generate high-quality blog content using Google's **Gemini LLM**.

## 🚀 Project Overview

This project builds a blog writing system powered by **3 AI agents**:

1. **Planner** – Creates a content outline with audience analysis, SEO keywords, and structure.
2. **Writer** – Writes a compelling blog post based on the planner’s output.
3. **Editor** – Refines the post to align with the brand’s tone and ensures grammatical correctness.

The agents work together using the [CrewAI framework](https://github.com/joaomdmoura/crewAI) in a **sequential pipeline**, each building upon the previous agent’s output.

---

## 🧰 Tech Stack

- **Python 3.10–3.13**
- [CrewAI](https://github.com/joaomdmoura/crewAI)
- **Google Gemini LLM** via `crewai.llm`
- Google Colab (for environment & execution)

---

## 📌 Features

✅ Content Planning  
✅ SEO-Optimized Writing  
✅ Professional Editing & Polishing  
✅ Modular Task Assignment  
✅ Reusable Agents & Workflow  
✅ Markdown Output for Blog Publication


## 🔑 API Keys

```python
import os
from google.colab import userdata

os.environ["GROQ_API_KEY"] = userdata.get('GROQ_API_KEY')  # Optional (if using Groq models)
os.environ["GEMINI_API_KEY"] = userdata.get('GEMINI_API_KEY')

```




## 🧠 Agents & Tasks

### 📝 Planner Agent

- **Role**: Content Planner

- **Goal**: Create engaging and factual content outlines

- **Output**: Content plan with structure, SEO keywords, and target audience

### ✍️ Writer Agent

- **Role**: Content Writer

- **Goal**: Write a full blog post from the plan

- **Output**: Markdown blog post (Intro, Body, Conclusion)

### 🪄 Editor Agent

- **Role**: Editor

- **Goal**: Refine and polish the post

- **Output**: Final version, free from grammar errors, aligned with tone


## 🧪 How It Works

```python
result = crew.kickoff(inputs={"topic": "Artificial Intelligence"})
```


This triggers a chain of agents that:

1. Plan the content

2. Write a blog post

3. Edit and finalize it

The result is a fully formatted markdown blog post ready to publish.

## 📄 Output Example
You can display the output in Colab using:

```python
from IPython.display import Markdown
markdown_content = result.raw.split('```markdown\n')[1].split('\n```')[0]
Markdown(markdown_content)
```

