# Arcane Final IA

Este projeto é um fork de [Pythonando/arcane-final](https://github.com/Pythonando/arcane-final) com ajustes e melhorias.

## Descrição

Aplicação Django com integração à OpenAI e uso de NLP para construção de uma interface de consulta automatizada via painel web ou integrações externas (ex: WhatsApp).

## Funcionalidades

- Treinamento da IA com base em PDFs
- Chat com IA integrada usando LangChain + OpenAI
- Streaming de respostas
- Consulta a fontes associadas
- Integração com WhatsApp via webhook
- Painel de administração com autenticação

## Tecnologias utilizadas

- Python 3.10+
- Django
- LangChain
- FAISS
- Django Q
- OpenAI API
- SQLite (padrão, mas substituível)

## Instalação e uso

### 1. Clone o projeto

```bash
git clone https://github.com/e-brendon/arcane-final_IA.git
cd arcane-final_IA
```

### 2. Crie um ambiente virtual

```bash
python3.10 -m venv .venv
source .venv/bin/activate
```

### 3. Instale as dependências

```bash
pip install -r requirements.txt
```

### 4. Configure a variável de ambiente

Crie um arquivo `.env` na raiz com:

```
OPENAI_API_KEY=sua-chave-da-openai
```

Ou copie o arquivo env_base para .env e coloque a chave do chatGPT
```
cp env_base .env
```
### 5. Execute as migrações

```bash
python manage.py migrate
```

### 6. Crie um superusuário (opcional)

```bash
python manage.py createsuperuser
```

### 7. Inicie o servidor

```bash
python manage.py runserver 0.0.0.0:8000
```

Acesse via navegador: `http://localhost:8000/oraculo/`

## 📂 Estrutura principal

```
arcane-final_IA/
├── core/               # Configurações principais do Django
├── oraculo/            # App responsável pelo chat e IA
├── usuarios/           # App de autenticação de usuários
├── templates/          # Templates HTML
├── static/             # Arquivos estáticos
├── db.sqlite3          # Banco de dados SQLite
├── .env                # Chave da API OpenAI
└── manage.py
```

## Rotas principais

- `/oraculo/treinar_ia/`
- `/oraculo/chat/`
- `/oraculo/stream_response/`
- `/oraculo/ver_fontes/<id>/`
- `/oraculo/webhook_whatsapp/`
- `/usuarios/login/`
- `/admin/`

## 📄 Licença

Distribuído como fork educacional e experimental. Consulte a licença original em [Pythonando/arcane-final](https://github.com/Pythonando/arcane-final).
