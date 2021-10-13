# Base de Dados Sleep-EDF Database Expanded
Lucas Rigo Tofoli - 20211ceca0382

```
@article{kemp2000analysis,
  title={Analysis of a sleep-dependent neuronal feedback loop: the slow-wave microcontinuity of the EEG},
  author={Kemp, Bob and Zwinderman, Aeilko H and Tuk, Bert and Kamphuisen, Hilbert AC and Oberye, Josefien JL},
  journal={IEEE Transactions on Biomedical Engineering},
  volume={47},
  number={9},
  pages={1185--1194},
  year={2000},
  publisher={IEEE}
}
```

## Do que se trata a base de dados
A base de dados é composta por 197 polissonografias com gravações de noites inteiras de sono, possuindo EEG, EOG e EMG do queixo, além disso algumas gravações ainda possuem dados sobre a respiração, temperatura corporal e alguns marcadores de eventos.

Vale ressaltar que os hipnogramas ou os padrões de sono foram manualmente pontuados por profissionais treinados de acordo com o manual de Rechtschaffen e Kales.

EEG - Eletroencefalograma.

EOG - Eletrooculograma.

EMG - Eletromiograma.


## Como os dados foram adquiridos/coletados?
Os dados foram coletados a partir de dois diferentes estudos, o "Sleep Cassette Study and Data" e o "Sleep Telemetry Study and Data".

Sleep Cassette Study and Data: Dentre os 197 arquivos da base de dados, 153 fazem parte desse estudo e foram obtidos de 1987 a 1991 em adultos saudáveis de 25 a 101 anos de idade sem a utilização de medicamentos. Dois PSG's de 20 horas foram registrados de dia e de noite nos pacientes utilizando um aparelho durante todo o seu dia realizando as atividades cotidianas, o aparelho lembra um gravador de fita cassete do tipo walkman. Nesse estudo os sinais EOG e EEG foram amostrados em 100 Hz, e o sinal EMG passou por um filtro e uma retificação e depois amostrados em 1 Hz.

Sleep Telemetry Study and Data: Na base de dados em questão possuem 44 arquivos utilizando esse estudo e os seus registros foram coletados em 1994 sobre os efeitos do 'temazepam' no sono, os pacientes foram divididos entre 22 homens e 22 mulheres com esse único medicamento sendo utilizado. Os PSG's são de 9 horas durante duas noites, em uma noite após a ingestão do temazepam e na outra noite após a ingestão de placebo. Para esse estudo os sinais EOG, EMG e EEG foram amostrados em 100 Hz e os marcadores de eventos em 1 Hz.


## Qual o formato que os dados estão gravados?
As gravações da polissonografia (PSG) estão no formato EDF e os hipnogramas estão no formato EDF+. Cada arquivo desse possui um cabeçalho com detalhes da gravação, do paciente e algumas caracteristicas dos sinais (com calibração de amplitude).


## Quais são os resultados esperados quando se usa essa base?
Essa base de dados trás consigo um objetivo de apresentar um grande número de informações sobre alguns comportamentos do corpo humano durante as noites de sono através de uma polissonografia.

Dentre os dados da PSG está o EEG que analisa a atividade elétrica cerebral, o EOG analisa a diferença do impulso elétrico de repouso entre a córnea a região da retina, e o EMG que analisa as atividades de nervos periféricos e dos músculos, no caso dessa base o EMG analisará o queixo. Todos esses dados são representados em um gráfico.


## Qual é a performance reportada nos artigos mais relevantes que usam essa base? 
O acesso a muitos artigos que citam essa base de dados são pagos, porém em alguns é possível encontrar a eficiência do estudo no resumo. Os artigos utilizados como base foram os seguintes:

https://ieeexplore.ieee.org/document/7984343 - Este artigo faz um estudo sobre a relação entre acidentes de carro e a sonolência dos motoristas, para isso eles utilizam os sinais de EEG da base de dados, criando uma plataforma capaz de identificar o nível de sono. E a partir desse estudo eles obtiveram uma precisão de 89.5%.

https://ieeexplore.ieee.org/document/8308684 - Este estudo tem como objetivo obter o coeficiente de cepstrum discriminativo a partir dos sinais de EEG da base de dados e com isso classificar o estágio do sono. Foi utilizado o algoritmo SVM (Support Vector Machine), resultando em uma média de 95% de taxa de classificação correta do estágio do sono.

https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/iet-smt.2017.0240 - Diferente dos estudos anteriores, esse artigo propõe um novo método para monitoramento de distúrbios do sono com base em uma máquina de estado finito (FSM - finite-state machine) utilizando os sinais de EEG, EOG e EMG. Para obtenção dos resultados foram projetados dois módulos FSM, um para onda do sono e outro para identificar o estágio do sono. E a partir dessas informações obtiveram uma precisão de 99% para os casos de teste.


## Informações adicionais
Os arquivos dos estudos possuem uma nomenclatura para identificação:

Sleep Cassette: SC4ssNEO-PSG.edf

Sleep Telemetry: ST7ssNJ0-PSG.edf

Em ambas as nomenclaturas o 'ss' representa o número do sujeito e o 'N' representa a noite.
