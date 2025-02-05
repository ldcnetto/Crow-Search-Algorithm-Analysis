# Crow-Search-Algorithm-Analysis

Jupyter Notebook produzido para o projeto final da disciplina de Computação Bioinspirada

## Projeto Final - Comparação de Algoritmos de Otimização

Este projeto compara o desempenho do Crow Search Algorithm (CSA) e algumas de suas variantes (Advanced CSA e Variable Step CSA) com um Algoritmo Genético (GA) e uma Estratégia Evolutiva (ES) em quatro funções de benchmark: Ackley, Rastrigin, Schwefel e Rosenbrock. O objetivo é analisar a eficácia de cada algoritmo na busca pelo mínimo global dessas funções.

## Algoritmos Implementados

### 1. Algoritmo Genético (GA)

O GA implementado utiliza os seguintes parâmetros:

- **Tamanho da População:** 100
- **Número de Dimensões:** 30
- **Mutação:** Gaussiana, com taxa de 25%
- **Crossover:** One Point Crossover, com taxa de 75%
- **Seleção de Parentes:** Roleta
- **Seleção de Sobreviventes:** Ranking de Fitness
- **Taxa de Natalidade:** 10% por geração
- **Número de Gerações:** 500

O algoritmo simula a evolução natural, onde indivíduos (soluções candidatas) são selecionados, cruzados e mutados ao longo das gerações, buscando soluções cada vez melhores.

### 2. Estratégia Evolutiva (ES)

A ES implementada utiliza a estratégia (λ, μ), com os seguintes parâmetros:

- **Número de Dimensões:** 30
- **μ (Tamanho da População de Pais):** 25
- **λ (Tamanho da População de Filhos):** 5 \* μ
- **Número de Gerações:** 500
- **Sigma Inicial:** 10 (Ajustado dinamicamente)
- **Mutação:** CMA-ES (Covariance Matrix Adaptation Evolutionary Strategy) - A matriz de covariância é ajustada dinamicamente com base no desempenho das soluções.

A ES gera filhos através de mutação e seleciona os melhores indivíduos para a próxima geração, iterativamente refinando as soluções. A adaptação da matriz de covariância no CMA-ES auxilia na busca direcionada pelo mínimo.

### 3. Crow Search Algorithm (CSA)

O CSA é um algoritmo de otimização baseado no comportamento inteligente de corvos em esconder e procurar comida. Ele simula o comportamento de um bando de corvos que escondem comida em caches e a recuperam posteriormente. Os corvos aprendem com os outros e tentam roubar comida dos caches dos outros. O algoritmo utiliza memória para lembrar a localização dos melhores caches encontrados.

- **Tamanho da População:** 20
- **Número de Dimensões:** 30
- **Probabilidade de Consciência (AP):** 0.5
- **Comprimento do Voo (fl):** 2
- **Número de Gerações:** 500

### 4. Advanced CSA (ACSA)

O ACSA é uma variante do CSA com uma estratégia de passo variável. Esta variante melhora a capacidade de exploração e o desempenho de convergência do algoritmo original ao introduzir um mecanismo de ajuste de parâmetros adaptativo. Ele ajusta dinamicamente a probabilidade de consciência (AP) e o comprimento do voo (fl) ao longo das iterações.

- **Tamanho da População:** 20
- **Número de Dimensões:** 30
- **Probabilidade de Consciência Máxima (APmax):** 0.6
- **Probabilidade de Consciência Mínima (APmin):** 0.4
- **Fator de Ajuste de Alcance (FAR):** 0.2
- **Comprimento do Voo (fl):** 2
- **Parâmetro de Perturbação (pd):** 0.5
- **Número de Gerações:** 500

### 5. Variable Step CSA (VSCSA)

O VSCSA é outra variante do CSA que emprega um comprimento de voo variável baseado em cossenos, adaptando-se durante a busca. Este ajuste dinâmico auxilia o algoritmo a equilibrar entre exploração e explotação do espaço de busca.

- **Tamanho da População:** 20
- **Número de Dimensões:** 30
- **Probabilidade de Consciência (AP):** 0.5
- **Número de Gerações:** 500

## Como Executar o Código

1. **Certifique-se de ter as bibliotecas necessárias instaladas:**

   ```bash
   pip install numpy plotly matplotlib rich seaborn
   ```

2. **Execute o notebook `Projetos_Estratégia_Evolutiva.ipynb`:**

   Você pode executar o notebook célula por célula ou executá-lo por completo. O código irá gerar gráficos e exibir resultados na saída padrão para cada função de benchmark e cada algoritmo, permitindo a comparação do desempenho.

## Análise dos Resultados

O código coleta dados sobre o melhor fitness, o fitness médio e o desvio padrão do fitness ao longo das iterações/gerações e execuções. Os gráficos gerados permitem a visualização e comparação do desempenho de cada algoritmo em cada função. A análise desses dados permite determinar qual algoritmo obteve os melhores resultados em termos de encontrar o mínimo global e a consistência ao longo de múltiplas execuções.
