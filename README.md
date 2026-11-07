# Python, data focused

Study notebooks of **Python for data analysis**: language basics, pandas, ETL, data visualization and statistics. They were written in **Google Colab** during Alura courses and the MBA in Data Science and Analytics (USP/Esalq).

The machine learning notebooks (clustering, PCA, regression, logistic regression, trees, time series, text mining) now live in the **[Data-Science](https://github.com/PRBerlanda/Data-Science)** repository, which has one tested project per branch.

## Notebooks

| Topic | Notebook | What it covers | Data |
|---|---|---|---|
| Python basics | [Working_with_Lists](Working_with_Lists.ipynb) | `input`, conditionals, `while`/`for` loops, lists, `map`/`lambda` | none |
| | [For_Usage](For_Usage.ipynb) | Loops, functions, `filter`, list processing exercises | none |
| | [For_Try_Def](For_Try_Def.ipynb) | Comprehensions, dictionaries, `try/except`, functions with NumPy | none |
| pandas | [Knowing_Pandas](Knowing_Pandas.ipynb) | Reading data, `info`, `groupby`, filters, new columns | Alura rent dataset (URL) |
| | [Filtering_and_Grouping](Filtering_and_Grouping.ipynb) | Filtering, `melt`, `groupby`, merging greenhouse-gas emissions (SEEG) with population (IBGE), Plotly | SEEG / IBGE spreadsheets* |
| ETL | [Working_with_Archive_Formats](Working_with_Archive_Formats.ipynb) | Reading CSV, Excel, JSON, XML and HTML; encodings (`chardet`); SQL with SQLAlchemy | course files* |
| | [Data_ETL](Data_ETL.ipynb) | `json_normalize`, `explode`, cleaning numbers, text and dates | course JSON/CSV files* |
| | [ETL_Exporting_to_SQL](ETL_Exporting_to_SQL.ipynb) | Normalising a book table into authors/genres/books/comments and writing SQL `INSERT` scripts | `livros.csv`* + comments (URL) |
| | [Streaming](Streaming.ipynb) | Joining and summarising the Netflix / Prime Video / Hulu / Disney+ catalogues | [Kaggle dataset](https://www.kaggle.com/datasets/ruchi798/tv-shows-on-netflix-prime-video-hulu-and-disney)* |
| Visualization | [DataViz_PLT_SNS](DataViz_PLT_SNS.ipynb) | Matplotlib, Seaborn and Plotly with immigration to Canada (1980–2013) | `imigrantes_canada.csv`* |
| Statistics | [Statistics_1](Statistics_1.ipynb) | Variable types, frequency distributions, central tendency and dispersion with the PNAD 2015 survey | `dados.csv` (PNAD)* |
| | [Frequency_Measures](Frequency_Measures.ipynb) | Frequency tables, measures of position and dispersion, charts | Alura datasets (URL) |
| | [Resuming_Data](Resuming_Data.ipynb) | Challenge notebook: summarising and analysing a survey sample by region | Alura dataset (URL) |
| | [Hyphotesis_Test](Hyphotesis_Test.ipynb) | Sampling distributions, normal distribution, t-tests (independent and paired samples), confidence intervals | course CSV files* |
| Finance | [Price_and_indicators](Price_and_indicators.ipynb) | Stock prices (`yfinance`) and fundamental indicators of Brazilian companies (`fundamentus`) | live APIs |

\* Upload the file to the Colab session (`/content/`) before running. These files come from the courses and are not stored here. The notebooks marked "URL" download their data directly.

## How to run

**Google Colab (recommended):** open a notebook on GitHub and replace `github.com` with `githubtocolab.com` in the address bar, or go to *File → Open notebook → GitHub* in Colab. The libraries used are already installed in Colab, except `deep-translator` and `fundamentus`, which the notebooks install with `pip`.

**Locally:**

```bash
git clone https://github.com/PRBerlanda/Python-Data-Focused-.git
cd Python-Data-Focused-
python -m venv venv && source venv/bin/activate
pip install -r requirements.txt
jupyter lab
```

The `from google.colab import data_table` line in `Streaming.ipynb` only works in Colab; outside it, remove the line and the tables display as usual.

## Changes in this update

- **Machine learning notebooks removed.** Their topics are covered by the Data-Science repository:
  - `Clustering` → `01-Cluster-Analysis`
  - `Factorial_PCA` → `02-PCA-Factor-Analysis`
  - `Linear_Regression` → `04-Linear-Regression`
  - `Logistic_Regression` → `05-Binary-Logistic-Regression`
  - `Classification_Tree`, `Regression_Tree`, `Decision_Tree_with_ensamble` → `10-Trees-and-Ensembles`
  - `Temporal_Series_Training` → `09-Time-Series-Forecasting`
  - `Text_Mining` → `13-Text-Mining-NLP`
- **`Prediction_model_absenteism_turnover` removed** because its outputs showed row-level HR data.
- **Duplicate removed.** `Creating_SQL_Archive` was an unfinished version of the same task as `ETL_Exporting_to_SQL`: three of its cells failed with `KeyError`. The complete notebook was kept.
- **Added** `Statistics_1` (PNAD 2015).
- **Fixed** `Resuming_Data`: the Centre-West filter compared a column with a list (`== [...]`, `ValueError`). It now uses `.isin([...])`, which returns the 8,772 rows of the four states.
- **Fixed** `Working_with_Lists`: the full-name loop printed `'Nome completo '` without the name and kept the error output of an earlier attempt.
- **Smaller `Streaming.ipynb`** (22 MB → 83 KB). The Colab interactive-table JavaScript, saved in every output, was removed; the tables are kept as HTML, so the notebook now opens on GitHub.
- **Added** `requirements.txt` for running outside Colab.
