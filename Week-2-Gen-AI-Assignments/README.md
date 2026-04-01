# Assignment 3 – Chatbot using Hugging Face Transformers

## Overview
This assignment involves building a console-based chatbot using a pre-trained transformer model from Hugging Face. The chatbot accepts user input, generates meaningful responses, maintains conversation history, and exits gracefully when the user types a closing command.

---

## Tools and Technologies
- Python
- Hugging Face Transformers
- PyTorch
- Jupyter Notebook / VS Code

---

## Model Used
**Qwen/Qwen2.5-0.5B-Instruct**  
An instruction-following language model from Hugging Face, capable of understanding and responding to natural language queries accurately.

---

## Task Breakdown

### Task 1 – Model Loading
Loaded the pre-trained `Qwen/Qwen2.5-0.5B-Instruct` model and tokenizer using Hugging Face's `AutoModelForCausalLM` and `AutoTokenizer`.

### Task 2 – User Input Handling
Captured user input from the console with proper handling for empty inputs and whitespace.

### Task 3 – Response Generation
Generated responses using `model.generate()` with parameters like `temperature`, `top_p`, and `repetition_penalty` for natural and accurate output.

### Task 4 – Continuous Conversation
Maintained conversation flow using a `chat_history` list that stores previous messages, allowing the model to respond contextually across multiple turns.

### Task 5 – Exit Condition
Implemented a `check_exit()` function that stops the chatbot when the user types `exit`, `quit`, `bye`, `goodbye`, or `stop`.

---

## Pipeline Flow
```
User Input → Tokenization → Chat Template Formatting → Model Processing → Response Generation → Display Output → Repeat until Exit
```

---

## How to Run

1. Clone the repository
```bash
git clone https://github.com/samruddhikhedkar2004/Innomatics-GenAI-Tasks.git
```

2. Install dependencies
```bash
pip install transformers torch
```

3. Open the notebook
```bash
jupyter notebook
```

4. Run all cells and interact with the chatbot in the console

---

## Learning Outcomes
- Understood how transformer-based instruction-following models work
- Loaded and used a pre-trained model from Hugging Face Model Hub
- Applied prompt-based text generation using `model.generate()`
- Built a fully functional interactive console chatbot
- Implemented multi-turn conversation flow using chat history
