# Análise Preditiva de Preços de Imóveis

## 🏠 Visão Geral do Projeto

Este projeto tem como objetivo principal construir um modelo de Machine Learning capaz de prever os preços de venda de imóveis. O pipeline de Ciência de Dados foi executado de ponta a ponta, desde a análise exploratória e tratamento de dados até a otimização de modelos e a preparação para o deploy em produção.

## 📊 Estrutura e Etapas do Projeto

O projeto está organizado em seções que seguem as etapas de um fluxo de trabalho de Ciência de Dados.

### 1. Análise Exploratória de Dados (EDA) e Pré-processamento

- **Carregamento e Limpeza:** Os dados foram carregados, e os nomes das colunas foram traduzidos para o português para facilitar a manipulação.
- **Entendimento dos Dados:** Foram feitas análises detalhadas das dimensões (`.shape`), tipos de dados (`.info()`) e estatísticas descritivas (`.describe()`).
- **Tratamento de Dados Ausentes:** Estratégias foram implementadas para lidar com valores nulos, incluindo a remoção de colunas com alta porcentagem de dados faltantes e o preenchimento de valores com a moda para variáveis categóricas, e com a média para variáveis numéricas (como o `LotFrontage` com a média de vizinhanças).

### 2. Análise de Correlação e Visualização

- **Matriz de Correlação:** Uma matriz de correlação foi utilizada para identificar as variáveis mais relevantes para a previsão de preços.
- **Análise da Variável-Alvo:** A distribuição da variável `SalePrice` foi examinada, e uma transformação logarítmica foi aplicada para corrigir a assimetria.
- **Análise de Variáveis Chave:** Gráficos de dispersão e boxplots foram gerados para visualizar a relação entre o preço e as variáveis mais correlacionadas (`GrLivArea`, `OverallQual`, `GarageCars`, etc.), confirmando a presença de correlações lineares e a necessidade de pré-processamento.

### 3. Engenharia e Transformação de Atributos

- **Tratamento Específico:** Apliquei técnicas diferentes para cada tipo de variável, garantindo a qualidade do dataset.
- **Conversão de Variáveis Categóricas:** Usei o `One-Hot Encoding` para transformar variáveis categóricas em um formato numérico que os modelos pudessem processar.

### 4. Modelagem Preditiva

- **Modelos Utilizados:**
  - **XGBoost:** Um modelo poderoso e de alto desempenho, conhecido por sua eficiência.
  - **Regressão Linear:** Utilizado como baseline para comparação.
  - **Árvore de Decisão:** Um modelo mais simples, testado para fins comparativos.
- **Métrica de Avaliação:** O **Root Mean Squared Error (RMSE)** foi a métrica principal para avaliar a precisão de cada modelo.
- **Resultados Iniciais:**
  - XGBoost: RMSE de 0.134 (melhor desempenho)
  - Regressão Linear: RMSE de 0.155
  - Árvore de Decisão: RMSE de 0.208
- **Otimização de Hiperparâmetros:** O modelo XGBoost foi refinado com um **Hyperparameter Tuning**, reduzindo seu RMSE de **0.134** para **0.128**, provando a importância da otimização.

### 5. Próximos Passos (Pronto para o Deploy!)

- **Dashboard Interativo:** O próximo passo é criar um dashboard (`Streamlit` ou `Dash`) para apresentar as análises e o modelo de forma interativa a *stakeholders*.
- **Deploy do Modelo:** O modelo otimizado será empacotado e colocado em produção em um servidor na nuvem, como Heroku ou AWS, tornando-o acessível via API.

## 🛠️ Tecnologias e Bibliotecas

- `Python`
- `Pandas`
- `Numpy`
- `Matplotlib`
- `Seaborn`
- `Scikit-learn`
- `XGBoost`
