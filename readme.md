![Local-CTI Logo](images/logo.webp)

# 🛡️ Local-CTI: Cyber Threat Intelligence Platform

**Transform your threat analysis with AI-powered intelligence retrieval**

Local-CTI is an advanced threat intelligence platform that leverages the power of local large language models and vector databases to provide instant, contextual answers about cybersecurity threats. Built for security professionals who need rapid access to threat intelligence without relying on external APIs.

---

## ✨ Key Features

🔍 **Intelligent Query Processing** - Ask natural language questions about threats and get precise answers  
📚 **Extensive Knowledge Base** - Pre-loaded with 2200+ threat intelligence reports  
🔒 **Privacy-First** - Everything runs locally, your data never leaves your environment  
⚡ **Fast Retrieval** - Optimized vector database for lightning-fast information access  
🎯 **Contextual Responses** - AI provides relevant context from multiple sources  

---

## 🚀 Quick Start

### Prerequisites

Ensure you have the following installed:
- **Python 3.8+** 
- **Ollama** ([Download here](https://ollama.ai/))
- **Git LFS** ([Installation guide](https://git-lfs.github.com/))

### Installation Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/R0h1tAnand/Local-CTI.git
   cd Local-CTI
   ```

2. **Set up Python environment**
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch the application**
   ```bash
   streamlit run app.py
   ```

> **💡 First Run Note**: The initial startup will download required AI models (dolphin-mistral & nomic-embed-text). This may take 5-10 minutes depending on your internet connection.

---

## 📖 Usage Guide

### Basic Usage
Simply run the application and start asking questions about cybersecurity threats in natural language:
- "What are the latest ransomware trends?"
- "Tell me about APT28 tactics"
- "How does CVE-2023-1234 work?"

### Advanced Configuration

Customize your experience with command-line options:

```bash
streamlit run app.py [OPTIONS]
```

| Option | Description | Default |
|--------|-------------|---------|
| `-m, --model` | LLM model for responses | `dolphin-mistral` |
| `-e, --embedding_model` | Embedding model for search | `nomic-embed-text` |
| `-p, --path` | Documents directory | `reports` |
| `--nb-docs` | Max documents to retrieve | `8` |

**Example with custom settings:**
```bash
streamlit run app.py -m "llama2" -e "all-minilm" -p "/custom/reports" --nb-docs 15
```

---

## 📁 Project Structure

```
Local-CTI/
├── app.py                 # Main Streamlit application
├── models.py             # Model management utilities
├── document_loader.py    # Document processing logic
├── requirements.txt      # Python dependencies
├── db/                   # Vector database storage
│   └── chroma.sqlite3   # Pre-built threat intel database
├── images/              # Application assets
│   └── logo.webp       # Project logo
└── reports/             # Document storage (add your PDFs here)
```

---

## 🔧 Customization

### Adding Your Own Intelligence Reports

1. **Add PDF files** to the `reports/` directory
2. **Restart the application** - new documents will be automatically processed and indexed
3. **Query away** - your new intelligence is now searchable

### Switching AI Models

Use any Ollama-compatible model:
```bash
ollama pull codellama        # Download new model
streamlit run app.py -m codellama  # Use it in Local-CTI
```

Popular models to try:
- `mistral` - Balanced performance
- `codellama` - Code-focused analysis
- `neural-chat` - Conversational responses

---

## 🔬 Technical Architecture

**Core Technologies:**
- **🦜 LangChain** - LLM orchestration and document processing
- **🦙 Ollama** - Local model inference engine  
- **🎨 ChromaDB** - High-performance vector database
- **📄 PyPDF** - PDF document parsing
- **🎈 Streamlit** - Interactive web interface

**Data Flow:**
1. Documents → PDF Parser → Text Chunks
2. Text Chunks → Embedding Model → Vector Database  
3. User Query → Embedding → Similarity Search
4. Retrieved Context + Query → LLM → Response

---

## 🏆 Credits & Acknowledgments

This project builds upon the excellent foundation laid by [@amscotti](https://github.com/amscotti) in the [local-LLM-with-RAG](https://github.com/amscotti/local-LLM-with-RAG) project. We've extended it specifically for cybersecurity threat intelligence use cases.

**Data Sources:**
- Primary intelligence database sourced from [VX-Underground](https://vx-underground.org/)
- Community-contributed threat reports and analysis

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

---

## 🤝 Contributing

We welcome contributions! Whether it's bug fixes, feature additions, or intelligence report contributions, please feel free to:
1. Fork the repository
2. Create a feature branch
3. Submit a pull request

---

**Built with ❤️ for the cybersecurity community**