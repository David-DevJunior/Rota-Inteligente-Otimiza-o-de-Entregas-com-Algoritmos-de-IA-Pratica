# Rota-Inteligente-Otimiza-o-de-Entregas-com-Algoritmos-de-IA-Pratica

**1. Descrição do problema, desafio proposto e objetivos.**

Com base no cenário apresentado, é possível identificar que os nossos serviços foram solicitados por uma pequena empresa de delivery denominada Sabor Express, cujas operações concentram-se principalmente na região central da cidade. Atualmente, a empresa enfrenta dificuldades significativas na gestão de seus pedidos e rotas de entrega, o que impacta diretamente sua eficiência operacional e a qualidade do serviço oferecido.

Um dos principais problemas relatados pelo proprietário está relacionado à ausência de rotas de entrega otimizadas. As rotas atualmente utilizadas pelos entregadores são definidas, em grande parte, com base na experiência individual de cada motorista, sem o apoio de tecnologias ou sistemas inteligentes capazes de auxiliar na escolha dos trajetos mais eficientes. Essa prática resulta em percursos mais longos, maior consumo de combustível e uso inadequado dos recursos disponíveis.

Além disso, observa-se a falta de um mecanismo de organização dos pedidos com base na distância entre os pontos de entrega, o que contribui para a definição de rotas ineficientes. Essa limitação pode comprometer a eficiência do processo de distribuição e a qualidade do serviço prestado. Como consequência, a empresa enfrenta diversos impactos negativos, tais como:

- Aumento no consumo de combustível;

- Elevação dos custos operacionais;

- Atrasos ocasionais nas entregas devido a rotas mal planejadas;

- Redução da satisfação dos clientes.

Diante desse contexto, propõe-se a criação de uma solução baseada em Inteligência Artificial, com o objetivo de servir como base para a otimização do processo de entregas da empresa. O modelo proposto terá como finalidade sugerir rotas mais eficientes para os entregadores, considerando principalmente a distância entre os pontos de origem e destino, permitindo a escolha dos caminhos de menor custo dentro da rede de entregas.

Como benefícios esperados com a implementação dessa solução, destacam-se a redução dos custos operacionais, a melhoria na eficiência das entregas, o uso mais racional dos recursos disponíveis e, consequentemente, o aumento da satisfação dos clientes, proporcionado por um serviço mais organizado, ágil e confiável.

**2. Explicação detalhada da abordagem adotada.**

Diante dessa problemática, foi proposta a construção de um algoritmo que fosse capaz de utilizar conceitos de inteligência artificial para auxiliar na análise e optimização de rotas de entrega, visando a redução das distâncias percorridas utilizadas pelos entregadores. Este Código foi desenvolvido com o intuito de simular o cenário real da empresa “Sabor Express” utilizado dados fictícios para validar a abordagem adotada.

Inicialmente, foi desenvolvido um DataFrame o qual contempla as coordenadas (x,y) de cada cliente localizado dentro da região de atuação da empresa. Estas são geradas de forma aleatória e representadas dentro de um plano cartesiano, onde o ponto de origem (0,0) corresponde ao restaurante. Dessa forma, cada item do DataFrame é tratado como um cliente que precisa receber uma entrega.

Seguidamente, os dados são organizados por meio de um processo de agrupamento denominado clustering. Com a utilização do algoritmo K-Means, o modelo de inteligência torna-se capaz de agrupar os clientes em diferentes zonas da região, permitindo uma melhor organização das entregas. O número de agrupamentos criados é equivalente ao número de motoristas disponíveis na empresa, possibilitando uma distribuição mais equilibrada das rotas de entrega. Dessa forma, cada centróide passa a representar uma região de atendimento, e os clientes são automaticamente associados ao centróide mais próximo, formando zonas como zona_0, zona_1 e zona_2.

Por fins didáticos, o projeto terá como foco de estudo a zona_0, permitindo a visualização detalhada do processo de otimização de rotas. A partir dessa zona, é construído um grafo exclusivo, no qual cada cliente é representado como um nó. Todos os nós são conectados entre si por meio de arestas, caracterizando um grafo completo. O peso de cada aresta corresponde à distância euclidiana entre dois clientes, calculada a partir de suas coordenadas (x, y). Essa modelagem possibilita a comparação entre diferentes distâncias e custos de deslocamento.

