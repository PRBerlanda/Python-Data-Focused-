# 01-Python-Fundamentals

Branch do repositório [Python-Data-Focused-](https://github.com/PRBerlanda/Python-Data-Focused-). Veja a [main](https://github.com/PRBerlanda/Python-Data-Focused-/tree/main) para a lista de todas as branches.

## Notebooks

| Notebook | Conteúdo |
|---|---|
| [NumPy_Fundamentals](NumPy_Fundamentals.ipynb) | **Fundamentos de NumPy.** Criação e operações com arrays, desempenho em relação às listas, broadcasting, leitura de dados com `np.loadtxt`, fatiamento, tratamento de valores ausentes, uma regressão linear simples calculada "à mão" e geração de números aleatórios, usando preços de maçãs em cidades da Rússia. |
| [Python_Fundamentals](Python_Fundamentals.ipynb) | **Fundamentos de Python.** Notebook de estudo com a base da linguagem para análise de dados: tipos, operadores, estruturas de controle, coleções, compreensões, funções e tratamento de exceções, seguido de exercícios organizados por tema. |

Para abrir no Colab: *Arquivo → Abrir notebook → GitHub*, informe `PRBerlanda/Python-Data-Focused-` e escolha esta branch. A primeira célula de cada notebook indica os dados necessários. Localmente: `pip install -r requirements.txt`.

## Notas da consolidação

- **Python_Fundamentals.ipynb**:
  - **Origens:** `Working_with_Lists` (versão do repositório, com a correção do nome completo; substitui `Untitled15`), `For_Usage` (= `Usando For`), `For_Try_Def` (= `Funções For, Try e Def`), `Untitled14`, `Untitled16` e `Untitled17`.
  - **Seções 1–12, por tema:** tipos, operadores, entrada/saída, condicionais, laços, listas, dicionários, tuplas/desempacotamento, compreensões/`zip`, funções/`lambda`/`map`/`filter`, módulos e exceções.
  - **Seção 13:** os exercícios, agrupados por tema.
- **NumPy_Fundamentals.ipynb:** vem de `Usando Numpy`, mais a célula de broadcasting de `For_Try_Def`. **Dados:** `apples_ts.csv` (arquivo do curso Alura), enviado para `/content/`.
- **Removido:**
  - Rabiscos:
    - `'''` sem fechar;
    - lista markdown sem sentido;
    - print da data de nascimento;
    - `type()`/`dir()`/`tamanho` soltos;
    - `i + 3 / 2`.
  - `!pip install` de matplotlib, `!pip list`, `from random import *` e `help(random)`.
  - Duplicações:
    - tabuada (3×);
    - nome completo com `map` (2×);
    - separação de notas (2×);
    - `media` com docstring (2×);
    - boletim (2×);
    - crescimento de bactérias (2×);
    - `lista_completa` literal.
  - Tentativas com erro seguidas da versão correta.
  - Pseudocódigo inválido (que virou markdown) e um modelo de função vazio.
- **`input()` substituído** por valores de exemplo com o comentário `# valor de exemplo (originalmente lido com input)`. Laços que liam até um valor de parada usam `iter([...])`/`next()`.
- **Correções:**
  - `soma + temp` → `soma += temp`;
  - `marca_pontos` comparava listas inteiras → `x1[i] > x2[i]`;
  - o custo da viagem exibia uma tupla → `sum(gastos)`;
  - `gastos` não estava definido;
  - validação de data com `print(input())` → inteiros;
  - produto mais vendido: indentação, `produtos`/`produto` e a porcentagem, que nunca era calculada;
  - erro de digitação `voto_desing` (`NameError`);
  - `multiplos`: o `if` ficava fora do laço;
  - `qualitativo2` era definido, mas `qualitativo` é que era chamado;
  - `acertos` inexistente → `corretor` (o verificador de pontuação virou `verifica_pontuacao`);
  - tipos de retorno errados → `tuple`;
  - `except` genérico → `ZeroDivisionError`;
  - `random.choices` sem `random` → `choices`;
  - exercício `gera_codigo` concluído;
  - `'19 Trimestre'` → `'1º Trimestre'`.
- **Correções NumPy:**
  - `array_equal(ano3, ano3)` (sempre `True`) → `ano3` vs `ano4`;
  - contagem de NaN movida para antes do preenchimento;
  - `coef_angulares[1]` → o coeficiente de menor norma (`argmin`).
- **Dados pessoais:** nome, idade e cidade pessoais e a data de nascimento foram trocados por valores genéricos ou removidos. Nenhuma chave ou segredo foi encontrado.
