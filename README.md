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
