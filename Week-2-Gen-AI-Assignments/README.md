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

---
# NLP Assignment 4 – Fine-Tuning BERT for Text Classification

## Overview
This assignment focuses on fine-tuning a pre-trained **BERT model** for binary sentiment classification using the **IMDB Movie Reviews** dataset. The goal is to understand how transformer models work, apply different fine-tuning strategies, and evaluate model performance using standard classification metrics.

---

## Dataset
- **Name:** IMDB Movie Reviews
- **Source:** Hugging Face Datasets (equivalent to Kaggle IMDB dataset)
- **Task:** Binary Sentiment Classification
- **Labels:** 0 = Negative, 1 = Positive
- **Size:** 50,000 reviews (25k train + 25k test)

---

## Tools & Technologies
- Python
- Hugging Face Transformers
- PyTorch
- Google Colab (GPU)
- Jupyter Notebook

---

## Project Pipeline
```
Raw Data → Preprocessing → Tokenization → Model Training → Evaluation → Experiment Comparison
```

---

## Steps Followed

### 1. Data Preprocessing
- Removed HTML tags (e.g. `<br />`)
- Removed special characters and digits
- Converted text to lowercase
- Handled missing/empty values

### 2. Data Splitting
| Split | Size |
|---|---|
| Train | 80% |
| Validation | 20% |
| Test | Separate held-out set |

### 3. Tokenization
- Used `bert-base-uncased` tokenizer
- Max token length: 128
- Generated input IDs and attention masks

### 4. Model
- `AutoModelForSequenceClassification` from Hugging Face
- Pre-trained: `bert-base-uncased`
- Number of labels: 2

### 5. Training Configuration
| Parameter | Value |
|---|---|
| Optimizer | AdamW |
| Learning Rate | 2e-5 |
| Epochs | 3 |
| Batch Size | 16 |
| Gradient Clipping | 1.0 |
| LR Scheduler | Linear warmup |

---

## Experiments

| Experiment | Setup | Trainable Parameters |
|---|---|---|
| Exp 1: Full Fine-Tuning | All layers trainable | All (~110M) |
| Exp 2: Frozen BERT | All BERT layers frozen | Classifier head only |
| Exp 3: Last 2 Layers | Last 2 encoder layers + classifier | ~14M |
| Bonus: DistilBERT | Full fine-tuning on DistilBERT | ~66M |

---

## Evaluation Metrics
- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix

---

## Results & Analysis

### Experiment Comparison

| Experiment | Expected Behavior |
|---|---|
| Exp 1: Full Fine-Tuning | Best performance — entire model adapts to the task |
| Exp 2: Frozen BERT | Fastest training — uses pre-trained features as-is |
| Exp 3: Last 2 Layers | Good balance of speed and accuracy |

### Key Insights

1. **Full Fine-Tuning (Exp 1)** achieves the highest accuracy as all model weights adapt to the downstream task.
2. **Frozen BERT (Exp 2)** performs surprisingly well, proving that BERT's pre-trained representations are powerful even without task-specific fine-tuning.
3. **Last 2 Layers (Exp 3)** strikes a balance — upper layers capture task-relevant patterns while base BERT features remain stable.
4. **Training Time:** Frozen BERT trains fastest; Full fine-tuning takes the most time.
5. **Overfitting:** Full fine-tuning has a higher overfitting risk on small datasets; Frozen BERT is more stable.
---

## Bonus
- ✅ Implemented **DistilBERT** — 40% smaller and 60% faster than BERT, with competitive accuracy
- ✅ Used **Linear Learning Rate Scheduler** with warmup steps

---

## Conclusion

This assignment demonstrated three fine-tuning strategies for BERT on binary sentiment classification:

- **Full Fine-Tuning** provides the best accuracy by adapting all model weights to the task
- **Frozen BERT** is efficient and effective, leveraging powerful pre-trained language representations
- **Last 2 Layers Fine-Tuning** offers a great trade-off between compute cost and performance
- **DistilBERT** achieves competitive results with significantly fewer parameters and faster inference

The IMDB dataset is well-suited for sentiment analysis and BERT achieves strong results even with limited samples and epochs.

---
