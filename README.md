# 07-Financial-Data

Branch do repositório [Python-Data-Focused-](https://github.com/PRBerlanda/Python-Data-Focused-). Veja a [main](https://github.com/PRBerlanda/Python-Data-Focused-/tree/main) para a lista de todas as branches.

## Notebooks

| Notebook | Conteúdo |
|---|---|
| [Stock_Prices_and_Fundamentals](Stock_Prices_and_Fundamentals.ipynb) | **Cotações e indicadores fundamentalistas de ações.** Extração de cotações históricas de ações da B3 com `yfinance` e de indicadores fundamentalistas com `fundamentus`, tratamento dos dados (formato longo, tipos numéricos, junção) e cálculo de LPA, VPA e do valor intrínseco de Graham, seguidos dos desafios do curso. |

Para abrir no Colab: *Arquivo → Abrir notebook → GitHub*, informe `PRBerlanda/Python-Data-Focused-` e escolha esta branch. A primeira célula de cada notebook indica os dados necessários. Localmente: `pip install -r requirements.txt`.

## Notas da consolidação

- **Origens:** `Extração das cotações e indicadores.ipynb` (= `repo_atual/Price_and_indicators.ipynb`) → seções 1–3; `Desafios+(Aulas+01,+03+e+05).ipynb` → seção 4. Conteúdo reorganizado por tema: 1) cotações (`yfinance`), 2) indicadores (`fundamentus`), 3) transformação (formato longo, tipos, junção, LPA/VPA), 4) desafios.
- **Dados:** APIs ao vivo (Yahoo Finance e Fundamentus); nenhum arquivo para enviar.
- **Corrigido:** `pip install fundamentus` sem `!` (sintaxe inválida fora do Colab) → `!pip install -q fundamentus yfinance`; `apply(pd.to_numeric, ..., axis=1)` (linha a linha) → por coluna; `import yfinance` repetido/fora do setup unificado como `import yfinance as yf`.
- **Alterado:** as linhas comentadas que recalculavam P/L e P/VP (e sobrescreveriam as colunas do Fundamentus) viraram colunas de conferência `P/L_calc` e `P/VP_calc`.
- **Completado:** o Desafio 2 citava a fórmula de Graham (VI = √(22,5 × LPA × VPA)) sem calculá-la; agora calcula `VI_Graham` (NaN quando LPA ou VPA ≤ 0). O `del` final foi removido e as variáveis do desafio ganharam nomes próprios para não sobrescrever as das seções 1–3.
- **Removido:** células vazias dos desafios da Aula 03; Desafio 3 (Aula 05), que repetia o download/`stack` da seção 1 com outro período e terminava com uma célula incompleta; imports repetidos; exibições intermediárias (`df` após `stack`, `ind_2`/`ind` duplicados).
- **Não executado** (validação apenas por `nbtools check`); os resultados dependem da data de execução e da disponibilidade das APIs.
