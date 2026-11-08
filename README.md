# 02-Pandas-Data-Analysis

Branch do repositório [Python-Data-Focused-](https://github.com/PRBerlanda/Python-Data-Focused-). Veja a [main](https://github.com/PRBerlanda/Python-Data-Focused-/tree/main) para a lista de todas as branches.

## Notebooks

| Notebook | Conteúdo |
|---|---|
| [Pandas_Filtering_Grouping_SEEG](Pandas_Filtering_Grouping_SEEG.ipynb) | **Filtrando e agrupando dados com pandas: emissões de gases de efeito estufa (SEEG).** Seleção com `loc` e `isin`, reestruturação com `melt` e `pivot_table`, agrupamentos com `groupby` (inclusive multi-índice com `xs`, `idxmax` e `swaplevel`) e junção com a população dos estados para calcular a emissão per capita, com gráficos em pandas e Plotly. |
| [Pandas_Fundamentals](Pandas_Fundamentals.ipynb) | **Conhecendo o pandas.** Primeiros passos com a biblioteca pandas usando uma base de imóveis para aluguel no Rio de Janeiro: leitura, inspeção, agrupamentos, gráficos, tratamento de nulos, filtros, criação de colunas e exportação. No final, os desafios do curso com uma base de alunos. |

Para abrir no Colab: *Arquivo → Abrir notebook → GitHub*, informe `PRBerlanda/Python-Data-Focused-` e escolha esta branch. A primeira célula de cada notebook indica os dados necessários. Localmente: `pip install -r requirements.txt`.

## Notas da consolidação

- **Pandas_Fundamentals.ipynb:**
  - **Seções 1–6:** vêm de `Knowing_Pandas` (= `Conhecendo o Pandas`).
  - **Seção 7 (desafios):** vem de `Aula 01 Conhecendo Pandas - Resolvido` (7.1) e `Aula 02 Conhecendo Pandas` (7.2).
  - **Dados:** lidos por URL (`aluguel.csv` e `alunos.csv` da Alura).
- **Pandas_Filtering_Grouping_SEEG.ipynb:** vem de `Filtering_and_Grouping` (= `Filtrando e Agrupando Dados`). **Dados** a enviar para `/content/`:
  - `1-SEEG10_GERAL-BR_UF_2022.10.27-FINAL-SITE.xlsx` (SEEG, aba `GEE Estados`);
  - `POP2022_Municipios.xls` (IBGE).
- **Correção (Aula 01):** `df['Notas'].replace({7.0, 8.0}, inplace=True)` passava um conjunto, e não um dicionário. Agora é `df_alunos['Notas'] = df_alunos['Notas'].replace({7.0: 8.0})`, aplicado sobre uma `.copy()` do recorte filtrado.
- **Correções (Knowing_Pandas):**
  - `assign`/`apply` usavam `df` em vez de `df2`/`df3` (`KeyError`);
  - a média fixa `4744.61...` → `@media_geral`;
  - `fillna(method=...)`, removido do pandas recente → `fillna(0)`, com `ffill`/`bfill`/`interpolate` como alternativas comentadas;
  - `inplace` sobre o resultado de uma query → atribuição;
  - células com várias expressões foram separadas;
  - o segundo download → `dados.copy()`.
- **Correções (SEEG):**
  - `df.pop(...)` logo após o `drop` da mesma coluna (`KeyError`);
  - a lista de métodos de groupby escrita como código (`SyntaxError`) virou tabela markdown;
  - a participação do CO2 usava `iloc` fixo → agora usa rótulos e exclui as linhas `CO2e`;
  - `insert` agora recebe um array 1D;
  - `'\('` → `r'\('`.
- **Removido (SEEG):**
  - a segunda carga da planilha (`efeito_estufa.xlsx`) com o mesmo filtro e `melt`;
  - a primeira de duas versões da limpeza da população;
  - `df`/`.groups` soltos;
  - o cálculo repetido de `emissao_por_gas`;
  - as duas últimas células, com `data.csv` (dados de RH de empresa, sem relação com o SEEG).
- **Sem segredos ou dados pessoais.**
