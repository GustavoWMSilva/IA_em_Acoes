# Projeto de Análise Fundamentalista com Inteligência Artificial

## Introdução

Este projeto tem como objetivo utilizar a análise fundamentalista para a seleção de ações, empregando uma abordagem baseada em dados trimestrais. A proposta é fornecer informações consistentes à Inteligência Artificial (IA), permitindo que ela tome decisões informadas sobre quais empresas incluir em uma carteira de investimentos.

## Etapas do Projeto

### 1. Entendimento e Projeto

- Compreensão aprofundada do tema.
- Escolha da base de dados e definição dos cálculos necessários para o treinamento da IA.

### 2. Coleta de Dados

- Seleção de empresas listadas no índice Bovespa (77 códigos de ações).
- Utilização do FUNDAMENTUS, uma plataforma online, para obter informações financeiras e fundamentalistas, incluindo Balanço Patrimonial e Demonstrativo de Resultados (DRE) por trimestre.
- Cotações obtidas via Yahoo Finance para 65 empresas.

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

## Tratamento de Dados

Para criar um gabarito, comparamos o comportamento da cotação em relação ao Índice Bovespa. A feature selection reduziu as 47 informações para 10 fundamentos relevantes.

## Criar Comparativo e Avaliação

Experimentos indicam que uma carteira aleatória pode superar estratégias complexas. Usamos um modelo Dummy como parâmetro mínimo. O objetivo é superar esse parâmetro, mesmo que ligeiramente, o que pode representar um ganho substancial no mundo das ações.

## Aplicação na Prática

Testar o modelo com um trimestre não visto pela IA é crucial. A validação com novas informações é a única maneira de avaliar seu desempenho real.

## Conclusão

Este projeto visa criar uma metodologia robusta para a seleção de ações, utilizando análise fundamentalista e IA. A abordagem sistemática, desde a coleta até o teste prático, busca maximizar o potencial de retorno nas decisões de investimento.
