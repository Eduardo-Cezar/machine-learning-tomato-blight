# Predição da Severidade da Requeima em Tomateiros usando Imagens de Drones

Este repositório contém um notebook Python desenvolvido para prever o nível de severidade da doença **requeima** em tomateiros, utilizando imagens multiespectrais capturadas por drones. As bandas espectrais utilizadas incluem R (Red), G (Green), B (Blue), RE (Red Edge) e IR (Infra Red).

O objetivo do projeto é aprimorar um algoritmo de machine learning para prever a severidade da requeima com base nas características extraídas das imagens.

## Descrição do Projeto

O projeto utiliza técnicas de machine learning para prever a severidade da requeima em tomateiros. O código original foi aprimorado com a implementação de vários algoritmos de regressão, como **SVR**, **Random Forest**, **KNN**, **AdaBoost** e **GBM (Gradient Boosting Regressor)**. Além disso, foi utilizado o **Grid Search CV** para otimizar os hiperparâmetros de cada algoritmo.

### Métricas Utilizadas:
- **Validação Cruzada**: Para avaliar o desempenho dos modelos.
- **Seleção de Features**: Utilizando **RFE (Recursive Feature Elimination)** para selecionar as features mais relevantes.

## Estrutura do Código

O notebook está organizado da seguinte forma:

1. **Introdução**: Apresentação do problema e dos dados.
2. **Metodologia**:
   - Divisão dos dados em treino e teste.
   - Padronização dos dados com `Standard Scaler`.
   - Seleção de features com **RFE**.
   - Aplicação de validação cruzada em um modelo de regressão linear.
3. **Implementações**:
   - **SVR (Support Vector Regression)**: Ajuste de hiperparâmetros com Grid Search.
   - **Random Forest**: Ajuste de hiperparâmetros para regressão.
   - **KNN (K-Nearest Neighbors)**: Variação do número de vizinhos.
   - **AdaBoost**: Ajuste de parâmetros para regressão.
   - **GBM (Gradient Boosting Regressor)**: Ajuste de hiperparâmetros.
4. **Comparação de Modelos**: Comparação dos desempenhos dos algoritmos utilizando validação cruzada.
5. **Resultados**: Discussão dos resultados obtidos com os diferentes modelos.

## Resultados

O algoritmo **KNN** com 3 vizinhos mais próximos obteve o melhor desempenho de acordo com a métrica de validação cruzada. Abaixo estão os principais resultados:

- **KNN**: Melhor desempenho com 3 vizinhos.
- **Random Forest**: Desempenho próximo ao KNN, mas com maior complexidade.
- **SVR**: Desempenho satisfatório, mas inferior ao KNN.
- **AdaBoost e GBM**: Desempenho inferior em comparação aos outros modelos.