Seguidamente, foi definido um conjunto de variáveis fundamentais que auxiliam na organização e na construção do percurso do entregador dentro do grafo. Entre elas, podem-se destacar:

- rota_final: lista responsável por armazenar a sequência de coordenadas visitadas, incluindo o restaurante e todos os clientes atendido.

- visitados: estrutura que registra os clientes já atendidos, evitando repetições.

- atual: representa a posição atual do entregador durante a execução do algoritmo.

- distancia_total:armazena a distância total percorrida ao longo da rota.

Essas variáveis são constantemente atualizadas por meio de estruturas de repetição (for e while), permitindo que o algoritmo avalie, a cada passo, qual é o próximo cliente mais próximo ainda não visitado. A utilização da lista de clientes visitados é essencial para evitar ciclos infinitos e garantir que cada nó seja visitado apenas uma vez durante a construção da rota.

Por fim, foram construídos os gráficos responsáveis por apresentar visualmente todas as informações relacionadas às entregas a serem realizadas na região. Para isso, foram utilizadas diferentes ferramentas de formatação, como cores, legendas e rótulos, com o objetivo de facilitar a compreensão e a interpretação dos dados apresentados.

Por meio dessas visualizações, é possível identificar a localização dos diferentes clientes distribuídos pelas zonas definidas no processo de clustering, bem como observar de forma clara a rota de entrega otimizada atribuída ao motorista responsável pela zona_0, permitindo uma análise mais intuitiva e eficiente da solução proposta. 

Dessa forma, o algoritmo implementado permite uma visão clara e estruturada do problema de roteamento de entregas, combinando técnicas de clustering para a divisão territorial e a modelagem em grafos para o cálculo de trajetos eficientes. Essa abordagem contribui para a redução de custos operacionais, melhor aproveitamento dos entregadores disponíveis, diminuição do tempo e da distância percorrida nas entregas e maior eficiência no planejamento das rotas, resultando em um serviço mais ágil e confiável para os clientes.

**3. Algoritmos Utilizados.**

Para dar solução ao caso da empresa Sabor Express, foram utilizados diferentes algoritmos de agrupamento, busca e modelagem de dados, os quais serviram como base para a construção de uma ferramenta inteligente voltada ao apoio na análise e otimização de rotas de delivery na região de atuação da empresa. 

Assim entre os principais algoritmos utilizados podemos mencionar:

**Algoritmos de aleatoriedade:** Durante a construção do código, foram utilizados algoritmos de aleatoriedade para a geração das coordenadas de cada cliente, por meio de funções como np.random.seed(42) e np.random.uniform(). Além disso, foram definidos parâmetros fixos para representar a localização imutável do restaurante. A partir dessas ferramentas, foi possível criar uma simulação de uma situação real de delivery da empresa Sabor Express.

**Algoritmos de agrupamento K-Means:** Conforme mencionado anteriormente, a utilização do algoritmo K-Means possibilitou a criação de um gráfico para a visualização das entregas em zonas distintas. Essa organização permite que cada setor seja atribuído de forma estratégica aos motoristas, promovendo uma gestão de carga equilibrada e eficiente, o que evita a sobrecarga de encomendas para um único funcionário.

**Modelagem do problema:** Foram utilizadas técnicas de modelagem que permitem uma melhor visualização dos clientes e das distâncias entre eles, por meio da representação em nós e arestas. Essa abordagem facilita a compreensão das conexões entre os pontos de entrega e contribui para a análise dos possíveis percursos dentro de cada zona.

**Heurística gulosa do vizinho mais próximo:** Essa heurística tem como objetivo selecionar, a partir do ponto atual, o próximo cliente mais próximo que ainda não tenha sido visitado. O processo se repete até que todos os clientes da zona sejam atendidos, permitindo a construção de uma rota eficiente com base na menor distância percorrida em cada etapa.

Esses algoritmos auxiliam os entregadores na execução de suas principais atividades, permitindo uma melhor organização das entregas e a definição de percursos mais eficientes, considerando principalmente a distância entre os pontos. Como resultado, a solução contribui para a redução do tempo de deslocamento, do consumo de recursos e para o aumento da eficiência operacional do serviço de entregas.

**4. Diagrama do Grafo.**
Seguidamente apresentamos os resultados da modelagem de dados, destacando o agrupamento Kmeans e estruturas de grafos para a obtenção do melhor caminho.


