# 🧠 Comprehensive AI-Powered Retail Analytics System
**Multi agent to power enterprise AI like - Accenture AI**

Check out the deployed webpage - https://mansishah-accenture-agent.streamlit.app/

---

## 📌 Problem Statement

Retail businesses often struggle with making timely, data-driven decisions across areas like demand forecasting, inventory monitoring, and pricing optimization. These decisions typically require collaboration among various departments and expertise in querying large datasets, which is inefficient and error-prone using traditional methods.

### Why AI Multi-Agent Systems?

Multi-agent AI systems can mimic the collaborative nature of human decision-making by dividing complex retail analytics tasks among specialized agents. Each agent can independently reason, act, and then collaborate to complete tasks efficiently—bringing modularity, scalability, and speed.

---

## 🔍 Project Description

This project is an AI-powered retail analytics platform built with **LlamaIndex**, **Groq’s ultra-fast LLMs**, and **Streamlit**. Users can interact using natural language, and the system translates this into executable Pandas code for real-time analytics across retail datasets.

---

## 🧩 Agent Collaboration

- **Agent 1**: Fast, general-purpose query handler (`Groq gemma2-9b-it`)
- **Agent 2**: Deep reasoning and complex query handler (`Groq llama3-70b`)
- **Agent 3**: Fallback sandbox agent (can be extended for meta-reasoning)

Agents use the **ReAct** framework:

```
Thought → Action → Observation → Repeat
```

This enhances explainability by showing step-by-step reasoning and tool usage.

---

## 🧠 Query Processing

- Each dataset has a dedicated `PandasQueryEngine` backed by `llama3-70b`
- Agents dynamically select the correct dataset using tool abstractions via **LlamaIndex**
- Outputs are formatted using custom **boxify logic** for clarity

---

## 🧾 Datasets Supported 

- `demand_forecasting.csv` – Sales transactions across time and regions  
- `inventory_monitoring.csv` – Stock levels and supply chain status  
- `pricing_optimization.csv` – Historical pricing and promotional effects
-  `sample_market_data_report.pdf` – Market intelligence report containing company performance, revenue growth, market capitalization, technology sector trends, market indicators, and risk analysis (used for RAG-based document question answering)

---

## 🧰 Tools, Libraries, and Frameworks Used

- **LlamaIndex** – Query engine and agent orchestration  
- **Streamlit** – Interactive frontend interface  
- **Groq LLMs** – Ultra-fast inference via `gemma2-9b-it` and `llama3-70b`  
- **Pandas** – Data wrangling and query execution  
- **ReAct Framework** – Agent reasoning and action chaining  
- **Custom Tools**:
  - `ChatMemoryBuffer`
  - `Output Formatter`
  - `PromptTemplate` abstraction  

---

## 🧠 LLM Selection

### Ideal LLMs Used
- **Groq llama-3.3-70b-versatile** – For complex reasoning and comprehension  
- **Groq llama-3.1-8b-instant** – For low-latency instruction following  

**Justification**:  
Groq LLMs offer ultra-fast execution, which is essential for real-time analytics and a smooth user experience. For cost-sensitive or open environments, GPT-3.5 and Mistral are strong fallback options.

---

## 💻 Code and Deployment

### 🔗 GitHub Repository  
👉 [GitHub Link]([https://github.com/your-username/ai-retail-analytics](https://github.com/nishant0363/Nishant-Accenture-Agent)) 

---

## 📁 Repository Structure

```
├── .devcontainer/ – Development container configuration added by streamlit deployement
├── .ipynb_checkpoints/ – Jupyter notebook checkpoints
├── Extra/ – Extra files and older version codes
├── pycache/ – 
├── data/ – CSV files which LLM uses/refers.
├── 9.png – My Profile Image used as ICON in chat window
├── Accenture Project.jpeg – Project-Top Image
├── Accenture-logo.png – Accenture branding/logo used as ICON in chat window
├── image.png – 
├── interactive1.py – Streamlit UI logic
├── requirements.txt – Python dependencies
├── streamlit4.py – Main Streamlit application
```


## 📊 Example Use Cases

- “What were the top 5 products by sales”
- “low sales products?”
- “Store 48 sales?”

**Workflow**:  
Natural language → LLM interpretation → Pandas code generation → Result display

---

## 🚀 New Feature: Retrieval-Augmented Generation (RAG)

The application now supports answering questions from external PDF documents using a RAG pipeline.

### Workflow

- Load PDF documents
- Convert text into embeddings
- Store embeddings in a VectorStoreIndex
- Retrieve the most relevant chunks
- Generate answers using Groq's `llama-3.3-70b-versatile`

### Example Questions

- What are the major risks mentioned in the market report?
- Which company has the highest revenue growth?
- Compare AlphaCloud and NeuralWorks.
- What market indicators are discussed?

## 🚀 Future Extensions

- Support for SQL via `SQLQueryEngine`  
- Ingest unstructured PDF data using **LlamaParse**  
- Add **voice interface** for accessibility  
- Enable **graph analytics** for supply chain modeling  
- **Cloud deployment** with persistent user sessions  

