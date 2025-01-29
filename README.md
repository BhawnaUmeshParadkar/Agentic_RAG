# 🚀 Intelligent Question Routing & Answering System

## 📌 Overview
This project is an **AI-powered question-answering system** that intelligently routes user queries to either a **Retrieval-Augmented Generation (RAG) system** or **web search**, ensuring high-quality, relevant, and hallucination-free responses.

## 🏗️ Key Features
- **Dynamic Routing**: Determines whether a question should be answered using a vector store or a web search.
- **Retrieval-Augmented Generation (RAG)**: Uses a PDF-based knowledge retrieval system.
- **Web Search Integration**: Fetches answers from the web for queries outside the vector store’s scope.
- **Multi-Step Answer Validation**:
  - **Relevance Grading**: Assesses if retrieved information is relevant.
  - **Hallucination Filtering**: Ensures factual accuracy.
  - **Final Answer Validation**: Generates a response only if the answer is useful.

## ⚙️ Tech Stack
- **LLM**: `llama3-8b-8192` (via Groq API)
- **Embedding Model**: `BAAI/bge-small-en-v1.5` (via Hugging Face)
- **Search Tools**:
  - **PDFSearchTool** (for RAG-based retrieval)
  - **TavilySearchResults** (for web search)
- **CrewAI**: Manages AI agents and task execution.

## 🏗️ Agents & Their Roles
1. **Router Agent**: Routes the question to either the RAG system or web search.
2. **Retriever Agent**: Fetches relevant information based on the routing decision.
3. **Grader Agent**: Evaluates if the retrieved document is relevant.
4. **Hallucination Grader Agent**: Ensures the answer is factually accurate.
5. **Answer Grader Agent**: Provides a final quality check and determines if additional web search is required.

## 🚀 How It Works
1. **User asks a question** → Routed to either the vector store or web search.
2. **Retriever Agent** fetches the information.
3. **Grader Agent** validates relevance.
4. **Hallucination Grader** checks factual correctness.
5. **Answer Grader** decides if the response is useful or if a web search is needed.

## 🔧 Setup & Usage
1. **Set up API keys**:
   ```python
   os.environ['GROQ_API_KEY'] = 'your_groq_api_key'
   os.environ['TAVILY_API_KEY'] = 'your_tavily_api_key'
   ```
2. **Run the system**:
   ```python
   result = answer_task.run("How does exercise price determine for ESOP?")
   print(result)
   ```

## 📌 Future Enhancements
- Add more LLM provider options.
- Support for multi-document retrieval.
- Expand grading mechanisms for better response validation.

---

🔗 **Developed using CrewAI, LangChain, and Groq LLMs** 🚀
