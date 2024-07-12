# Projeto de Análise Fundamentalista com Inteligência Artificial

## Observação
Não sou um especialista em ação isso é simplesmente um projeto para estudar ciencia de dados.
Esse código faz parte de um curso para entender a análise de dados e IA.
Projeto Inspiração: https://medium.com/swlh/teaching-a-machine-to-trade-stocks-like-warren-buffett-part-i-445849b208c6

## Introdução

Este projeto tem como objetivo utilizar a análise fundamentalista para a seleção de ações, empregando uma abordagem baseada em dados trimestrais. A proposta é fornecer informações consistentes à Inteligência Artificial (IA), permitindo que ela tome decisões informadas sobre quais empresas incluir em uma carteira de investimentos.

![Decisão](https://github.com/GustavoWMSilva/Imagens/blob/main/Decisao.png)
## Etapas do Projeto

### 1. Entendimento e Projeto

- Compreensão aprofundada do tema.
- Escolha da base de dados e definição dos cálculos necessários para o treinamento da IA.

### 2. Coleta de Dados

- Seleção de empresas listadas no índice Bovespa (77 códigos de ações).
  
![Fundamentos](https://github.com/GustavoWMSilva/Imagens/blob/main/Empresas.png)

- Utilização do FUNDAMENTUS, uma plataforma online, para obter informações financeiras e fundamentalistas, incluindo Balanço Patrimonial e Demonstrativo de Resultados (DRE) por trimestre.
- Cotações obtidas via Yahoo Finance para 65 empresas.
  
![Cotações](https://github.com/GustavoWMSilva/Imagens/blob/main/Cotacoes.png)


### 3. Análise Exploratória de Dados

- Utilização de visualizações para compreender a distribuição dos dados.
- Correção de problemas identificados e preparação dos dados para a IA.

### 4. Treinamento do Modelo

- Avaliação de diferentes modelos para escolher o mais adequado.
- Ajustes no modelo escolhido para otimizar o desempenho.
- Realização de previsões e testes práticos.

## Escolha das Empresas

A seleção das empresas é baseada nos códigos do índice Bovespa, totalizando 77 ações. As informações fundamentais e de cotação são cruciais para a IA decidir quais ações incluir na carteira, renovada trimestralmente.

## Definição da Forma de Análise

A padronização das informações é essencial. Analisamos o crescimento/descrecimento percentual dos fundamentos no segundo trimestre de 2020 em relação ao primeiro trimestre. Para evitar viés, o crescimento/descrecimento das cotações é avaliado do segundo trimestre para o terceiro.

![Base para Orientação](https://github.com/GustavoWMSilva/Imagens/blob/main/Orientacao.png)


![Exemplo](https://github.com/GustavoWMSilva/Imagens/blob/main/Relacao.png)


## Tratamento de Dados

Para criar um gabarito, comparamos o comportamento da cotação em relação ao Índice Bovespa. A feature selection reduziu as 47 informações para 10 fundamentos relevantes.

![Filtro](https://github.com/GustavoWMSilva/Imagens/blob/main/Relevantes.png)


## Criar Comparativo e Avaliação

Experimentos indicam que uma carteira aleatória pode superar estratégias complexas. Usamos um modelo Dummy como parâmetro mínimo. O objetivo é superar esse parâmetro, mesmo que ligeiramente, o que pode representar um ganho substancial no mundo das ações.

## Aplicação na Prática

Testar o modelo com um trimestre não visto pela IA é crucial. A validação com novas informações é a única maneira de avaliar seu desempenho real.
O resultado para o primeiro trimestre de 2021 foi de 10%

## Conclusão

Este projeto visa criar uma metodologia robusta para a seleção de ações, utilizando análise fundamentalista e IA. A abordagem sistemática, desde a coleta até o teste prático, busca maximizar o potencial de retorno nas decisões de investimento.

Vou criar um README.md baseado no que você descreveu e no exemplo do artigo.

---

# Detalhes - Análise de Fundamentos e Previsão de Ações

## Dependências
pip install pandas xlrd plotly seaborn scikit-learn yfinance pandas_datareader

## Descrição

Este projeto tem como objetivo analisar os fundamentos das empresas e prever o desempenho das ações utilizando técnicas de aprendizado de máquina. O pipeline de análise e previsão é baseado no artigo "I Built a Machine Learning Model to Trade Stocks Like Warren Buffett".

## Estrutura do Projeto

### Bloco 1: Criação de Dicionários de Dataframes

- **Objetivo:** Criar dataframes para cada empresa a partir dos balanços e DREs.
- **Descrição:** Os arquivos de balanços são lidos e processados para criar dataframes unificados contendo as informações financeiras de cada empresa.

### Bloco 2: Obtenção de Preços das Ações

- **Objetivo:** Carregar os preços das ações de um arquivo Excel e organizar os dados em um dicionário.
- **Descrição:** Os preços históricos das ações são obtidos e armazenados para cada empresa.

### Bloco 3: Remoção de Empresas com Cotações Vazias

- **Objetivo:** Garantir que apenas empresas com dados completos sejam analisadas.
- **Descrição:** Empresas com cotações vazias são removidas para manter a integridade dos dados.

### Bloco 4: Junção de Fundamentos com Preço da Ação

- **Objetivo:** Combinar os dados de fundamentos com os preços das ações.
- **Descrição:** Criação de uma tabela única para cada empresa que combina dados financeiros com preços de mercado.

### Bloco 5: Remoção de Colunas Inexistentes

- **Objetivo:** Garantir a consistência dos dados.
- **Descrição:** Remoção de colunas que não existem em todas as tabelas de fundamentos das empresas.

### Bloco 6: Ajuste de Colunas com o Mesmo Nome

- **Objetivo:** Evitar conflitos de nomes.
- **Descrição:** Renomeação de colunas duplicadas para garantir unicidade.

### Bloco 7: Análise de Valores Vazios nas Colunas

- **Objetivo:** Entender a qualidade dos dados.
- **Descrição:** Análise da quantidade de valores vazios em cada coluna das tabelas de fundamentos.

### Bloco 8: Remoção de Colunas com Muitos Valores Vazios e Preenchimento de Valores Faltantes

- **Objetivo:** Limpeza dos dados.
- **Descrição:** Remoção de colunas com muitos valores vazios e preenchimento de valores faltantes utilizando a técnica de forward fill.

### Bloco 9: Obtenção de Dados do IBOV

- **Objetivo:** Utilizar o IBOV como referência na análise.
- **Descrição:** Obtenção de dados históricos do IBOV a partir do Yahoo Finance.

### Bloco 10: Preparação dos Dados do IBOV

- **Objetivo:** Alinhar os dados do IBOV com os dados das empresas.
- **Descrição:** Preenchimento de valores faltantes e renomeação de colunas para consistência.

### Bloco 11: Cálculo de Variações Percentuais

- **Objetivo:** Analisar tendências e padrões de desempenho.
- **Descrição:** Cálculo das variações percentuais das colunas de fundamentos e dos preços das ações.

### Bloco 12: Remoção de Valores Vazios

- **Objetivo:** Garantir a integridade dos dados.
- **Descrição:** Remoção de valores vazios restantes nas tabelas de fundamentos.

### Bloco 13: Remoção de Colunas com Muitos Valores Vazios

- **Objetivo:** Reduzir a dimensionalidade dos dados.
- **Descrição:** Remoção de colunas com muitos valores vazios após o preenchimento.

### Bloco 14: Remoção de Colunas Não Utilizadas

- **Objetivo:** Simplificar o dataframe final.
- **Descrição:** Remoção de colunas que não serão utilizadas nas análises subsequentes.

### Bloco 15: Unificação de Dados em um Único DataFrame

- **Objetivo:** Análise conjunta dos dados.
- **Descrição:** Unificação dos dados de todas as empresas em um único dataframe.

### Bloco 16: Combinação de Dados de Todas as Empresas

- **Objetivo:** Criar uma base de dados consolidada.
- **Descrição:** Combinação dos dados de fundamentos de todas as empresas em um dataframe principal.

### Bloco 17: Análise Exploratória

- **Objetivo:** Entender a composição dos dados.
- **Descrição:** Análise exploratória dos dados, incluindo a distribuição das decisões de compra e venda.

### Bloco 18: Transformação de Categorias

- **Objetivo:** Simplificar a análise.
- **Descrição:** Transformação de categorias específicas.

### Bloco 19: Análise de Correlação

- **Objetivo:** Identificar relações entre variáveis.
- **Descrição:** Análise da correlação entre as variáveis do dataframe.

### Bloco 20: Remoção de Colunas Altamente Correlacionadas

- **Objetivo:** Evitar redundância.
- **Descrição:** Remoção de colunas que possuem alta correlação.

### Bloco 21: Seleção de Características

- **Objetivo:** Destacar variáveis importantes.
- **Descrição:** Utilização de um modelo de árvore de decisão para selecionar as características mais importantes.

### Bloco 22: Padronização dos Dados

- **Objetivo:** Melhorar o desempenho dos modelos.
- **Descrição:** Padronização dos dados para garantir que todas as variáveis tenham a mesma escala.

### Bloco 23: Separação dos Dados em Treino e Teste

- **Objetivo:** Preparar os dados para treinamento e avaliação.
- **Descrição:** Separação dos dados em conjuntos de treino e teste.

### Bloco 24: Modelo Dummy

- **Objetivo:** Estabelecer um baseline.
- **Descrição:** Treinamento e avaliação de um modelo dummy.

### Bloco 25: Avaliação dos Modelos de Machine Learning

- **Objetivo:** Comparar o desempenho dos modelos.
- **Descrição:** Treinamento e avaliação de diversos modelos de machine learning.

### Bloco 26: Tuning do Modelo

- **Objetivo:** Otimizar o desempenho do modelo.
- **Descrição:** Realização do tuning do modelo utilizando GridSearchCV.

### Bloco 27: Avaliação do Modelo Tunado

- **Objetivo:** Garantir desempenho superior.
- **Descrição:** Avaliação do desempenho do modelo tunado no conjunto de teste.

### Bloco 28: Preparação para o Último Trimestre

- **Objetivo:** Realizar previsões para o último trimestre.
- **Descrição:** Preparação dos dados do último trimestre para previsões.

### Bloco 29: Ajuste e Padronização dos Dados do Último Trimestre

- **Objetivo:** Garantir consistência dos dados.
- **Descrição:** Ajuste e padronização dos dados do último trimestre.

### Bloco 30: Previsões para o Último Trimestre

- **Objetivo:** Identificar oportunidades de investimento.
- **Descrição:** Realização de previsões para o último trimestre utilizando o modelo tunado.

### Bloco 31: Comparação com o IBOV

- **Objetivo:** Avaliar a eficácia das previsões.
- **Descrição:** Comparação das previsões de decisões com o desempenho do IBOV.

## Resultados

Os resultados incluem previsões de compra e venda para o último trimestre, avaliação dos modelos de machine learning utilizados, e comparação do desempenho das previsões com o índice de mercado IBOV.

## Conclusão

Este projeto demonstra como a análise de fundamentos e a previsão de ações podem ser realizadas utilizando técnicas de aprendizado de máquina. A abordagem é baseada em um pipeline estruturado e em práticas recomendadas descritas no artigo "I Built a Machine Learning Model to Trade Stocks Like Warren Buffett".

---
