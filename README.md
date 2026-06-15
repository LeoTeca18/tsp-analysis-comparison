# Análise Experimental de Algoritmos no Problema do Caixeiro Viajante (TSP)

Este repositório contém o projeto prático desenvolvido para a disciplina de Análise de Algoritmos do Programa de Pós-graduação em Computação Aplicada. O objetivo central é analisar o comportamento de diferentes abordagens algorítmicas ao lidarem com o Problema do Caixeiro Viajante (TSP), avaliando o impacto da explosão combinatória em instâncias reais de mapeamento geográfico.O trabalho consiste em projetar, implementar e avaliar empiricamente o trade-off entre o tempo de execução (eficiência computacional) e a qualidade da solução (distância total da rota) através de testes práticos com tamanhos de entrada ($N$) crescentes, utilizando como estudo de caso os pontos turísticos do município de Veranópolis (RS).

🎯 **O Problema de Otimização**

O Problema do Caixeiro Viajante consiste em encontrar a rota mais curta (ciclo hamiltoniano de custo mínimo) que visita um conjunto de $N$ localidades exatamente uma vez e retorna à coordenada de origem.Como encontrar a solução ótima global pertence à classe NP-difícil, este repositório explora e compara a viabilidade prática de uma abordagem exata clássica frente a uma alternativa heurística de tempo polinomial.

🔬 **Algoritmos Implementados e Comparados**

O projeto realiza um benchmark automatizado entre duas estratégias distintas de resolução:

1. **Força Bruta (Busca Exaustiva)**
   
   **Estratégia**: Gera de forma explícita todas as permutações possíveis através da biblioteca itertools. Garante matematicamente a descoberta da rota ótima absoluta (menor distância possível).

   **Complexidade Assintótica**: Fatorial, $\mathcal{O}(N!)$ no tempo de execução.

   **Limitação**: Torna-se computacionalmente proibitivo para instâncias superiores a $10$ pontos devido à explosão combinatória de tempo e consumo de CPU.

2. **Heurística do Vizinho Mais Próximo (Nearest Neighbor)**
   
   **Estratégia**: Abordagem gulosa (greedy) construída iterativamente. A partir de um ponto de partida definido, o algoritmo seleciona sempre a próxima localidade não visitada que apresentar a menor distância euclidiana imediata.
   
   **Complexidade Assintótica**: Polinomial, $\mathcal{O}(N^2)$, devido à varredura sistemática das subjacências a cada tomada de decisão.

   **Vantagem/Desvantagem**: Execução instantânea mesmo em escalas maiores, contudo, o seu comportamento míope compromete o determinismo de otimalidade, gerando soluções subótimas (gaps de erro).

📊 **Metodologia de Experimentação e Análise**

O plano de testes foi estruturado no notebook para avaliar dinamicamente o impacto da escala do problema ($N$) variando o número de pontos turísticos de forma incremental até o limite crítico operacional da Força Bruta (NUMERO_MAXIMO_PONTOS_ANALISE = 10).

**Cenário de Testes (Instâncias Reais)**

Os algoritmos processam as coordenadas reais de latitude e longitude baseadas no mapeamento geográfico de Picolo (2021), incluindo pontos como a Ponte Ernesto Dornelles, Belvedere do Espigão, Capela São João Batista, entre outros.

**Métricas de Avaliação**

**Qualidade da Solução**: Média da menor distância linear cumulativa calculada para avaliar o distanciamento da heurística em relação à solução ótima global.

**Tempo de Execução**: Medição rigorosa em segundos (via biblioteca time) do tempo real de CPU gasto por cada algoritmo para traçar as curvas empíricas de escalabilidade.

📁 **Estrutura do Projeto**

O repositório está organizado de forma a garantir a perfeita reprodutibilidade dos experimentos analíticos:

├── Trabalho_1_Análise_de_Algoritmos.ipynb   # Jupyter Notebook com o código-fonte e gráficos integrados

├── TrabalhoI.pdf                           # Diretrizes e requisitos formais do projeto acadêmico

└── README.md                               # Documentação principal do repositório (este arquivo)

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

PICOLO, Ana Paula. Aplicação do Problema do Caixeiro Viajante para determinação de rotas turísticas. 2021. Trabalho de Conclusão de Curso (Tecnologia em Análise e Desenvolvimento de Sistemas) – Instituto Federal de Educação, Ciência e Tecnologia do Rio Grande do Sul (IFRS), Veranópolis, RS, 2021.
