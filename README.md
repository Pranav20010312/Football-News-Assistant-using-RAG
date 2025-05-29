# ⚽ Football News Assistant using RAG

## 📌 Problem Statement  
Built a **GenAI application** to transform football news articles into an interactive question-answering tool.  
Fans and journalists often want to extract meaningful insights quickly from long-form news content. This project uses **RAG (Retrieval-Augmented Generation)** to let users ask questions about live football articles and get accurate, source-cited answers in real time.

---

## 🧰 Technologies & Tools Used

- **Python** – Core programming language
- **LangChain** – RAG pipeline orchestration
- **Gradio** – UI for interaction inside Jupyter Notebook
- **ChromaDB** – Vector store for similarity search
- **HuggingFace** – Sentence embeddings with `all-MiniLM-L6-v2`
- **Groq + LLaMA 3 (70B)** – LLM used for fast, high-quality answers
- **Unstructured** – For scraping article content from URLs
- **Jupyter Notebook** – Development and demonstration environment

---

## 🧪 Project Workflow

### 1. 🌐 URL Ingestion
- User provides a football news article URL.
- Text content is fetched and parsed using `UnstructuredURLLoader`.

### 2. ✂️ Text Chunking & Embedding
- Article is split into semantic chunks using `RecursiveCharacterTextSplitter`.
- Each chunk is embedded via HuggingFace’s `MiniLM` model.

### 3. 🧠 Vector Store Setup
- Embeddings are stored in **ChromaDB**.
- Database is refreshed each run to stay in sync with new URLs.

### 4. 🤖 Retrieval-Augmented Generation (RAG)
- Relevant chunks are retrieved via semantic similarity.
- Passed to **LLaMA 3 70B** through the Groq LLM interface.
- LangChain's `RetrievalQAWithSourcesChain` generates accurate, source-grounded answers.

### 5. 🖥️ Gradio UI in Jupyter Notebook
- Clean interface where users:
  - Paste article URLs.
  - Type natural-language questions.
  - Receive answers + original source links.

---

## 🖼️ Screenshot
Below is the Football News Assistant answering questions from a article using RAG and LLM.
![App Preview](APP.jpg)


---

## 📊 Outcomes
-Enables football fans and analysts to ask detailed questions about current news.

-Reduces time spent reading full-length articles.

---

## ⚙️ Setup Instructions
1) Run the following command to install all dependencies.

   pip install -r requirements.txt

2) Create a .env file with your GROQ credentials as follows:

   GROQ_MODEL=MODEL_NAME_HERE
   GROQ_API_KEY=GROQ_API_KEY_HERE
