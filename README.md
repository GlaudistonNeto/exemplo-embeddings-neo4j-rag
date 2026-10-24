# example-embeddings-neo4j

Exemplo de pipeline de embeddings com Neo4j como vector store, usando TypeScript e LangChain.

## O que faz

1. **Lê o conteúdo:** carrega um PDF com `PDFLoader`.
2. **Quebra em chunks:** divide o texto com `RecursiveCharacterTextSplitter`.
3. **Gera embeddings:** converte cada chunk em vetor com Hugging Face Transformers, rodando localmente.
4. **Salva no Neo4j:** armazena os chunks e vetores em um índice vetorial do Neo4j.
5. **Busca por similaridade:** recupera os trechos mais próximos de cada pergunta e envia ao LLM (via OpenRouter) para gerar a resposta.

## Stack

Node.js, TypeScript, LangChain, Hugging Face Transformers, Neo4j 5 (Docker), OpenRouter

## Como rodar

    pnpm i
    cp .env.example .env     # preencha as variáveis
    pnpm run infra:up        # sobe o Neo4j
    pnpm start

Neo4j Browser: http://localhost:7474