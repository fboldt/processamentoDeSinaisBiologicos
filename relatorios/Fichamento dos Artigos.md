# Fichamento dos Artigos que utilizam a base de dados Sleep-EDF Database Expanded
Lucas Rigo Tofoli - 20211ceca0382

## EEG-based drowsiness detection platform to compare different methodologies
Esse artigo estuda a criação de um sistema capaz de detectar sonolência a partir da análise de sinais de EEG (eletroencefalograma). O objetivo de criar esse sistema é de diminuir as chances de um acidente de trânsito, principalmente de veículos pesados na rodovia, que em 30% das vezes é causado pela sonolência do motorista.

Extração de características para o classificador:

Mesmo que haja uma grande variedade de informações que podem ser extraídos do sinal de EEG, esse sistema utiliza apenas os que foram observados com os melhores resultados para se utilizar no classificador. Com isso, no domínio do tempo foram extraídos os recursos relacionados a média, variância, assimetria e curtose do sinal. E no domínio da frequência, foram extraídos os recursos relacionaos aos coeficientes de Hjorth (mobilidade e complexidade), entropia, densidade do espectro de potência, potência média e as sub-bandas do EEG (alfa, beta, teta e delta).

Classificação:

Agora com todas as características definidas, elas foram usadas como entrada para criação e treinamento dos classificadores. Para realizar essa classificação foram utilizados:

- K-Nearest Neighbors (KNN): é um algoritmo de classificação que utiliza os k-neighbors mais próximos para determinar a qual classe aquele dado pertence, essa determinação é feita a partir da minimização de uma medida de semelhança. Sendo neste estudo 2 classes, "acordados" e "estado de sonolência".

- Redes Neurais Artificiais: são compostas por elementos simples que operam em paralelo, esses elementos correspondem a uma matemática representação de uma rede de neurônios em sistemas biológicos. Neste estudo foi utilizado várias combinações entre o número de camadas, neurônios e funções de ativação.

- Support Vector Machine (SVM): é um método de classificação onde um conjunto de dados de treinamento representando duas classes diferentes é projetada em um alto espaço dimensional por uma função de kernel. Neste estudo foram utilizadas 2 funções, Função de Base Radial Gaussiana e Perceptron multicamadas.

- Naive Bayes: é um classificador com modelo de probabilidade condicional, baseado no Teorema de Bayes, o qual assume que todos os eventos pertencem a uma classe única das classes existentes, apoiado em um conhecimento a priori que pode estar relacionado ao evento.

Resultados:

Ao utilizar o sistema, o usuário pode escolher entre os diferentes tipos de classificadores, o que consequentemente influencia em diferentes resultados. Isso ajuda a aprimorar o sistema, de forma a escolher uma configuração que apresente a melhor precisão.

No artigo foi apresentado o resultado de testes utilizando SVM com base radial kernel de função, possuindo assim 89,60% de precisão com delay 23 e 28,45% com delay 12.


## Cepstrum Coefficients Based Sleep Stage Classification
Esse artigo faz um estudo do coeficiente cepstrum discriminativo dos sinais de EEG para classificação dos estágios do sono, utilizando o Support Vector Machine (SVM). Sendo os 3 estágios do sono, "Wake", "REM" e "NREM".

Extração de características para o classificador:

Os coeficientes de cepstrum são extraídos para formar um vetor de recursos para remover a redundância nos sinais de EEG. E então a extração segue os seguintes passos:

- As gravações do sinal de EEG são divididas em quadros de 30 segundos, e cada quadro é multiplicado por uma janela função para formar uma época.

- DFT (Discrete Fourier Transform) das épocas são calculadas e seu valor absoluto é alimentado para um conjunto de filtros com escala de frequência, assim capturando uma banda de frequência predefinida.

- Cada saída dos filtros é somada à frequência, e o logaritmo correspondente é calculado para obter a quantidade de energia das bandas para as quais o filtro é projetado.

- E então a DCT (Discrete Cosine Transform) dos valores de espectro do logaritmo são calculados para voltar ao domínio do tempo. Resultando nos coeficientes cepstrum para formar o vetor de recursos.

Classificação:

Para realizar a classificação dos estágios do sono, é utilizado o Support Vector Machine (SVM), que assim como escrito anteriormente ele é um método de classificação onde um conjunto de dados de treinamento representando duas classes diferentes, é projetada em um alto espaço dimensional. No caso desse estudo, não é possível separar linearmente os dados do treinamento, por isso o modelo do SVM pode ser mapeado para um espaço dimensional maior através da função de Kernel, criando assim um hiperplano no domínio transformado. O método utilizado para fazer a comparação e assim classificar foi o um contra um.

Resultados:

Neste estudo, os coeficientes cepstrum são considerados como características do sinal EEG. Já os filtros (triangular, Hamming e Hanning), normalização do filtro, escala de frequência, energia das épocas e derivadas de primeira e segunda ordem dos coeficientes são considerados como parâmetros de extração de recursos, melhorando assim a atuação do classificador.

A partir disso, observou-se que a melhor taxa de classificação é obtida para coeficientes cepstrum linear, utilizando banco de filtros Hamming normalizado e quando os recursos são aumentados com energia, coeficiente cepstrum de ordem zero e termos derivados, sendo assim  tendo como resultado uma precisão de 95,58%.

## Conclusão

Ambos os artigos estudam a base de dados Sleep-EDF Database Expanded como classificação, um dos artigos faz a análise separando em duas classes somente (acordado e sonolento) e o outro em três classes (awake, REM, NREM). Isso também demonstra que a base de dados pode ter diferentes pesquisas relacionadas ao seu conteúdo, utilizando diferentes métodos e classificadores.