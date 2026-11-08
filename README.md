# 05-Data-Visualization

Branch do repositório [Python-Data-Focused-](https://github.com/PRBerlanda/Python-Data-Focused-). Veja a [main](https://github.com/PRBerlanda/Python-Data-Focused-/tree/main) para a lista de todas as branches.

## Notebooks

| Notebook | Conteúdo |
|---|---|
| [Data_Visualization](Data_Visualization.ipynb) | **Visualização de dados com Python.** Gráficos com Matplotlib, Seaborn e Plotly a partir dos dados de imigração para o Canadá (Parte 1) e gráficos de comparação e de distribuição com foco em storytelling, usando vendas de uma rede de lojas e medidas de produtos de limpeza (Parte 2). |

Para abrir no Colab: *Arquivo → Abrir notebook → GitHub*, informe `PRBerlanda/Python-Data-Focused-` e escolha esta branch. A primeira célula de cada notebook indica os dados necessários. Localmente: `pip install -r requirements.txt`.

## Notas da consolidação

- **Origens:** `Aula Alura Data Visualization PLT e SNS.ipynb` (idêntico a `repo_atual/DataViz_PLT_SNS.ipynb`) → seções 1–4 (Parte 1); `DataViz_ Comparação e Distribuição.ipynb` → seções 5–9 (Parte 2). Os imports e a paleta de cores (constantes `AZUL1`…`VERDE2`) ficam no setup.
- **Dados:** `imigrantes_canada.csv` (enviar para `/content/`); as bases da Parte 2 são lidas por URL (`alura-cursos/dataviz-graficos`).
- **Removido (repetições):** recargas do CSV para o `melt` (agora usa `df.reset_index()`); `df_teste` (Brasil via melt, igual a `dados_brasil`); linha OO simples (coberta pelo subplot linha+boxplot); versão `Solarize_Light2` (igual à `dark_background`); barras horizontais sem destaque (entre a vertical e a com destaque); barplot Seaborn básico (a função de paletas faz o mesmo); `america_sul.head()` solto; `print` dos *containers*; os dois "desafios" da Aula 1 (lucro por ano e top 10 em vendas: mesmos gráficos de 5.1/5.3 trocando a métrica, com recarga dos dados e redefinição de `texto_colorido`); célula vazia de verificação; `from pandas.core.reshape import encoding`, `import math`/`numpy` não usados, `fig.update` solto, imports dentro das funções.
- **Corrigido:** `anos = range(1980, 2013)` excluía 2013 → `range(1980, 2014)`; título "1988 a 2013" → "1980 a 2013"; título do gráfico da América Latina dizia "Brasil" (variável `america_sul` renomeada para `america_latina`); `sort_values`/`drop(inplace=True)` em resultado de `query` (SettingWithCopyWarning); escapes inválidos `\ ` em strings LaTeX → `\\ `; `set_title` duplicado nas barras 100%; `fig, axs` usado como `ax` no violin plot; `axhline/axvline` recebiam `xmin/xmax` em unidades de dados (são frações do eixo); `vol_amaciante.quantile(...)` (Series) → `vol_amaciante['Volume'].quantile(...)`; resample `'Q'` → `'QE'`; texto "10%" da pergunta do sabão em pó alinhado ao código (1%).
- **Completado:** as Aulas 3–5 do notebook do Drive eram o modelo do curso com `...` no lugar do código e personalizações comentadas (nunca executadas). Foram completadas: resample trimestral de SP, gráfico de linha e eixo de datas (`mdates`), layout do Plotly por região, `describe`, histograma, `kdeplot`, linhas de média/mediana/moda, boxplot com anotações, violin plot e dispersão com cores por regra de rejeição. As coordenadas das anotações (textos, elipses) vêm do original e podem precisar de ajuste fino ao rodar; o `binwidth` do histograma ficou como alternativa comentada.
- **Não executado** (validação apenas por `nbtools check`).
