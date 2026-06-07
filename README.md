# Análise de Algoritmos Aproximativos: Estudo de Caso no Problema do Caixeiro Viajante (TSP)

Este repositório contém o projeto prático desenvolvido para a disciplina de **Análise e Projeto de Algoritmos**. O objetivo central é analisar o comportamento de **algoritmos aproximativos** ao lidarem com o **Problema do Caixeiro Viajante (TSP)**, que pertence à classe NP-difícil, inviabilizando soluções exatas em tempo útil para grandes instâncias.

O trabalho consiste em projetar, implementar e avaliar o *trade-off* entre o tempo de execução (eficiência computacional) e a qualidade da solução (distância total da rota) através de experimentos práticos com tamanhos de entrada ($N$) crescentes.

---

## 🎯 O Problema de Otimização

O Problema do Caixeiro Viajante consiste em encontrar a rota mais curta (ciclo hamiltoniano de custo mínimo) que visita um conjunto de $N$ cidades exatamente uma vez e retorna à cidade de origem. 

Como encontrar a solução ótima global exige tempo exponencial, este repositório explora abordagens aproximativas que entregam soluções satisfatórias em **tempo polinomial**.

---

## 🔬 Algoritmos Implementados e Comparados

O projeto realiza o benchmark entre duas estratégias de resolução:

### 1. Heurística do Vizinho Mais Próximo (*Nearest Neighbor*) - Baseline
* **Estratégia:** Algoritmo aproximativo baseado em uma abordagem gulosa (*greedy*). A partir de um ponto inicial, escolhe iterativamente a cidade não visitada mais próxima.
* **Complexidade Assintótica:** $\mathcal{O}(N^2)$ devido à necessidade de varrer a matriz de distâncias a cada escolha.
* **Vantagem/Desvantagem:** Execução extremamente rápida, mas propensa a soluções subótimas devido ao comportamento míope da estratégia.

### 2. Otimização por Colônia de Formigas (*Ant Colony Optimization - ACO*)
* **Estratégia:** Meta-heurística aproximativa bio-inspirada. Utiliza uma colônia de agentes (formigas virtuais) que constroem caminhos probabilisticamente com base em uma matriz de feromônios e informações heurísticas locais.
* **Complexidade Assintótica:** $\mathcal{O}(I \cdot A \cdot N^2)$, onde $I$ é o número de iterações e $A$ o número de agentes.
* **Vantagem/Desvantagem:** Oferece rotas significativamente mais curtas por evitar ótimos locais, exigindo maior tempo de processamento computacional.

---

## 📊 Metodologia de Experimentação e Análise

O plano de testes foi estruturado para avaliar o impacto da escala do problema no comportamento dos algoritmos, variando o número de cidades ($N$) de forma incremental.

### Métricas de Avaliação
* **Qualidade da Solução:** Distância total do circuito gerado para estimar implicitamente o fator de aproximação ($\rho$).
* **Tempo de Execução:** Mensuração do tempo absoluto de CPU gasto para alcançar a solução, permitindo traçar as curvas empíricas de crescimento em paralelo com a análise de complexidade teórica.

---

## 📁 Estrutura do Projeto

## 🚀 Como Executar
