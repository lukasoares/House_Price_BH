## House_Price_BH
Tratamento, análise e modelo de preços de imóveis em Belo Horizonte utilizando uma base de dados disponibilizada no Kaggle.

##Objetivo
O objetivo deste projeto é colocar em prática todo o meu aprendizado no processo de machine learning. Indo do tratamento dos dados, análise, escolha de classe do melhor modelo, seus hiper parametros. Para isso decide escolher uma base de dados da cidade que eu moro, Belo Horizonte, selecionando modelos de regressão como Random Florest, Gradient Booster, dentre outros, para poder prever preços de imóveis.


##Notebook 1
Neste notebook se encontra todo o processo de tratamento dos dados. Desde da retirada de dados nulos ou inválidos, limpeza e remoção com erro de entrada utilizando box plots. Também neste notebook foi criado uma nova coluna "zones" que contém as regiões administrativas de cada bairro para facilitar ou até possibilitar
uma análise mais clara, já que a base de dados original não continha nenhuma variável qualitativa que possibilitasse um estudo por grupos.




##Notebook 2
Aqui esta presente análises gráficas do bando de dados, utilizando histogramas, box plots e gráficos de barra por agrupamentos regionais. Após esta etapa, foi efetuada a transformação logarítima da variável dependente ou observável "price" e a vetorização das variáveis independentes ("one-hot") categóricas. Com os dados transformados, foi utilizado o método "Nested Cross Validation" que separa a base de dados entre treino e teste. O objetivo deste processo, é manter a base de teste apenas para a validação do modelo, enquanto a base de treino é utilizada para a escolha da melhor classe de modelo utilizando cross validation e para a escolha dos melhores hyper parametros utilizando GridSearchCV. Desta maneira é possível obter uma validação mais realista do modelo final. 
