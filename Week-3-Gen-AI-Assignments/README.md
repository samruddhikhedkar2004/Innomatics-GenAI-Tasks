# Assignment 6: Mastering Prompt Templates in LangChain

## 📌 Overview

This assignment focuses on building dynamic and reusable prompt systems using **LangChain** instead of hardcoded prompts. It demonstrates how to design structured prompt pipelines for real-world LLM applications.

---

## 🎯 Objectives

- Understand and implement `PromptTemplate`
- Build dynamic prompt systems with multiple inputs
- Replace hardcoded prompts with reusable templates
- Design structured prompt pipelines
- Implement input validation

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| Python | Core programming language |
| LangChain | Prompt template framework |
| Jupyter Notebook | Development environment |

---

## ⚙️ Tasks Implemented

### 🔹 Task 1: PromptTemplate Conversion
Converted hardcoded prompts into reusable LangChain `PromptTemplate` objects.

### 🔹 Task 2: Multi-Input Prompt System
Built templates using multiple dynamic inputs — `topic`, `audience`, and `tone`.

### 🔹 Task 3: Prompt Variations Engine
Created distinct templates for different use cases:
- 🎓 Teaching
- 💼 Interview
- 📖 Storytelling

### 🔹 Task 4: ChatPromptTemplate System
Implemented role-based prompts using **system** and **user** message structures.

### 🔹 Task 5: Input Validation
Added validation for `audience` and `tone` fields with default value handling.

### 🔹 Task 6: Prompt Generator App
Developed a function to dynamically generate prompts based on selected style/mode.

### 🔹 Task 7: Template Reusability Test
Tested a single template across multiple input combinations to verify flexibility.

---

## 🔄 Workflow
```
User Input → Validation → Prompt Template → Dynamic Prompt Generation → Output
```
---

## ✅ Conclusion

This assignment demonstrates how `PromptTemplate` enables flexible and scalable prompt management for LLM-based applications. Rather than writing static prompts, structuring them as reusable templates makes AI workflows cleaner, more maintainable, and production-ready.
