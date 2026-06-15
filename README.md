# Análise Experimental de Algoritmos no Problema do Caixeiro Viajante (TSP)

Este repositório contém o projeto prático desenvolvido para a disciplina de Análise de Algoritmos do Programa de Pós-graduação em Computação Aplicada. O objetivo central é analisar o comportamento de diferentes abordagens algorítmicas ao lidarem com o Problema do Caixeiro Viajante (TSP), avaliando o impacto da explosão combinatória em instâncias reais de mapeamento geográfico. O trabalho consiste em projetar, implementar e avaliar empiricamente o trade-off entre o tempo de execução e a qualidade da solução através de testes práticos com tamanhos de entrada ($N$) crescentes, utilizando como estudo de caso os pontos turísticos do município de Veranópolis (RS).

🎯 **O Problema de Otimização**

O Problema do Caixeiro Viajante consiste em encontrar a rota mais curta que visita um conjunto de $N$ localidades exatamente uma vez e retorna à coordenada de origem. Como encontrar a solução ótima global pertence à classe NP-difícil, este repositório explora e compara a viabilidade prática de uma abordagem exata clássica frente a uma alternativa heurística de tempo polinomial.

🔬 **Algoritmos Implementados e Comparados**

O projeto realiza um benchmark automatizado entre duas estratégias distintas de resolução:

1. Força Bruta (Busca Exaustiva)

2. Heurística do Vizinho Mais Próximo (Nearest Neighbor)

📊 **Metodologia de Experimentação e Análise**

O plano de testes foi estruturado no notebook para avaliar dinamicamente o impacto da escala do problema ($N$) variando o número de pontos turísticos de forma incremental até o limite crítico operacional da Força Bruta.

**Cenário de Testes (Instâncias Reais)**

Os algoritmos processam as coordenadas reais de latitude e longitude baseadas no mapeamento geográfico de Picolo (2021), incluindo pontos como a Ponte Ernesto Dornelles, Belvedere do Espigão, Capela São João Batista, entre outros.

**Métricas de Avaliação**

**Qualidade da Solução**: Média da menor distância linear cumulativa calculada para avaliar o distanciamento da heurística em relação à solução ótima global.

**Tempo de Execução**: Medição rigorosa em segundos (via biblioteca time) do tempo real de CPU gasto por cada algoritmo para traçar as curvas empíricas de escalabilidade.

🛠️ **Tecnologias e Dependências**

**Linguagem**: Python 3

**Manipulação de Dados**: pandas (para tabelamento de resultados e agrupamentos por qtd_pontos)

**Matemática e Loops**: math (distância euclidiana), itertools (permutações) e tqdm (monitoramento de progresso)

**Visualização**: matplotlib.pyplot (geração de gráficos de linhas e barras de desempenho) e plotly.graph_objects (renderização de scatter plots interativos sobre mapas)

🚀 **Como Executar o Projeto**

**Clone o repositório para a sua máquina local**:

git clone https://github.com/seu-usuario/tsp-analysis-comparison.git

**Instale as bibliotecas necessárias para a execução**:

pip install pandas matplotlib plotly tqdm notebook

**Inicie o ambiente do Jupyter**:

jupyter notebook Trabalho_1_Análise_de_Algoritmos.ipynb

Execute as células sequencialmente para visualizar o cálculo de rotas no mapa interativo e gerar os gráficos comparativos de tempo de execução e distâncias médias.

📖 **Referência Bibliográfica**

[1] D. L. Applegate, R. E. Bixby, V. Chvátal, W. J. Cook, The traveling
salesman problem: a computational study, in: The traveling salesman
problem, Princeton university press, 2011.
[2] G. Gutin, A. P. Punnen, The traveling salesman problem and its
variations, Vol. 12, Springer Science & Business Media, 2006.
[3] A. P. Picolo, R. S. da Silva, Aplicação do problema do caixeiro viajante
para determinação de rotas turísticas (2021).
[4] T. H. Cormen, C. E. Leiserson, R. L. Rivest, C. Stein, Introduction to
algorithms (3-rd edition), MIT Press and McGraw-Hill (2009).
[5] D. J. Rosenkrantz, R. E. Stearns, P. M. Lewis, II, An analysis of
several heuristics for the traveling salesman problem, SIAM journal
on computing 6 (3) (1977) 563–581.
