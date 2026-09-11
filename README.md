# 🏈 NFL Game Prediction: Data Mining & Machine Learning

Este repositório contém um pipeline completo focado na previsão de resultados de jogos da NFL (2021-2025). O projeto é desenvolvido em iterações, iniciando com modelos preditivos base, seguidos por uma profunda exploração de mineração de dados em quatro pilares matemáticos, com o objetivo final de extrair a verdadeira "topologia" e o "DNA" das franquias para otimizar futuras predições.

## 🗂️ Estrutura do Repositório

O projeto está organizado estruturalmente em duas frentes principais que refletem as iterações de desenvolvimento:

### 1. `📁 baseline` (Iteração 1)

Responsável por todo o fluxo inicial de engenharia de features, treinamento dos modelos preditivos de referência e realização das inferências brutas.

* **`init_data_eng.ipynb`**: Tratamento de dados, criação de novas variáveis (feature engineering) e preparação do dataset.
* **`rf_baseline.ipynb`**: Treinamento e validação de um modelo Random Forest (RF) de referência (baseline).
* **`xgb_baseline.ipynb`**: Implementação de um modelo XGBoost de referência.
* **`predictions.ipynb`**: O motor de inferência que consome os modelos treinados para gerar as previsões das partidas.
* **`nfl_features_ml_2021_2025.parquet`**: Base de dados tratada e estruturada englobando as features originais (2021 a 2025).

### 2. `📁 mining` (Iteração 2)

Focado na extração de conhecimento avançado através dos **4 Pilares do Data Mining**. O objetivo desta camada é descobrir padrões ocultos, identificar anomalias estatísticas e mapear taticamente a NFL para, futuramente, alimentar modelos preditivos superiores aos baselines.

* **`EDA.ipynb`**: Notebook base de Análise Exploratória de Dados.
* **`association_rules.ipynb`**: Mineração de Regras de Associação (FP-Growth) para descobrir correlações táticas diretas.
* **`📁 outliers`**: Deteção de anomalias estatísticas extremas mascaradas como sucesso.
  * **`iso_forest.ipynb`**: Aplicação de Isolation Forest.
  * **`LOF.ipynb`**: Aplicação de Local Outlier Factor.
* **`📁 dim_redux`**: Redução da dimensionalidade pra 2D, focando na explicabilidade macro, e tentando extrair insights.
  * **`etl_data.ipynb`**: Preparação dos dados específicos para redução.
  * **`dados_reducao.parquet`**: Dataset intermediário salvo pra uso nos modelos, é a saída do 'etl_data.ipynb'.
  * **`PCA.ipynb`**: Abordagem linear (descartada do pipeline principal por baixa performance topológica).
  * **`t-SNE.ipynb`**: Abordagem de topologia local e isolamento de extremos.
  * **`UMAP.ipynb`**: Abordagem global (State of the Art) para estratificação da liga.
* **`📁 clustering`**: Agrupamento matemático (Identidade e DNA das franquias).
  * **`HDBSCAN.ipynb`**: Agrupamento baseado em densidade hierárquica rodando sobre os espaços reduzidos obtidos em 'dim_redux'. Identifica a estratificação das elites, classes médias, e times ruins.
  * **`GMM.ipynb`**: Modelos de Mistura Gaussiana (Probabilísticos) para *soft clustering* dos times.

  ### 3. O próximo passo será usar os achados do data mining pra tentar criar modelos com desempenho melhor do que oo baselines estabelecidos na primeira iteração. (Iteração 3)

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Python
* **Ambiente:** Jupyter Notebook
* **Bibliotecas Preditivas (Baseline):** `scikit-learn` (Random Forest, GridSearchCV), `xgboost`
* **Bibliotecas de Mineração:** `scikit-learn` (t-SNE, Outliers, GMM), `hdbscan` (Clustering de Densidade), `umap-learn` (Redução Topológica), `mlxtend` (Regras de Associação)
* **Manipulação e Estruturas:** Pandas, Numpy, formato Parquet

## 🚀 Como Executar

1. Clone o repositório.
2. Certifique-se de ter as dependências completas instaladas (`pip install numpy pandas matplotlib scikit-learn xgboost hdbscan umap-learn mlxtend`).
3. **Para reproduzir os baselines:** Entre na pasta `baseline/` e rode a esteira na seguinte ordem: `init_data_eng.ipynb` ➡️ `rf_baseline.ipynb` / `xgb_baseline.ipynb` ➡️ `predictions.ipynb`.
4. **Para acompanhar a descoberta tática:** Entre na pasta `mining/` e avance através dos 4 pilares, começando pelas regras de associação, filtragem de outliers, redução de dimensionalidade e finalizando na construção de clusters. A execução das reduções gera o arquivo intermediário `dados_reducao.parquet` necessário para a pasta `clustering`.
