# 🏈 NFL Game Prediction: Data Mining & Ensemble Models

Este repositório contém um pipeline completo de Machine Learning focado na previsão de resultados de jogos da NFL (National Football League). O projeto está dividido em duas frentes principais: Mineração de Dados (exploração e descoberta de padrões) e Modelagem Ensemble (treinamento, otimização e inferência).

## 🗂️ Estrutura do Repositório

O projeto é organizado nos seguintes diretórios:

### 1. `📁 mining`

Focado na exploração e compreensão da base de dados.

* **`EDA.ipynb`**: Notebook de Análise Exploratória de Dados (Exploratory Data Analysis). Aqui são investigadas as distribuições das variáveis, correlações e características históricas dos jogos da NFL.
* **🚧 Roadmap (Em breve):** Introdução e aplicação dos **4 Pilares do Data Mining**, aprofundando a extração de conhecimento da base de dados antes da modelagem.

### 2. `📁 ensemble`

Responsável por todo o fluxo de engenharia de features, treinamento dos modelos preditivos e realização das inferências para os jogos da NFL.

* **`engenharia_de_dados.ipynb`**: Tratamento de dados, criação de novas variáveis (feature engineering) e preparação do dataset para o consumo dos algoritmos de Machine Learning.
* **`modelo_rf_gridsearch.ipynb`**: Treinamento de um modelo Random Forest (RF) utilizando GridSearch para a busca exaustiva de hiperparâmetros.
* **`modelo_xgb_gridsearch.ipynb`**: Implementação de um modelo XGBoost otimizado via GridSearch.
* **`motor_de_inferencia.ipynb`**: O motor de predição final. Consome os modelos treinados e os dados mais recentes para gerar as previsões dos resultados das partidas.
* **`nfl_features_ml_2021_2025.parquet`**: Base de dados tratada e estruturada (formato colunar de alta performance) englobando as features das temporadas de 2021 a 2025.

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Python
* **Ambiente:** Jupyter Notebook
* **Bibliotecas de Modelagem:** Scikit-learn (Random Forest, GridSearch), XGBoost
* **Otimização de Hiperparâmetros:** Optuna, GridSearchCV
* **Manipulação de Dados:** Pandas, Numpy

## 🚀 Como executar

1. Clone o repositório.
2. Certifique-se de ter as bibliotecas necessárias instaladas (`pip install numpy scipy jupyter ipykernel pandas matplotlib seaborn scikit-learn nflreadpy`).
3. Inicie a exploração pela pasta `mining/EDA.ipynb` para entender os dados.
4. Para reproduzir os modelos, siga a ordem lógica na pasta `ensemble`: execute primeiro a `engenharia_de_dados.ipynb`, seguido pelo treinamento dos modelos e, por fim, o `motor_de_inferencia.ipynb`.
