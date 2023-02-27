<h1>House_Price_BH</h1>
Tratamento, análise e modelo de preços de imóveis em Belo Horizonte utilizando uma base de dados disponibilizada no Kaggle.

<h2>Objetivo</h2>

O objetivo deste projeto é colocar em prática todo o meu aprendizado no processo de machine learning. Indo do tratamento dos dados, análise exploratória, escolha da melhor classe de modelo, seus hiper parametros, validação final e avaliação dos resultados. Para isso decide escolher uma base de dados da cidade que eu moro, Belo Horizonte, selecionando modelos de regressão como Random Florest, Gradient Booster, dentre outros, para poder prever preços de imóveis.


<h3>Notebook 1 - Tratamento e limpeza dos dados</h3>
Neste notebook se encontra todo o processo de tratamento dos dados. Desde da retirada de dados nulos ou inválidos, limpeza utilizando diversor recursos do Python e Pandas. Também foi feita a remoção de erros de entrada utilizando box plots. Também neste notebook foi criado uma nova coluna "zones" que contém as regiões administrativas de cada bairro para facilitar ou até possibilitar
uma análise mais clara, já que a base de dados original não continha nenhuma variável qualitativa que possibilitasse um estudo por grupos.

<h3>Notebook 2</h3>
<p>Aqui esta presente análises gráficas do banco de dados, utilizando histogramas, box plots e gráficos de barra por agrupamentos regionais. Após esta etapa, foi efetuada a transformação logarítima da variável dependente ou observável "price" e a vetorização das variáveis independentes ("one-hot") categóricas.</p>!![image](https://user-images.githubusercontent.com/110298606/221657828-b65925b4-58a4-4611-8c8d-a5609568832a.png)
 
<p>Com os dados transformados, foi utilizado o método "Nested Cross Validation" que separa a base de dados entre treino e teste. O objetivo deste processo, é manter a base de teste apenas para a validação do modelo, enquanto a base de treino é utilizada para a escolha da melhor classe de modelo com cross validation e para a escolha dos melhores hyper parametros utilizando GridSearchCV. Desta maneira é possível obter uma validação mais realista do modelo final.</p><p>Após o cross validation e GridSearchCV, foi feito testes estatísticos de hipótese de normalidade e de média e Gradient Boosting Regressor foi a classe que teve o melhor desempenho.</p>Chegamos então na validação  final do modelo com o dataset de teste e obteve um resultado de R^2 = 0.86 e um RMSE =400.00.
Também foi feito um estudo gráfico dos resídiuos do modelo e um teste de normalidade, tendo um resultado negativo nesse sentido e de provável necessidade de melhora.


