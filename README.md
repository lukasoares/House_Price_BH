## House_Price_BH
Tratamento, análise e modelo de preços de imóveis em Belo Horizonte utilizando uma base de dados disponibilizada no Kaggle.

<h1>Objetivo</h1>
O objetivo deste projeto é colocar em prática todo o meu aprendizado no processo de machine learning. Indo do tratamento dos dados, análise, escolha de classe do melhor modelo, seus hiper parametros. Para isso decide escolher uma base de dados da cidade que eu moro, Belo Horizonte, selecionando modelos de regressão como Random Florest, Gradient Booster, dentre outros, para poder prever preços de imóveis.


<h2>Notebook 1 - Tratamento e limpeza dos dados</h2>
Neste notebook se encontra todo o processo de tratamento dos dados. Desde da retirada de dados nulos ou inválidos, limpeza e remoção com erro de entrada utilizando box plots. Também neste notebook foi criado uma nova coluna "zones" que contém as regiões administrativas de cada bairro para facilitar ou até possibilitar
uma análise mais clara, já que a base de dados original não continha nenhuma variável qualitativa que possibilitasse um estudo por grupos.



<h3>Notebook 2</h3>
Aqui esta presente análises gráficas do banco de dados, utilizando histogramas, box plots e gráficos de barra por agrupamentos regionais. Após esta etapa, foi efetuada a transformação logarítima da variável dependente ou observável "price" e a vetorização das variáveis independentes ("one-hot") categóricas. Com os dados transformados, foi utilizado o método "Nested Cross Validation" que separa a base de dados entre treino e teste. O objetivo deste processo, é manter a base de teste apenas para a validação do modelo, enquanto a base de treino é utilizada para a escolha da melhor classe de modelo com cross validation e para a escolha dos melhores hyper parametros utilizando GridSearchCV. Desta maneira é possível obter uma validação mais realista do modelo final.

As métricas escolhidas para a avaliação dos modelos foram R^2 e RMSE. Após efetuar o "cross validation" as classes que mais se saíram melhor foram Random Florest Regression e Gradient Booster Regression, com R^2 = 0.86 e 0.84 respectivamente.

Após a selecão dos 2 melhores modelos, chegou a hora de testar os melhores hiper parametros.

Com os hiperparametros escolhidos, chegou a hora de escolher o melhor modelo. O método utilizado foi 5x2 cross validation, que consiste em circo repetições para duas partições (k-fold = 2), dando um total amostral de 10 para cada classe de modelo. Após isso foi aplicado um teste de hipótese de normalidade para as duas amostras e com 95% de confiança as duas amostras provém de uma distribuição normal. Com isso em mãos foi efetuado o teste de média t-test para amostras dependentes unicaudal superior.

Com 95% de confiança Gradient Boost Regression tem estatisticamente uma média maior que Gradient Booster Regression para essa análise.

Com o melhor modelo e com seus melhores hiperparametros, foi feita a validação final. O resultado foi de R^2 = 0.86 e RMSE = 0.400 para essa base de teste.


