
---

# Desafio 4: Construindo um Modelo de Regressão para Marketing

Este notebook desenvolve um modelo de regressão linear para prever o retorno de vendas baseado em investimentos de marketing nas plataformas YouTube, Facebook e Jornal.

## Estrutura do Projeto

### 1. **Importações**
As bibliotecas utilizadas no desenvolvimento do modelo são:

- `pandas`: Manipulação e análise de dados
- `seaborn` e `matplotlib`: Visualização de dados
- `scikit-learn`: Modelagem e avaliação do modelo
- `random`: Para gerar valores aleatórios no teste de acurácia

### 2. **Carregamento dos Dados**
Os dados estão no arquivo `MKT.csv`, contendo informações sobre investimentos de marketing e vendas associadas. O arquivo é carregado com:

```python
MKT = pd.read_csv('MKT.csv', sep=',')
```

### 3. **Análise Exploratória e Descritiva**
Realiza-se uma análise inicial para entender a distribuição dos dados e verificar a correlação entre as variáveis.

#### 3.1 Análise Descritiva
Comandos principais:

- `MKT.head(10)`: Visualiza as primeiras 10 linhas do dataset
- `MKT.info()`: Verifica os tipos de dados e valores nulos
- `MKT.describe()`: Exibe estatísticas descritivas

Foram criados histogramas para examinar a distribuição dos investimentos nas plataformas.

#### 3.2 Análise Exploratória
- Correlação entre variáveis com `MKT.corr()`
- Mapa de calor da correlação com `sns.heatmap(MKT.corr())`

Observação: O investimento em YouTube tem o maior impacto nas vendas, seguido por Facebook e Jornal.

### 4. **Modelagem**
#### 4.1 Divisão dos Dados
As variáveis independentes (investimentos) e a dependente (vendas) são divididas:

```python
x = MKT[['youtube', 'facebook', 'newspaper']]
y = MKT['sales']
x_train, x_test, y_train, y_test = train_test_split(x, y, train_size=0.7, random_state=42)
```

#### 4.2 Criação e Treinamento do Modelo
O modelo de regressão linear é treinado com o conjunto de treino:

```python
LinearMKT = LinearRegression()
LinearMKT.fit(x_train, y_train)
```

#### 4.3 Avaliação do Modelo
O modelo é avaliado utilizando o `R²` para medir sua precisão:

```python
y_pred = LinearMKT.predict(x_test)
r2 = r2_score(y_test, y_pred)
print(f'R²: {r2:.2f}')
```

### 5. **Teste de Acurácia**
Testa-se o modelo com uma linha aleatória do dataset:

```python
linha_aleatoria = MKT.iloc[randint(0, 171)]
x_test_acur = [[318.24, 3.48, 51.60]]  # Valores de teste
y_test_acur = 15.24  # Valor real de vendas
y_test_acur_pred = LinearMKT.predict(x_test_acur)

print(f'Real: {y_test_acur}\nPredito: {y_test_acur_pred[0]:.2f}')
acuracidade = 100 - ((y_test_acur_pred / y_test_acur) * 100 - 100)[0]
print(f'Acuracidade: {acuracidade:.2f}%')
```

## Conclusão
A análise e o modelo sugerem que a empresa deve focar seus investimentos nas plataformas YouTube e Facebook para maximizar o retorno em vendas.

---
