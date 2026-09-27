# AtividadeDio3
Analise de dados e machine learning


Este projeto utiliza técnicas de análise de dados e Machine Learning para identificar possíveis fraudes em transações de cartões de crédito, atividade proposta pela DIO.

O objetivo é treinar e comparar dois modelos de classificação capazes de identificar transações  que podem ser fraudes, utilizando dados históricos de operações financeiras de dados publicos.

Etapas do projeto
1. Importação dos dados

Os dados são carregados diretamente de um arquivo CSV disponibilizados pela professora em uma aula e carregados usando Pandas.
2. Análise exploratória dos dados

Nesta etapa, são verificadas as principais características do conjunto de dados, incluindo:

Quantidade de linhas e colunas.
Tipos de dados e estatísticas gerais.
Valores ausentes e registros duplicados.
Distribuição entre transações normais e fraudulentas.
A verificação ´[e feita por prints, head() e por graficos usando seaborn.

3. Preparação dos dados

Uma nova coluna chamada LogAmount é adicionada, aplicando uma transformação logarítmica ao valor das transações para facilitar o treinamento do modelo de maquina.

deposo os dados são separados em:

x: variáveis utilizadas para realizar as previsões.
y: variável que indica se a transação é normal ou fraudulenta.

4. Divisão dos dados

dividi o processo em 3 etapas:

Treinamento: utilizado para ensinar os modelos.
Validação: utilizado para comparar os resultados e ajustar o limiar de classificação.
Teste: reservado para a avaliação final dos modelos.

A divisão utiliza estratificação para preservar a proporção de transações fraudulentas e normais em cada valor.

5. Treinamento dos modelos

São utilizados dois algoritmos de classificação:

Regressão Logística

Modelo de classificação que utiliza probabilidades para estimar se uma transação é fraudulenta. É aplicado o StandardScaler para padronizar as variáveis.

Random Forest

Modelo que combina várias árvores de decisão para realizar classificações. Essa abordagem permite identificar padrões mais complexos nos dados.

Ambos utilizam configurações para lidar com o desequilíbrio entre as classes.

6. Ajuste do limiar de classificação

Os modelos geram probabilidades de uma transação ser fraudulenta.

Em vez de utilizar apenas o limite padrão de 50%, o código testa diferentes limiares utilizando os dados de validação.

O objetivo é encontrar o limiar que apresenta o melhor resultado na métrica F1-score, equilibrando precisão e capacidade de identificar fraudes.

7. Testes dos modelos

O código realiza verificações para garantir que:

Os dois modelos foram treinados corretamente.
As previsões possuem a quantidade esperada de registros.
As probabilidades geradas são válidas.
Os valores das probabilidades estão entre 0 e 1.

Foi testado tambem por final alguns requisitos complementares da atividade como undersampling e oversampling.
