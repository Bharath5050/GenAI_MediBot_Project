# 🩺 GenAI MediBot

An intelligent medical assistant built using LLM, Pinecone, and LangChain. GenAI MediBot helps users search medical information and get context-aware answers powered by a vector database and chain-of-thought reasoning.

## 🚀 Features

- Natural Language Query Support  
- Semantic Search with Pinecone  
- Contextual Reasoning using LangChain  
- Modular and Scalable Architecture  
- FastAPI-based Backend for Integration  

## 🧱 Tech Stack

| Component     | Technology Used      |
|---------------|----------------------|
| LLM           | OpenAI GPT-4 / GPT-3.5 |
| Embeddings    | OpenAI Embeddings     |
| Vector DB     | Pinecone              |
| Chain Manager | LangChain             |
| Backend       | Python (FastAPI)      |
| Deployment    | Docker (optional)     |

## 🔧 Prerequisites

- Python 3.10+
- Required API Keys:
  - OpenAI API Key
  - Pinecone API Key, Environment, and Index

### Install Dependencies

```bash
pip install -r requirements.txt
```

## ⚙️ Setup Instructions

```bash
git clone https://github.com/Bharath5050/GenAI_MediBot_Project.git
cd GenAI_MediBot_Project
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### 🔐 Environment Variables

Create a `.env` file in the root directory with the following content:

```env
OPENAI_API_KEY=your_openai_key
PINECONE_API_KEY=your_pinecone_key
PINECONE_ENVIRONMENT=your_environment
PINECONE_INDEX_NAME=medibot
```

## 🚀 Running the Project

1. **Ingest documents** into Pinecone:

```bash
python ingest.py
```

2. **Start the backend API server**:

```bash
python serve.py
```

3. **Query the API:**

```bash
curl -X POST http://localhost:8000/query \
  -H "Content-Type: application/json" \
  -d '{"query": "What are the side effects of paracetamol?"}'
```

## 🧠 How It Works

### Ingestion Pipeline

- Load and chunk medical documents  
- Generate embeddings via OpenAI  
- Store embeddings in Pinecone  

### Query Flow

- Convert user input to vector  
- Retrieve top-k documents from Pinecone  
- Use LangChain to construct a context-aware prompt  
- LLM generates a final answer  

## 📚 Example

```json
{
  "query": "What is the dosage of ibuprofen for children?"
}
```

The bot returns relevant medical context and a safe, LLM-generated answer.

## 🧪 Running Tests

```bash
pytest tests/
```

## 🌱 Future Enhancements

- [ ] Web UI using React or Next.js  
- [ ] Support multiple LLM backends (Anthropic, Cohere)  
- [ ] Add user authentication  
- [ ] Deploy with Docker and CI/CD  

## 🤝 Contribution

1. Fork the repo  
2. Create a feature branch: `git checkout -b feature-name`  
3. Commit your changes  
4. Push the branch: `git push origin feature-name`  
5. Open a Pull Request  

## 📄 License

Licensed under the [MIT License](LICENSE).
