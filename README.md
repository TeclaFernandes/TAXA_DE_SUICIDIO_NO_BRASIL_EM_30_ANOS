
# 💛 Análise de Taxa de Suicídios no Brasil e no Mundo

Este repositório contém um código de análise de dados de suicídios, com foco na comparação entre as taxas de suicídio no Brasil e no resto do mundo. Utiliza bibliotecas populares como Pandas, Numpy, Matplotlib e Seaborn para análise e visualização dos dados.

## 📌 Objetivo

O objetivo desta análise é explorar os dados de suicídios ao longo do tempo, analisar a relação com o PIB per capita e identificar padrões de suicídios em diferentes faixas etárias, sexos e gerações.

## 📎 Bibliotecas Utilizadas

- `pandas`: Para manipulação e análise de dados.
- `numpy`: Para cálculos numéricos.
- `matplotlib`: Para visualização gráfica.
- `seaborn`: Para visualizações avançadas.

## ✔ Etapas do Código

1. **Carregamento e Visualização Inicial dos Dados**:
   O código carrega o dataset de suicídios de um arquivo CSV hospedado no GitHub e exibe as primeiras linhas para revisão inicial.
   ```python
   df = pd.read_csv('https://raw.githubusercontent.com/carlosfab/data_science/master/datasets/suicide_rates.csv')
   df.head()
   ```

2. **Filtragem dos Dados para o Brasil**:
   O conjunto de dados é filtrado para conter apenas informações relativas ao Brasil.
   ```python
   df_brasil = df[df['country'] == 'Brazil'].copy()
   ```

3. **Análise de Dados Faltantes**:
   O código verifica se há valores ausentes (missing values) no conjunto de dados para o Brasil e para o mundo, ajudando a identificar possíveis problemas com os dados.
   ```python
   df.isnull().sum()
   ```

4. **Análise da Taxa de Suicídios ao Longo do Tempo**:
   São calculadas as médias de suicídios a cada 100 mil habitantes para o Brasil e para o mundo ao longo dos anos e comparadas em gráficos de linhas.
   ```python
   sns.lineplot(x=anos, y=suicidio_mundial_media, label='Mundial', color='blue')
   sns.lineplot(x=anos, y=suicidio_brasil_media, label='Brasil', color='green')
   ```

5. **Distribuição de Suicídios por Faixa Etária**:
   O código cria uma tabela pivot para visualizar os suicídios no Brasil por faixa etária e plota gráficos de barras para mostrar a distribuição por faixa etária.
   ```python
   tabela.plot.bar(stacked=True, figsize=(16, 8))
   ```

6. **Análise por Geração**:
   A quantidade de suicídios é analisada por geração (baby boomers, geração X, Y, etc.), com gráficos de barras para visualizar as tendências ao longo dos anos.
   ```python
   sns.countplot(x='generation', order=df_brasil['generation'].value_counts().index, data=df_brasil)
   ```

7. **Análise por Gênero**:
   A proporção de suicídios entre homens e mulheres é analisada e apresentada em um gráfico de pizza.
   ```python
   plt.pie(generos, labels=['MULHERES', 'HOMENS'], colors=cor_genero, autopct='%1.1f%%', shadow=True, startangle=90)
   ```

8. **Relação Entre PIB e Suicídios**:
   O código analisa a correlação entre o PIB per capita e a taxa de suicídios no Brasil, utilizando gráficos de dispersão (regressão) para identificar possíveis padrões.
   ```python
   sns.regplot(x=gdp_media_brasil, y=suicidio_brasil_media, data=df_brasil, color='green')
   ```

9. **Análise por Faixa Etária e Sexo**:
   O código calcula os suicídios por faixa etária e sexo, apresentando gráficos de barras para as comparações entre os grupos de mulheres e homens.
   ```python
   sns.barplot(x=m, y=mn)  # Para mulheres
   sns.barplot(x=h, y=hn)  # Para homens
   ```

## ✅ Resultados Esperados

- **Gráficos de tendências** ao longo do tempo para suicídios no Brasil e no mundo.
- **Análises detalhadas** sobre suicídios por faixa etária, sexo e geração.
- **Identificação de padrões** de suicídios no Brasil em comparação com o resto do mundo.
- **Correlação** entre PIB per capita e taxa de suicídios.

## ▶ Como Rodar

1. Clone o repositório:
   ```
   git clone <URL_DO_REPOSITORIO>
   ```
   
2. Instale as dependências necessárias:
   ```
   pip install -r requirements.txt
   ```

3. Execute o código em um ambiente Python para visualizar os gráficos e as análises.

## 🔖 Conclusão

Este projeto fornece uma visão detalhada da taxa de suicídios no Brasil e no mundo, com foco em fatores como faixa etária, sexo, geração e PIB per capita. Através de visualizações claras, é possível entender melhor como esses fatores se relacionam e influenciam a taxa de suicídios.

## 📄 Licença

Este projeto tem apenas fins educacionais e analíticos.
