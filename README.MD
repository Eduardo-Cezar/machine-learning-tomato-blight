# Predição da Severidade da Requeima em Tomateiros usando Imagens de Drones

Este repositório contém um notebook Python desenvolvido com o intuito prever o nível de severidade da doença **requeima** em tomateiros, utilizando imagens multiespectrais capturadas por drones. As bandas espectrais utilizadas incluem R (Red), G (Green), B (Blue), RE (Red Edge) e IR (Infra Red).

## Sobre a Requeima do Tomateiro

A **requeima** (causada pelo patógeno *Phytophthora infestans*) é uma das doenças mais devastadoras que afetam os tomateiros. Ela pode causar perdas significativas na produção agrícola, especialmente em condições de umidade e temperatura favoráveis ao desenvolvimento do fungo. Os sintomas incluem manchas escuras nas folhas, caules e frutos, que podem levar à morte da planta se não forem controlados a tempo.

### Impacto da Requeima:
- **Redução da produtividade**: A doença pode destruir grandes áreas de plantação em pouco tempo.
- **Custos elevados**: O controle da requeima geralmente requer a aplicação de fungicidas, o que aumenta os custos de produção.
- **Perdas econômicas**: Agricultores podem sofrer grandes perdas financeiras devido à redução da colheita.

### Como o Algoritmo Pode Ajudar:
O algoritmo desenvolvido neste projeto utiliza **imagens multiespectrais capturadas por drones** para prever o nível de severidade da requeima em tomateiros. Ao analisar as bandas espectrais (R, G, B, RE, IR), o algoritmo é capaz de identificar padrões associados à doença, mesmo antes que os sintomas visíveis apareçam.

#### Benefícios do Algoritmo:
1. **Detecção Precoce**: O algoritmo pode identificar a presença da doença em estágios iniciais, permitindo que os agricultores tomem medidas preventivas antes que a doença se espalhe.
2. **Monitoramento em Grande Escala**: Com o uso de drones, é possível monitorar grandes áreas de plantação de forma rápida e eficiente.
3. **Redução de Custos**: Ao detectar a doença precocemente, os agricultores podem aplicar fungicidas de forma mais precisa, reduzindo o uso excessivo de produtos químicos.
4. **Aumento da Produtividade**: Com um controle mais eficaz da requeima, a produtividade dos tomateiros pode ser mantida ou até mesmo aumentada.

### Como Funciona:
O algoritmo utiliza técnicas de **machine learning** para analisar as características extraídas das imagens multiespectrais. Através de modelos como **KNN**, **Random Forest**, **SVR**, **AdaBoost** e **GBM**, o algoritmo é capaz de prever a severidade da requeima com base nas features selecionadas. A otimização dos hiperparâmetros com **Grid Search CV** garante que o modelo tenha o melhor desempenho possível.


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

- **Regressão Linear**: A métrica **R² (Coeficiente de Determinação)** foi de **0.888**, indicando um bom ajuste do modelo aos dados, mas com espaço para melhorias.
- **KNN (K-Nearest Neighbors)**: O modelo KNN com 3 vizinhos alcançou um **R² de 0.911**, superando a regressão linear e demonstrando ser o modelo mais eficaz para este problema.
- **Random Forest**: Desempenho próximo ao KNN, mas com maior complexidade.
- **SVR (Support Vector Regression)**: Desempenho satisfatório, mas inferior ao KNN.
- **AdaBoost e GBM (Gradient Boosting Regressor)**: Desempenho inferior em comparação aos outros modelos.

### Interpretação das Métricas:
- **R² (Coeficiente de Determinação)**: Essa métrica varia de 0 a 1 e indica o quanto o modelo consegue explicar a variabilidade dos dados. Um valor próximo de 1 significa que o modelo consegue prever com alta precisão, enquanto um valor mais baixo indica que o modelo não está capturando bem a relação entre as variáveis.
  - **Regressão Linear (R² = 0.888)**: Um R² de 0.888 indica que o modelo de regressão linear explica 88.8% da variabilidade dos dados, o que é um bom resultado, mas ainda pode ser melhorado.
  - **KNN (R² = 0.911)**: Um R² de 0.911 mostra que o KNN explica 91.1% da variabilidade dos dados, sendo o modelo mais preciso para este problema.
