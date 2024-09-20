---

# Desafio 4: Construindo um Modelo de Regressão para Marketing

Este notebook apresenta a construção de um modelo de regressão linear para prever o retorno de vendas baseado em investimentos de marketing em três plataformas: YouTube, Facebook e jornal.

## Estrutura do Projeto

### 1. **Importações**
As bibliotecas utilizadas para o desenvolvimento e análise do modelo são:

- `pandas` para manipulação e análise de dados
- `seaborn` e `matplotlib` para visualizações
- `scikit-learn` para modelagem e métricas

### 2. **Carregamento dos Dados**
Os dados utilizados para treinar e avaliar o modelo estão no arquivo `MKT.csv`, que contém informações sobre os investimentos em marketing nas plataformas YouTube, Facebook e jornais, além das vendas geradas.

### 3. **Análise Exploratória e Descritiva**
Nesta etapa, são realizadas diversas análises para entender melhor os dados:

- Visualização de amostras dos dados com `.head()`
- Análise de tipos de dados e valores ausentes com `.info()` e `.isnull()`
- Estatísticas descritivas com `.describe()`
- Histogramas para verificar a distribuição dos investimentos por plataforma
- Análise de correlação entre as variáveis com `.corr()` e `sns.heatmap()`

Conclusões preliminares indicam que o investimento no YouTube traz o maior retorno em vendas, seguido pelo Facebook, enquanto o jornal apresenta o menor impacto.

### 4. **Modelagem**
#### 4.1 Divisão dos Dados
Os dados são divididos em variáveis independentes (`youtube`, `facebook`, `newspaper`) e a variável dependente (`sales`). Em seguida, são divididos em conjuntos de treino (70%) e teste (30%) para validação do modelo.

#### 4.2 Criação e Treinamento do Modelo
O modelo de regressão linear é criado e treinado com o conjunto de treino.

#### 4.3 Avaliação do Modelo
O modelo é avaliado usando a métrica `R²`, que indica o quão bem ele explica a variabilidade dos dados de teste.

### 5. **Teste de Acurácia**
Uma linha aleatória do dataset é utilizada para testar a acurácia do modelo. São comparados os valores reais e preditos para verificar a precisão das previsões do modelo.

## Conclusão
Através da análise exploratória e da construção do modelo de regressão, foi possível observar que a empresa deve focar seus investimentos nas plataformas YouTube e Facebook para maximizar o retorno em vendas.

---
