# 🚀 Automatic Semantic Detection using LangChain

This project is a **semantic feedback classification and response system** built using **LangChain** and **Hugging Face models**. It automatically:
1. **Classifies feedback** as either *positive* or *negative*.
2. **Generates an appropriate response** based on the sentiment.

---

## 🧠 How It Works

The system consists of the following components:

### 1. Sentiment Classifier
- Uses a HuggingFace LLM to classify input feedback into:
  - `positive`
  - `negative`
- Powered by a Pydantic schema and LangChain's `PydanticOutputParser`.

### 2. Dynamic Response Generator
- Based on the sentiment classification:
  - A **positive** response prompt is triggered.
  - A **negative** response prompt is triggered.
- Uses LangChain’s `RunnableBranch` to dynamically select the appropriate prompt and model pipeline.

---

## 🔄 Workflow Diagram

```
     ┌────────────────────────────┐
     │     User Feedback Input    │
     └────────────┬───────────────┘
                  ▼
     ┌────────────────────────────┐
     │    Sentiment Classification│
     └────────────┬───────────────┘
                  ▼
    ┌─────────────┴───────────────┐
    │      RunnableBranch         │
    │  (Select response type)     │
    └────────────┬───────────────┘
      Positive   ▼     Negative
    ┌────────────┐ ┌─────────────┐
    │ Pos. Prompt│ │ Neg. Prompt │
    └────┬───────┘ └────┬────────┘
         ▼              ▼
   ┌──────────┐   ┌────────────┐
   │  Model   │   │   Model    │
   └──────────┘   └────────────┘
         ▼              ▼
     Appropriate     Appropriate
     Positive         Negative
     Response         Response

```
---

## 🛠️ Tech Stack

- **LangChain**
- **HuggingFaceH4/zephyr-7b-beta** LLM
- **Pydantic** for schema-based validation
- **Python** (with `dotenv` for environment handling)

---

## 📦 Installation

```bash
git clone https://github.com/mridulchdry17/Automatic-Semantic-Detection-using-LangChain.git
cd semantic-feedback-agent
pip install -r requirements.txt
```
#### Add your Hugging Face key in a .env file:
```
HUGGINGFACEHUB_API_TOKEN=your_token_here
```



