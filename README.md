## 🏢 Contexto Profissional

Você foi contratado(a) pela **MSousa Tech**, uma empresa fictícia de tecnologia focada em soluções educacionais e ferramentas de produtividade com Inteligência Artificial.

A MSousa Tech identificou um problema recorrente entre desenvolvedores iniciantes: **a dificuldade em encontrar respostas claras, didáticas e confiáveis sobre programação em Python**. Muitos alunos recorrem a fóruns dispersos, tutoriais desatualizados ou respostas genéricas de IA que não seguem um padrão pedagógico.

Como solução, a empresa decidiu desenvolver um **assistente de IA especializado em Python**, capaz de responder dúvidas de programação de forma estruturada, com explicações conceituais, exemplos de código comentados, detalhamento da lógica e links para a documentação oficial.

**Sua missão como desenvolvedor(a) contratado(a):** construir esse assistente utilizando **Python**, **Streamlit** e a **API da Groq**, seguindo as especificações técnicas definidas pela equipe de produto da MSousa Tech.

---

## 🎯 Objetivo do Projeto

Desenvolver uma aplicação web interativa chamada **"Ajuda Imunes AI Coder"**, que funcione como um **assistente pessoal de programação Python**, seguindo um padrão rígido de respostas pedagógicas e acessível via navegador.

Ao final do projeto, o aluno será capaz de:

- Compreender a integração entre **Python + Streamlit + APIs de LLM**;
- Aplicar conceitos de **prompt engineering** com *system prompts* personalizados;
- Gerenciar **estado de sessão** (`st.session_state`) em aplicações Streamlit;
- Trabalhar com **variáveis sensíveis** (API Keys) de forma segura;
- Estruturar um projeto real de portfólio.

---

## 🧩 Requisitos Funcionais (Especificações da MSousa Tech)

A aplicação deve atender aos seguintes requisitos definidos pelo time de produto:

| # | Requisito | Descrição |
|---|-----------|-----------|
| RF01 | Interface Web | Utilizar **Streamlit** para criar uma interface de chat interativa. |
| RF02 | Entrada de API Key | Permitir que o usuário insira sua **API Key da Groq** pela barra lateral, com campo do tipo senha. |
| RF03 | Memória de Conversa | Manter o **histórico de mensagens** durante a sessão usando `st.session_state`. |
| RF04 | Prompt de Sistema | Utilizar um **system prompt customizado** que define o comportamento pedagógico do assistente. |
| RF05 | Foco em Python | O assistente deve responder **exclusivamente** sobre programação, algoritmos e bibliotecas. |
| RF06 | Estrutura de Resposta | Toda resposta deve seguir o padrão: **Explicação → Código → Detalhes → Documentação de Referência**. |
| RF07 | Tratamento de Erros | Exibir mensagens amigáveis em caso de falha na comunicação com a API. |
| RF08 | Modelo LLM | Utilizar o modelo `openai/gpt-oss-20b` via API da Groq. |

---

## 🛠️ Tecnologias Utilizadas

- **Python 3.10+** — Linguagem base do projeto
- **Streamlit** — Framework para criação da interface web
- **Groq SDK** — Cliente oficial para comunicação com a API da Groq
- **LLM (openai/gpt-oss-20b)** — Modelo de linguagem responsável pelas respostas

---

## 📁 Estrutura do Projeto

```
ajuda-imunes-ai-coder/
│
├── app.py                # Código principal da aplicação
├── requirements.txt      # Dependências do projeto
└── README.md             # Este arquivo
```

---

## ⚙️ Instalação e Execução

### 1. Clone o repositório

```bash
git clone https://github.com/seu-usuario/ajuda-imunes-ai-coder.git
cd ajuda-imunes-ai-coder
```

### 2. Crie um ambiente virtual (recomendado)

```bash
python -m venv venv
# Windows
venv\Scripts\activate
# Linux/macOS
source venv/bin/activate
```

### 3. Instale as dependências

Crie um arquivo `requirements.txt` com o conteúdo:

```txt
streamlit
groq
```

E instale:

```bash
pip install -r requirements.txt
```

### 4. Obtenha sua API Key da Groq

1. Acesse [https://console.groq.com/keys](https://console.groq.com/keys)
2. Crie uma conta gratuita (se ainda não tiver)
3. Gere uma nova **API Key** e copie o valor

### 5. Execute a aplicação

```bash
streamlit run app.py
```

A aplicação abrirá automaticamente no navegador em `http://localhost:8501`.

---

## 🚀 Como Usar

1. **Insira sua API Key da Groq** na barra lateral (ela ficará oculta por segurança);
2. **Digite sua dúvida sobre Python** no campo de chat na parte inferior;
3. O assistente responderá seguindo o padrão:
   - 📖 **Explicação Clara** do conceito
   - 💻 **Exemplo de Código** comentado
   - 🔍 **Detalhes do Código** (linha a linha)
   - 📚 **Documentação de Referência** (link oficial)

### Exemplo de pergunta

> "Como funciona uma list comprehension em Python?"

---

## 🧠 Como Funciona o Prompt de Sistema

O coração do assistente está no `CUSTOM_PROMPT`, que define **quem ele é** e **como deve responder**. Ele instrui o modelo a:

1. **Focar apenas em programação** — ignorando perguntas fora do escopo;
2. **Seguir uma estrutura fixa de resposta** (explicação → código → detalhes → docs);
3. **Ser didático, claro e tecnicamente preciso**;
4. **Sempre citar a documentação oficial** como referência.

Esse é um exemplo prático de **Prompt Engineering aplicado a contextos educacionais**.

---

## 🔐 Segurança

- A **API Key nunca é armazenada** em disco ou em código-fonte;
- O campo usa `type="password"` para evitar exposição visual;
- Cada usuário utiliza sua **própria chave**, sem compartilhamento;
- Em caso de erro na inicialização do cliente, a aplicação é interrompida com segurança (`st.stop()`).

> ⚠️ **Nunca** faça commit de chaves de API em repositórios públicos.

---

## 🧪 Desafios Propostos (Extensões)

Após concluir a versão base, tente implementar:

- [ ] Botão para **limpar o histórico** da conversa;
- [ ] **Exportar** o histórico em `.txt` ou `.pdf`;
- [ ] Suporte a **múltiplos modelos** da Groq (seleção via `selectbox`);
- [ ] Adição de **temperature ajustável** pela interface;
- [ ] **Modo escuro/claro** customizado;
- [ ] **Contador de tokens** consumidos por resposta.

---

## 📚 Documentação de Referência

- 🐍 [Python Oficial](https://docs.python.org/3/)
- 🎈 [Streamlit Docs](https://docs.streamlit.io/)
- ⚡ [Groq API Docs](https://console.groq.com/docs)
- 🧠 [Prompt Engineering Guide](https://www.promptingguide.ai/)

---

## 👨‍🏫 Sobre o Projeto

Este projeto foi desenvolvido como **Situação de Aprendizagem** em ambiente escolar, simulando um cenário real de contratação pela empresa fictícia **MSousa Tech**. O objetivo é unir **prática de programação Python**, **integração com IA** e **desenvolvimento de portfólio** em uma única atividade.

> *"Deixe de ser imune ao conhecimento — e ajude o seu professor."* 🤖🐍

---

## 📝 Licença

Este projeto é de uso **educacional**. Sinta-se livre para estudar, adaptar e compartilhar, dando os devidos créditos.

---
