# 🤖 LLMOps — ChatGPT & Hugging Face Integration

Projeto focado em **LLMOps (Large Language Model Operations)**, demonstrando como integrar, gerenciar e operacionalizar modelos de linguagem utilizando **OpenAI (ChatGPT)** e **Hugging Face**.

O objetivo é criar uma base prática para desenvolvimento, experimentação e deploy de aplicações com IA generativa, incluindo boas práticas de engenharia, organização e escalabilidade.

---

## 🚀 Tecnologias Utilizadas

### 🧠 Inteligência Artificial
- OpenAI API (ChatGPT)
- Hugging Face Transformers
- Hugging Face Inference API

### 🔙 Backend
- Python 3.10+
- FastAPI / Flask *(dependendo da implementação do projeto)*
- Uvicorn

### ⚙️ LLMOps & Infra
- Docker
- dotenv
- Requests / HTTPX
- Logging

### 🔜 Opcional / Extensões
- LangChain
- Vector Databases (FAISS, Pinecone, etc.)
- Redis (cache)

---

## ⚙️ Como Rodar o Projeto Localmente

### 1️⃣ Clonar o Repositório

```bash
git clone <url-do-repositorio>
cd llmops-chatgpt-huggingface-main
```

2️⃣ Criar Ambiente Virtual
```
python -m venv venv
source venv/bin/activate  # Linux/Mac
```
Windows:
```
venv\Scripts\activate
```
3️⃣ Instalar Dependências
```
pip install -r requirements.txt
```
4️⃣ Configurar Variáveis de Ambiente

Crie um arquivo .env na raiz do projeto:
```
OPENAI_API_KEY=your_openai_key_here
HUGGINGFACE_API_KEY=your_hf_key_here
MODEL_NAME=gpt-4
HF_MODEL=google/flan-t5-base
```
5️⃣ Executar a Aplicação

Se estiver usando FastAPI:
```
uvicorn app.main:app --reload
```
Ou Flask:
```
python app.py
```
Servidor disponível em:
```
👉 http://localhost:8000
```

---

📡 Endpoints Principais
🔹 Chat com ChatGPT
POST /chat/openai

Body:

{
  "prompt": "Explique o que é LLMOps"
}
🔹 Geração com Hugging Face
POST /chat/huggingface

Body:

{
  "prompt": "Resuma inteligência artificial em 3 linhas"
}
🔹 Health Check
GET /health

---

🧠 Decisões Técnicas

- Separação por provedores (OpenAI / Hugging Face) para facilitar testes comparativos.

Arquitetura modular:

- routes/ → endpoints
- services/ → lógica de IA
- config/ → variáveis e setup
- Uso de variáveis de ambiente para segurança.
- Implementação desacoplada para permitir troca de modelos facilmente.
- Preparado para evolução com ferramentas de LLMOps (monitoramento, cache, etc.).

---

📦 Funcionalidades Implementadas

- 🤖 Integração com ChatGPT (OpenAI)
- 🤗 Integração com Hugging Face
- 🔄 Comparação entre modelos
- 📡 API REST para consumo externo
- ⚙️ Configuração via .env
- 🧪 Base para experimentação com prompts

---

🏗️ Estrutura do Projeto
```
├── app/
│   ├── main.py
│   ├── routes/
│   ├── services/
│   ├── config/
│   └── models/
├── requirements.txt
├── .env
└── README.md
```

---

🚀 Deploy

Docker (Recomendado)
```
docker build -t llmops-app .

docker run -p 8000:8000 llmops-app

Cloud (Render / Railway / AWS)
```
Subir repositório
```
Configurar serviço Python
```
Definir:

Start Command
```
uvicorn app.main:app --host 0.0.0.0 --port 8000
```
Variáveis:
```
OPENAI_API_KEY
HUGGINGFACE_API_KEY
```

---

🔐 Segurança

- Nunca versionar .env
- Usar secrets em produção
- Implementar rate limit (recomendado)
- Adicionar autenticação para APIs públicas

---

📈 Possíveis Evoluções

- 🧠 Memory (contexto persistente)
- 🔍 RAG (Retrieval-Augmented Generation)
- 📊 Observabilidade (logs + métricas)
- ⚡ Cache de respostas (Redis)
- 📚 Embeddings + busca semântica
- 🤖 Orquestração com LangChain

---

🎯 Objetivo do Projeto

- Aprender e aplicar conceitos de LLMOps
- Comparar modelos de linguagem
- Criar APIs inteligentes reutilizáveis
- Servir como base para aplicações reais com IA

---

📚 Referências
- https://platform.openai.com/docs
- https://huggingface.co/docs
- https://fastapi.tiangolo.com
- https://www.langchain.com
---
