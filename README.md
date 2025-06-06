# Prevejendo_Resistencia_do_Concreto
# Projeto de Previsão da Resistência do Concreto 🏗️📊

![Python](https://img.shields.io/badge/Python-3.9%2B-blue?style=flat&logo=python)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-0.24%2B-orange?style=flat&logo=scikit-learn)
![Pandas](https://img.shields.io/badge/Pandas-1.3%2B-lightgrey?style=flat&logo=pandas)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.4%2B-red?style=flat&logo=matplotlib)
![Seaborn](https://img.shields.io/badge/Seaborn-0.11%2B-purple?style=flat&logo=seaborn)
![Google Colab](https://img.shields.io/badge/Google%20Colab-Notebook-F9AB00?style=flat&logo=google-colab)

## Sobre o Projeto

Este repositório contém o desenvolvimento de um modelo de Machine Learning para prever a resistência à compressão do concreto. O projeto aborda um problema crucial na engenharia civil, onde a previsão precisa da resistência do concreto é vital para a segurança estrutural, otimização de custos e planejamento de projetos de infraestrutura.

O objetivo principal foi construir um modelo de regressão capaz de estimar a resistência do concreto com base em suas características de composição (como cimento, água, idade e outros agregados), permitindo otimizar processos produtivos e aumentar a eficiência técnica no setor da construção.

## Contexto do Desafio

Este projeto foi desenvolvido como parte de um desafio prático da **Matéria Modelos de Classificação e Regressão do curso de Cientista de Dados da DNC**. O objetivo era aplicar o pipeline completo de Machine Learning (da EDA à modelagem e avaliação) em um cenário real da engenharia de materiais.

## Dados

O conjunto de dados (`concrete_data.csv`) contém 2029 amostras de concreto, cada uma com 8 variáveis de entrada que descrevem a composição do material e 1 variável de saída que representa a resistência à compressão do concreto. As variáveis incluem:

* **Cimento** 
* **Escória de Alto Forno** 
* **Cinza Volante** 
* **Água** 
* **Superplastificante**
* **Agregado Graúdo**
* **Agregado Miúdo**
* **Idade**
* **Resistência Concreta**- *Variável Target*

## Estrutura do Projeto (Pipeline de MLOps)

O projeto seguiu um pipeline estruturado de desenvolvimento de Machine Learning, incluindo as seguintes etapas:

1.  **Análise Exploratória de Dados (EDA):**
    * Verificação de informações gerais do dataset (`.info()`).
    * Análise de correlações entre as variáveis e a variável alvo.
    * Visualização de distribuições (histogramas) e relações (gráficos de dispersão) para identificar padrões e potenciais outliers.
    * **Otimização:** Uso de funções para gerar gráficos de forma automatizada, reduzindo a repetição de código.

2.  **Pré-processamento e Tratamento de Dados:**
    * Verificação e tratamento de valores nulos (se existentes).
    * **Tratamento de Outliers:** Implementação de uma função para suavizar outliers utilizando o método do Intervalo Interquartil (IQR) para garantir dados mais robustos para a modelagem.
    * Padronização das features numéricas apenas para o modelo de Regressão Linear(utilizando `StandardScaler`).

3.  **Modelagem e Treinamento:**
    * Divisão dos dados em conjuntos de treino e teste (`train_test_split`).
    * **Construção de Pipelines:** Utilização de `sklearn.pipeline.Pipeline` para encadear os passos de pré-processamento (padronização) e modelagem, garantindo consistência e prevenindo *data leakage*.
    * **Modelos Implementados:**
        * `RandomForestRegressor` (com hiperparâmetros ajustados).
        * `LinearRegression`.

4.  **Avaliação dos Modelos:**
    * Cálculo das métricas de desempenho R² (Coeficiente de Determinação) e MAE (Erro Absoluto Médio) nos conjuntos de teste.
    * **Validação Cruzada:** Aplicação de `cross_val_score` (com 5 folds) para obter uma avaliação mais robusta e imparcial da performance dos modelos, verificando a generalização e a estabilidade.

5.  **Interpretabilidade e Previsão:**
    * **Interpretabilidade do Modelo:** Analisado a importância das variáveis no Random Forest, entendendo quais componentes são mais influentes na previsão da resistência.
    * **Simulação de Previsão:** Demonstração da capacidade do modelo de prever a resistência para uma nova combinação de componentes de concreto.

## Tecnologias Utilizadas

* `Python` (principalmente 3.9+)
* `pandas` para manipulação e análise de dados.
* `numpy` para operações numéricas.
* `matplotlib.pyplot` para visualizações estáticas.
* `seaborn` para visualizações estatísticas atraentes.
* `scikit-learn` para pré-processamento, modelagem (RandomForestRegressor, LinearRegression) e avaliação (r2_score, mean_absolute_error, cross_val_score, Pipeline, StandardScaler, train_test_split).
* Ambiente de Desenvolvimento: `Google Colab` (notebook Jupyter).

## Resultados e Conclusões
* **RandomForestRegressor:**
    * R² Médio (Validação Cruzada): 0.7724714237154728
    * MAE Médio (Validação Cruzada): 5.822189682445062
* **LinearRegression:**
    * R² Médio (Validação Cruzada): 0.5114922189755741
    * MAE Médio (Validação Cruzada): 9.319185240685417

O modelo de **Random Forest** demonstrou maior capacidade preditiva para este conjunto de dados, apresentando resultados mais robustos na validação cruzada. A interpretabilidade do mesmo forneceu insights valiosos sobre a influência de cada componente na resistência do concreto.

Este projeto reforçou a importância de um pipeline de ML bem estruturado e a aplicação de técnicas como validação cruzada e tratamento de outliers para construir modelos confiáveis e generalizáveis em cenários de engenharia.

## Autor

**Carlos Sotero**
* [LinkedIn](https://www.linkedin.com/in/carlos-sotero/)

## Licença

Este projeto está licenciado sob a licença MIT. Consulte o arquivo [LICENSE](LICENSE) para mais detalhes.
