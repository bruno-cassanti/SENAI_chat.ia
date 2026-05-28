# SENAI_chat.ia

# 🤖 SENAI IA Chatbot — Assistente de Programação Python com IA

Projeto desenvolvido como parte do curso **FIC IA Generativa aplicada à Programação com ChatGPT — SENAI**.

O objetivo deste projeto foi criar um chatbot inteligente focado exclusivamente em **programação com Python**, capaz de responder dúvidas de iniciantes com:

✅ explicações didáticas
✅ exemplos de código comentados
✅ detalhamento da lógica utilizada
✅ links oficiais de documentação

---

# 📌 Visão Geral

O **SENAI IA Chatbot** é uma aplicação web construída com **Streamlit** e integrada à API da **Groq**.

O usuário pode:

* inserir sua chave da API Groq
* fazer perguntas sobre Python
* visualizar respostas formatadas com exemplos práticos
* manter histórico da conversa durante a sessão

---

# 🖼️ Interface do Projeto

## Barra lateral

Na sidebar o usuário encontra:

* campo para inserir API Key
* descrição do chatbot
* observações sobre uso da IA
* link institucional do SENAI

## Área principal

Na tela principal:

* título do chatbot
* campo de pergunta
* histórico de mensagens
* resposta da IA em tempo real

---

# 🛠️ Tecnologias utilizadas

## Python

Linguagem principal da aplicação.

## Streamlit

Framework usado para criar a interface web de forma rápida.

Instalação:

```bash
pip install streamlit
```

Documentação:

https://docs.streamlit.io/

---

## Groq API

Responsável por gerar as respostas da IA.

Instalação:

```bash
pip install groq
```

Documentação:

https://console.groq.com/docs

---

## OS

Biblioteca padrão do Python.

Importada para futuras integrações com variáveis de ambiente e configurações locais.

```python
import os
```

---

# 📁 Estrutura do projeto

```bash
senai_chat/
│
├── senai_chat.py
├── requirements.txt
├── README.md
└── venv/
```

---

# ⚙️ Ambiente virtual

Para manter dependências isoladas foi criado um ambiente virtual Python.

Criando:

```bash
python -m venv chat_bot
```

Ativando no Windows:

```bash
chat_bot\Scripts\activate
```

Quando ativo aparece:

```bash
(chat_bot)
```

Instalando dependências:

```bash
pip install streamlit groq
```

Gerando requirements:

```bash
pip freeze > requirements.txt
```

---

# ▶️ Executando o projeto

Com ambiente virtual ativo:

```bash
streamlit run senai_chat.py
```

Depois abrir no navegador:

```bash
http://localhost:8501
```

---

# 🧠 Como funciona internamente

## 1. Configuração inicial

```python
st.set_page_config(...)
```

Define:

* título
* ícone
* layout
* sidebar expandida

---

## 2. Prompt do sistema

Foi criado um prompt personalizado:

```python
CUSTOM_PROMPT
```

Esse prompt define:

* foco apenas em programação
* Python como linguagem principal
* respostas estruturadas
* documentação oficial no final

Isso deixa a IA consistente.

---

## 3. Sidebar

Usando:

```python
with st.sidebar:
```

Criamos:

* título
* campo API Key
* descrição
* links

---

## 4. Estado da conversa

Usando:

```python
st.session_state.messages
```

Armazena:

* mensagens do usuário
* respostas do assistente

Mantém histórico da sessão.

---

## 5. Cliente Groq

Quando usuário digita API:

```python
client = Groq(api_key=groq_api_key)
```

Conecta com a API.

---

## 6. Envio da pergunta

Campo:

```python
st.chat_input()
```

Recebe pergunta.

---

## 7. Montagem das mensagens

Sistema + histórico:

```python
messages_for_api
```

---

## 8. Chamada da IA

```python
client.chat.completions.create(...)
```

Modelo utilizado:

```python
openai/gpt-oss-20b
```

Configurações:

```python
temperature=0.7
max_tokens=2048
```

---

## 9. Exibição

Resposta renderizada:

```python
st.markdown()
```

---

# 📚 Principais conceitos aplicados

Durante o desenvolvimento foram praticados:

* Python
* Streamlit
* APIs
* Engenharia de Prompt
* Session State
* UX básica
* tratamento de exceções
* autenticação com API Key
* organização de projeto

---

# 💡 Melhorias futuras

Ideias para evolução:

* salvar histórico em banco de dados
* exportar conversa
* suporte para múltiplas linguagens
* tema customizado
* exemplos automáticos
* integração com documentação oficial

---

# 🎯 Objetivo de aprendizado

Este projeto ajudou a praticar:

* integração entre front-end e IA
* consumo de APIs
* estruturação de prompts
* construção de apps Python
* organização de código real

---

# 👨‍💻 Autor

Bruno Cassanti

Projeto acadêmico desenvolvido no SENAI.

GitHub:

https://github.com/bruno-cassanti

---

# 🏫 SENAI

Curso:

**FIC IA Generativa aplicada à Programação com ChatGPT**

Unidade:

**SENAI Suíço-Brasileira**
