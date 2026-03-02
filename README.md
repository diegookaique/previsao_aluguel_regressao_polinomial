# Projeto de Previsão de Aluguel utilizando Regressão Polinomial

## Visão Geral do Projeto
Este projeto tem como objetivo principal prever o valor do aluguel (`Valor_Aluguel`) de imóveis com base em sua metragem (`Metragem`) utilizando o modelo de Regressão Polinomial. A ideia é explorar como diferentes graus de polinômio afetam a capacidade do modelo de se ajustar aos dados e realizar previsões precisas.

## Conjunto de Dados
O conjunto de dados `df_imoveis` foi carregado a partir do arquivo `ALUGUEL_MOD12.csv`. As colunas mais relevantes para esta análise são:
- `Valor_Aluguel`: Variável target (dependente) que queremos prever.
- `Metragem`: Variável preditora (independente) utilizada para a previsão.

## Metodologia
A abordagem utilizada foi a Regressão Polinomial. O processo envolveu os seguintes passos:
1.  **Carregamento e Exploração dos Dados**: O DataFrame `df_imoveis` foi carregado e inspecionado para entender sua estrutura.
2.  **Seleção de Variáveis**: `Valor_Aluguel` foi definida como a variável dependente (`y`) e `Metragem` como a variável independente (`x`).
3.  **Transformação Polinomial**: A variável `Metragem` foi transformada usando `PolynomialFeatures` para criar características polinomiais.
4.  **Divisão em Conjuntos de Treino e Teste**: Os dados transformados foram divididos em conjuntos de treino e teste para avaliar o desempenho do modelo em dados não vistos (80% treino, 20% teste).
5.  **Treinamento do Modelo**: Um modelo de Regressão Linear (`LinearRegression`) foi treinado nos dados transformados e divididos.
6.  **Avaliação do Modelo**: O desempenho do modelo foi avaliado usando o coeficiente de determinação R² (`r2_score`).

### Experimento com `degree=2`
Inicialmente, o modelo de Regressão Polinomial foi construído com um grau de 2. Isso significa que a relação entre 'Metragem' e 'Valor_Aluguel' foi modelada como uma curva quadrática.
-   **R² obtido**: `0.5423`

### Experimento com `degree=4`
Em uma segunda etapa, o grau do polinômio foi aumentado para 4 para verificar se um modelo mais complexo poderia capturar melhor as relações nos dados.
-   **R² obtido**: `0.5596`

## Resultados e Conclusão

Ao comparar os resultados dos dois modelos, observamos:
-   **Modelo com `degree=2`**: R² = 0.5423
-   **Modelo com `degree=4`**: R² = 0.5596

Embora ambos os resultados sejam relativamente próximos, o modelo com `degree=4` apresentou um valor de R² ligeiramente superior (0.5596) em comparação com o modelo de `degree=2` (0.5423). Isso sugere que o polinômio de grau 4 conseguiu um ajuste marginalmente melhor aos dados, indicando que pode haver uma não linearidade um pouco mais complexa que este grau consegue capturar.

No entanto, o aumento no R² de grau 2 para grau 4 foi modesto, o que implica que, embora um grau superior possa melhorar o ajuste, a diferença não é drástica para este conjunto de dados específico. Em regressão polinomial, aumentar o grau permite que o modelo capture relações não lineares mais complexas, mas também aumenta o risco de *overfitting* (superajuste).

## Sugestões para Futuras Melhorias
Para uma avaliação mais robusta da superioridade do `degree=4` e para mitigar o risco de superajuste, sugere-se a aplicação de técnicas como a **validação cruzada**. A validação cruzada pode ajudar a avaliar o desempenho do modelo em diferentes subconjuntos dos dados, fornecendo uma estimativa mais confiável de sua capacidade de generalização.

## Bibliotecas Utilizadas
-   `pandas`: Para manipulação e análise de dados.
-   `numpy`: Para operações numéricas.
-   `matplotlib.pyplot` e `seaborn`: Para visualização de dados.
-   `plotly.express`: Para visualizações interativas (não utilizada na visualização final do notebook, mas importada).
-   `sklearn.linear_model.LinearRegression`: Para o modelo de regressão linear.
-   `sklearn.preprocessing.PolynomialFeatures`: Para transformação polinomial das características.
-   `sklearn.model_selection.train_test_split`: Para divisão dos dados em treino e teste.
-   `sklearn.metrics.r2_score`: Para avaliação do desempenho do modelo.


**Gostou da Análise?** Conecte-se para trocarmos experiências e ideias sobre projetos de dados!

🔗 **Meu LinkedIn:** [https://www.linkedin.com/in/diego-kaique-9ba3697b]

📧 **Contato:** [kaique_0208@hotmail.com]
