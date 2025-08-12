
#  DSWA Agroimpact Challenge

Este projeto foi desenvolvido como parte de uma competição do Kaggle, com o objetivo de prever impactos ambientais com base em insumos agrícolas. Para preservar a confidencialidade dos dados da empresa, os nomes reais das colunas foram mantidos genéricos no notebook.

## Membros:
* Luis Felipi Cruz de Souza
* Felipe Bonadia de Oliveira Bravo

---

##  Etapas do Projeto

###  1. Análise Exploratória de Dados (EDA)

* Carregamento dos dados e inspeção inicial com .info() e .describe().
* Remoção da coluna feature1.
* Verificação de valores nulos (nenhum encontrado) e remoção de duplicatas.
* Análise de correlação entre as features e os alvos (targetX) com mapas de calor, para entender as relações entre variáveis.

###  2. Pré-processamento

* Separação do dataset em colunas de entrada (featureX) e colunas-alvo (targetX).
* Divisão entre conjunto de treino e teste com train_test_split.
* Padronização (normalização) dos dados utilizando StandardScaler para ambos os conjuntos de entrada e de saída.

###  3. Treinamento de Modelos

* Diversos modelos foram testados, incluindo:

  * **LinearRegression**
  * **Ridge**
  * **Lasso**
  * **ElasticNet**
  * **KNeighborsRegressor**
  * **DecisionTreeRegressor**
  * **RandomForestRegressor**
  * **GradientBoostingRegressor**
  * **ExtraTreesRegressor**
  * **SVR**
  * **MLPRegressor**
* Os modelos foram treinados usando MultiOutputRegressor, permitindo prever múltiplas variáveis de saída simultaneamente.
* Avaliação com cross_val_score e validação cruzada K-Fold.
* A métrica principal utilizada foi o **Mean Squared Error (MSE)**.
* Melhor resultado obtido foi com `ExtraTreesRegressor` 

###  4. Otimização com Optuna

* O Optuna foi utilizado para encontrar os melhores hiperparâmetros, com amostragem via TPESampler.
* A busca considerou parâmetros como número de estimadores, profundidade máxima e critérios de divisão para os modelos baseados em árvores.

###  5. Geração do Arquivo de Submissão

* Após o ajuste do modelo, foram feitas previsões no conjunto de teste real.
* Os resultados foram revertidos à escala original com inverse_transform e exportados em formato CSV para submissão no Kaggle.

---

##  Tecnologias e Bibliotecas

* Python
* Pandas & NumPy
* Matplotlib & Seaborn
* Scikit-learn
* Optuna

---
