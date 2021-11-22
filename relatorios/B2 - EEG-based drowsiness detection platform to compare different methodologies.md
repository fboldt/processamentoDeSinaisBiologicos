# EEG-based drowsiness detection platform to compare different methodologies
Lucas Rigo Tofoli - 20211ceca0382

```
@article{ribeiro2017eeg,
  title={EEG-based drowsiness detection platform to compare different methodologies},
  author={Ribeiro, Daniel and Teixeira, C{\'e}sar and Cardoso, Alberto},
  booktitle={2017 4th Experiment@ International Conference (exp. at'17)},
  pages={318--322},
  year={2017},
  organization={IEEE}
}
```

## Do que se trata
Esse artigo estuda a criação de um sistema capaz de detectar sonolência a partir da análise de sinais de EEG (eletroencefalograma). O objetivo de criar esse sistema é de diminuir as chances de um acidente de trânsito, principalmente de veículos pesados na rodovia, que em 30% das vezes é causado pela sonolência do motorista.

### Extração de características

Mesmo que haja uma grande variedade de informações que podem ser extraídos do sinal de EEG, esse sistema utiliza apenas os que foram observados com os melhores resultados para se utilizar no classificador. Com isso, no domínio do tempo foram extraídos as características relacionadas a média, variância, assimetria e curtose do sinal. E no domínio da frequência, foram extraídos as características relacionadas aos coeficientes de Hjorth (mobilidade e complexidade), entropia, densidade do espectro de potência, potência média e as sub-bandas do EEG (alfa, beta, teta e delta).

### Classificação

Agora com todas as características definidas, elas foram usadas como entrada para criação e treinamento dos classificadores. Para realizar essa classificação foram utilizados:

- K-Nearest Neighbors (KNN): é um algoritmo de classificação que utiliza os k-neighbors mais próximos para determinar a qual classe aquele dado pertence, essa determinação é feita a partir da minimização de uma medida de semelhança. Sendo neste estudo 2 classes, "acordados" e "estado de sonolência".

- Redes Neurais Artificiais: são compostas por elementos simples que operam em paralelo, esses elementos correspondem a uma matemática representação de uma rede de neurônios em sistemas biológicos. Neste estudo foi utilizado várias combinações entre o número de camadas, neurônios e funções de ativação.

- Support Vector Machine (SVM): é um método de classificação onde um conjunto de dados de treinamento representando duas classes diferentes é projetada em um alto espaço dimensional por uma função de kernel. Neste estudo foram utilizadas 2 funções, Função de Base Radial Gaussiana e Perceptron multicamadas.

- Naive Bayes: é um classificador com modelo de probabilidade condicional, baseado no Teorema de Bayes, o qual assume que todos os eventos pertencem a uma classe única das classes existentes, apoiado em um conhecimento a priori que pode estar relacionado ao evento.

### Resultados

Ao utilizar o sistema, o usuário pode escolher entre os diferentes tipos de classificadores, o que consequentemente influencia em diferentes resultados. Isso ajuda a aprimorar o sistema, de forma a escolher uma configuração que apresente a melhor precisão.

No artigo foi apresentado o resultado de testes utilizando SVM com base radial kernel de função, possuindo assim 89,60% de precisão com delay 23 e 28,45% com delay 12.
