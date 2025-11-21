# 🤖 Chatbot RAG | Orientação Pré e Pós-Operatória Cardíaca

Este repositório contém o código-fonte do protótipo desenvolvido para o **Trabalho de Conclusão de Curso (TCC)** em Informática Biomédica, focado na aplicação segura de Inteligência Artificial na saúde.

## 🎯 Objetivo

Desenvolver e validar um Agente Conversacional (AC) que utiliza a arquitetura **Retrieval Augmented Generation (RAG)** para fornecer orientações precisas e seguras a pacientes cardíacos, mitigando os riscos de alucinação de LLMs genéricos.

## ⚙️ Arquitetura e Tecnologias

O sucesso do projeto é atribuído à engenharia de uma Base de Conhecimento (BK) composta e à parametrização rigorosa da cadeia RAG.

| Componente | Tecnologia | Função no Projeto |
| :--- | :--- | :--- |
| **LLM (Modelo de Linguagem)** | Llama 3 (Versão Quantizada) | Geração de respostas humanas e contextualizadas. |
| **Framework** | LangChain | Orquestração da cadeia RAG e lógica do *retriever*. |
| **Banco de Vetores (DB)** | ChromaDB | Armazenamento persistente da Base de Conhecimento (BK) vetorial. |
| **Interface de Simulação** | Gradio | Criação da interface *web* e *mobile* para testes remotos. |

## 📁 Base de Conhecimento Híbrida

A BK foi otimizada para segurança clínica, combinando:
* **Literatura Científica:** Artigos revisados sobre cirurgia cardíaca.
* **Conhecimento Tático:** Documentos de FAQ e protocolos de rotina desenvolvidos por enfermeira especialista.

## 🔑 Segurança e Validação

* O sistema utiliza um **Prompt Template de Segurança** que força o redirecionamento ao médico em caso de perguntas individualizadas ou incerteza.
* A Taxa de Segurança (0% de alucinação) foi validada através de testes cegos com especialistas clínicos.

## 💻 Como Executar

Este projeto é desenvolvido para o ambiente Google Colab. Para executá-lo:

1.  **Clone este repositório** e faça o *upload* das pastas **`data/`** e **`chroma_db/`** para um local acessível no seu Google Drive.
2.  Abra o arquivo principal (`TCC_Chatbot_RAG.ipynb` ou o nome do seu notebook) no Google Colab.
3.  **Ajuste de Caminhos (CRÍTICO):** Na primeira célula do notebook, onde os caminhos para o Google Drive são definidos, é **essencial** que você ajuste as variáveis (`DRIVE_PATH`, `CHROMA_PERSIST_DIR`, etc.) para que elas apontem para a localização exata das pastas no seu próprio Drive.

    * *Exemplo de Ajuste no Notebook:* Se você colocou o projeto em `Meu Drive/TCC_Final/`, o caminho no código deve ser modificado para:
        ```python
        DRIVE_PATH = "/content/drive/MyDrive/TCC_Final/ChatbotRAG_TCC/"
        ```

4.  Execute as células sequencialmente.

---
**Autora:** Gabriela Toledo da Costa
**Instituição:** UFCSPA, Informática Biomédica.
