# 04-PySpark

Branch do repositório [Python-Data-Focused-](https://github.com/PRBerlanda/Python-Data-Focused-). Veja a [main](https://github.com/PRBerlanda/Python-Data-Focused-/tree/main) para a lista de todas as branches.

## Notebooks

| Notebook | Conteúdo |
|---|---|
| [PySpark_Introduction](PySpark_Introduction.ipynb) | **Introdução ao Apache Spark com PySpark.** Primeiros passos com PySpark no Google Colab usando os dados públicos de CNPJ da Receita Federal: leitura de CSV, tipos de dados, seleções, filtros, agregações, *joins*, Spark SQL e formas de armazenamento (CSV, Parquet, ORC e particionamento). |

Para abrir no Colab: *Arquivo → Abrir notebook → GitHub*, informe `PRBerlanda/Python-Data-Focused-` e escolha esta branch. A primeira célula de cada notebook indica os dados necessários. Localmente: `pip install -r requirements.txt`.

## Notas da consolidação

- **PySpark_Introduction** (46 células) ← "Spark for Data Science - Introduction.ipynb" (curso Alura de introdução ao Spark): teoria → 1; instalação Windows/Colab → 2; carga → 3; demais seções na ordem do original.
- **Setup atualizado:** o original instalava `openjdk-8`, mas apontava `JAVA_HOME` para o Java 21, baixava `spark-4.2.0-bin-hadoop3.tgz` com `wget` e usava `findspark`. Agora: `apt-get install openjdk-17-jdk-headless` (o Spark 4.x exige Java 17+) + `!pip install -q pyspark` + `SparkSession`; `findspark`, `SPARK_HOME` e o download manual foram removidos. Requisitos da seção Windows atualizados (Java 7/Python 2.6 → Java 17/Python 3).
- **Segurança:** havia um **authtoken do ngrok literal** (`!ngrok authtoken "..."`) usado só para expor a Spark UI. A parte do ngrok (download do binário, `pyngrok`, token) foi removida por ser acessória; o token não foi copiado. Fica a dica opcional `output.serve_kernel_port_as_window(4050)` do Colab. Recomenda-se revogar esse token no painel do ngrok.
- `empresasJoinView` e `freqView` (detectados como "imports" no inventário) são nomes de *views* temporárias do Spark SQL usados dentro de strings; não são módulos.
- **Generalização:** as três leituras com renomeação `_c0..._cN` viraram `ler_csv_receita(nome, colunas)`; a extração dos `.zip` (antes comentada) roda só se a pasta ainda não existir.
- **Correções:** `%%time` estava depois de um comentário (precisa ser a 1ª linha da célula); `spark.stop` → `spark.stop()`; `.count().alias('registros')` não renomeava a coluna → `.agg(f.count('*').alias('registros'))`; a 2ª consulta SQL sobrescrevia `freq` → `freq_sql`; saídas gravadas dentro da pasta de entrada `empresas/` → `curso-spark/saida/`; import não usado `FloatType` removido; links da documentação 3.1.2 → `latest`.
- **Removido:** saídas, `!apt-get update`, `!pip install findspark`/`pyngrok`, células do ngrok.
- **Dados:** `empresas.zip`, `estabelecimentos.zip`, `socios.zip` (URLs públicas do curso, no notebook) na pasta `MyDrive/curso-spark` do Google Drive.
