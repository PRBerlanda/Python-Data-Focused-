# Python, data focused

Notebooks de estudo de **Python para análise e engenharia de dados**, escritos no **Google Colab** durante cursos da Alura e do MBA em Data Science e Analytics (USP/Esalq).

Cada tema fica em uma **branch** própria. A `main` contém apenas este README. Os notebooks de *machine learning* (cluster, PCA, regressões, árvores, séries temporais, text mining, web scraping) estão no repositório **[Data-Science](https://github.com/PRBerlanda/Data-Science)**.

## Branches

| Branch | Notebooks | Conteúdo |
|---|---|---|
| [`01-Python-Fundamentals`](https://github.com/PRBerlanda/Python-Data-Focused-/tree/01-Python-Fundamentals) | [NumPy_Fundamentals](https://github.com/PRBerlanda/Python-Data-Focused-/blob/01-Python-Fundamentals/NumPy_Fundamentals.ipynb)<br>[Python_Fundamentals](https://github.com/PRBerlanda/Python-Data-Focused-/blob/01-Python-Fundamentals/Python_Fundamentals.ipynb) | Fundamentos de NumPy; Fundamentos de Python |
| [`02-Pandas-Data-Analysis`](https://github.com/PRBerlanda/Python-Data-Focused-/tree/02-Pandas-Data-Analysis) | [Pandas_Filtering_Grouping_SEEG](https://github.com/PRBerlanda/Python-Data-Focused-/blob/02-Pandas-Data-Analysis/Pandas_Filtering_Grouping_SEEG.ipynb)<br>[Pandas_Fundamentals](https://github.com/PRBerlanda/Python-Data-Focused-/blob/02-Pandas-Data-Analysis/Pandas_Fundamentals.ipynb) | Filtrando e agrupando dados com pandas: emissões de gases de efeito estufa (SEEG); Conhecendo o pandas |
| [`03-ETL-Data-Engineering`](https://github.com/PRBerlanda/Python-Data-Focused-/tree/03-ETL-Data-Engineering) | [Data_Wrangling_MBA](https://github.com/PRBerlanda/Python-Data-Focused-/blob/03-ETL-Data-Engineering/Data_Wrangling_MBA.ipynb)<br>[ETL_Cleaning_and_Transformation](https://github.com/PRBerlanda/Python-Data-Focused-/blob/03-ETL-Data-Engineering/ETL_Cleaning_and_Transformation.ipynb)<br>[ETL_File_Formats_and_SQL](https://github.com/PRBerlanda/Python-Data-Focused-/blob/03-ETL-Data-Engineering/ETL_File_Formats_and_SQL.ipynb) | Data Wrangling com pandas (MBA USP/Esalq); Transformação e limpeza de dados com pandas; Formatos de arquivos e exportação para SQL |
| [`04-PySpark`](https://github.com/PRBerlanda/Python-Data-Focused-/tree/04-PySpark) | [PySpark_Introduction](https://github.com/PRBerlanda/Python-Data-Focused-/blob/04-PySpark/PySpark_Introduction.ipynb) | Introdução ao Apache Spark com PySpark |
| [`05-Data-Visualization`](https://github.com/PRBerlanda/Python-Data-Focused-/tree/05-Data-Visualization) | [Data_Visualization](https://github.com/PRBerlanda/Python-Data-Focused-/blob/05-Data-Visualization/Data_Visualization.ipynb) | Visualização de dados com Python |
| [`06-Statistics`](https://github.com/PRBerlanda/Python-Data-Focused-/tree/06-Statistics) | [Statistics_Descriptive_PNAD](https://github.com/PRBerlanda/Python-Data-Focused-/blob/06-Statistics/Statistics_Descriptive_PNAD.ipynb)<br>[Statistics_Inference_and_Correlation](https://github.com/PRBerlanda/Python-Data-Focused-/blob/06-Statistics/Statistics_Inference_and_Correlation.ipynb)<br>[Statistics_Summarizing_Data](https://github.com/PRBerlanda/Python-Data-Focused-/blob/06-Statistics/Statistics_Summarizing_Data.ipynb) | Estatística descritiva com a PNAD 2015; Inferência estatística, correlação e regressão; Estatística com Python: resumindo e analisando dados |
| [`07-Financial-Data`](https://github.com/PRBerlanda/Python-Data-Focused-/tree/07-Financial-Data) | [Stock_Prices_and_Fundamentals](https://github.com/PRBerlanda/Python-Data-Focused-/blob/07-Financial-Data/Stock_Prices_and_Fundamentals.ipynb) | Cotações e indicadores fundamentalistas de ações |
| [`08-LLM-LlamaIndex`](https://github.com/PRBerlanda/Python-Data-Focused-/tree/08-LLM-LlamaIndex) | [LlamaIndex_Pandas_Query_Engine](https://github.com/PRBerlanda/Python-Data-Focused-/blob/08-LLM-LlamaIndex/LlamaIndex_Pandas_Query_Engine.ipynb)<br>[LlamaIndex_RAG_and_JSON_Responses](https://github.com/PRBerlanda/Python-Data-Focused-/blob/08-LLM-LlamaIndex/LlamaIndex_RAG_and_JSON_Responses.ipynb)<br>[LlamaIndex_SQL_Database](https://github.com/PRBerlanda/Python-Data-Focused-/blob/08-LLM-LlamaIndex/LlamaIndex_SQL_Database.ipynb) | LlamaIndex: consultas em linguagem natural sobre DataFrames; LlamaIndex: RAG, chatbot e respostas automatizadas em JSON; LlamaIndex: assistente para consultar um banco de dados SQL |

## Reorganização (novembro de 2026)

- **De 84 notebooks do Google Colab e 15 da antiga `main` para 16 notebooks em 8 branches.** Cópias, versões antigas, rascunhos (`Untitled*`) e notebooks vazios foram fundidos ou descartados.
- **Notebooks com dados de RH** (absenteísmo/turnover) **e os de machine learning** ficaram de fora; os de ML estão no repositório Data-Science.
- **Notas da consolidação:** o README de cada branch lista as origens de cada notebook, o que foi removido e as correções feitas.
- **Versão anterior:** os notebooks da antiga `main` continuam no histórico do Git (commit `e5941d0`).

## Padrão dos notebooks

- A primeira célula traz o título, a origem (curso), os dados necessários e o índice das seções.
- A segunda célula é o setup: instala só o que não vem no Colab e concentra todos os imports.
- As seções são numeradas (`## 1.`, `### 1.1`) e cada uma começa com uma explicação curta.
- Os notebooks são salvos sem saídas; rode no Colab para gerar tabelas e gráficos.
- Chaves de API nunca ficam no código. Elas são lidas dos *Secrets* do Colab (`userdata.get(...)`).

## Como rodar

**Google Colab (recomendado):** abra o notebook no GitHub, troque `github.com` por `githubtocolab.com` na barra de endereço ou use *Arquivo → Abrir notebook → GitHub* no Colab e escolha a branch. Os notebooks que usam arquivos de curso indicam na primeira célula o que enviar para `/content/`.

**Localmente:**

```bash
git clone -b <branch> https://github.com/PRBerlanda/Python-Data-Focused-.git
cd Python-Data-Focused-
python -m venv venv
pip install -r requirements.txt
jupyter lab
```

Linhas que começam com `!` e o módulo `google.colab` funcionam só no Colab ou no Jupyter.
