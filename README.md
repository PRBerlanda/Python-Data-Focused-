# 08-LLM-LlamaIndex

Branch do repositório [Python-Data-Focused-](https://github.com/PRBerlanda/Python-Data-Focused-). Veja a [main](https://github.com/PRBerlanda/Python-Data-Focused-/tree/main) para a lista de todas as branches.

## Notebooks

| Notebook | Conteúdo |
|---|---|
| [LlamaIndex_Pandas_Query_Engine](LlamaIndex_Pandas_Query_Engine.ipynb) | **LlamaIndex: consultas em linguagem natural sobre DataFrames.** Uso do `PandasQueryEngine` do LlamaIndex com uma LLM da Groq para responder perguntas sobre um DataFrame, customização de prompts e saídas com um pipeline (Workflow), geração de relatório em PDF e uma aplicação Gradio que analisa qualquer arquivo CSV. |
| [LlamaIndex_RAG_and_JSON_Responses](LlamaIndex_RAG_and_JSON_Responses.ipynb) | **LlamaIndex: RAG, chatbot e respostas automatizadas em JSON.** Processo de RAG (*Retrieval Augmented Generation*) com LlamaIndex: leitura de documentos, divisão em chunks, embeddings, armazenamento em banco vetorial (ChromaDB), chatbot com memória em Gradio e um pipeline de recomendação que gera respostas em JSON validadas contra a base de dados. |
| [LlamaIndex_SQL_Database](LlamaIndex_SQL_Database.ipynb) | **LlamaIndex: assistente para consultar um banco de dados SQL.** Conexão a um banco SQLite com SQLAlchemy, indexação das tabelas com embeddings para que o LlamaIndex encontre a tabela relevante para cada pergunta, geração de consultas SQL com uma LLM da Groq, prompts personalizados, um pipeline com Workflow e um chat em Gradio. |

Para abrir no Colab: *Arquivo → Abrir notebook → GitHub*, informe `PRBerlanda/Python-Data-Focused-` e escolha esta branch. A primeira célula de cada notebook indica os dados necessários. Localmente: `pip install -r requirements.txt`.

## Notas da consolidação

- **Secrets do Colab** (ícone de chave, com acesso liberado ao notebook): `GROQ_API` (os três notebooks, mesmo nome usado nos originais) e `OPENAI_API_KEY` (só a seção 1, opcional, do notebook de RAG). Nenhum original tinha chave literal no código nem nas saídas.
- **LlamaIndex_Pandas_Query_Engine**: `Aula_5.ipynb` (base; `Aula_5(1)`/`(2)` são idênticas entre si e só diferem por instalações e pelo modelo antigo `llama3-70b-8192`) → seções 1–3 e 5–6; `LlamaIndex - Analising Data with Pandas` → pipeline com Workflow (seção 4); `LlamaIndex CSV Reader` → app genérico com leitura de qualquer CSV (seção 6).
- **LlamaIndex_SQL_Database**: `LlamaIndex DB SQL Reader` (versão passo a passo; a célula “Prompt completo” que repetia tudo de uma vez foi removida).
- **LlamaIndex_RAG_and_JSON_Responses**: `Untitled18` → seção 1 (RAG mínimo com OpenAI, opcional); `LlamaIndex Chatbot with RAG` → seções 2–4; `LlamaIndex Automated Responses - With JSON formating` → seções 5–6.
- **Removido**: cascatas de `pip uninstall/install` com versões fixas e `!rm -rf`, as 5 versões repetidas do app Gradio (fica só a final), o `app.py` duplicado para o Hugging Face (resumido em markdown), consultas repetidas (“exibir” vs “plotar”), testes de versão com erro, import não usado de `mistralai`, `SimpleChatEngine` sem uso, `get` de um ID fixo do Chroma, e a célula Streamlit que dava erro (virou trecho de código em markdown).
- **QueryPipeline → Workflow**: `QueryPipeline`/`FnComponent` foram removidos das versões recentes do LlamaIndex; o pipeline Pandas e a cadeia SQL foram reescritos com `Workflow`/`@step`, mantendo os mesmos prompts e etapas. O pipeline Pandas virou uma classe `PandasWorkflow(df, llm)` reutilizada no app (corrige o `return` fora da função do original).
- **Correções**: `gerar_pdf` devolvia tupla para um único `gr.File` e `add_historico` devolvia `None` sem pergunta; PDF passou para `fpdf2` com `new_x/new_y` e texto convertido para latin-1 (evita erro com emojis); leitura de CSV com `chardet` + separador inferido (o original importava `chardet` sem usar); no SQL, o índice “contextualizado” era recriado sem as descrições (`context_str`) — agora usa as descrições; histórico do `gr.Chatbot` no formato `role/content`; no RAG, removido o wrapper de embedding do Chroma (chamava `HuggingFaceEmbedding.embed`, que não existe, e carregava o modelo duas vezes), índice carregado com `from_vector_store` quando a coleção já existe (em vez de `load_index_from_storage` logo após criar), embedding calculado da pergunta (e não da resposta), `validando` checava só o último título (indentação), `json.loads` protegido contra blocos ```json, `os.makedirs('csv')` antes de salvar.
- **Modelos**: Groq `openai/gpt-oss-20b` (o mais recente usado nos originais), embeddings `BAAI/bge-m3` (SQL) e `intfloat/multilingual-e5-large` (RAG), OpenAI `gpt-5.4-mini` na introdução.
- Apps intermediários usam `launch()` sem `debug=True` para não travar o “Executar tudo”; `theme` passado em `launch()` (Gradio 6, instalado com `-U`).
- **Dados**: `vendas.csv` e `livros_mais_vendidos.csv` via URL; enviar `ecommerce.db` para `/content/`, PDFs do catálogo para `/content/pdf/` e textos para `/content/artigos/`.
