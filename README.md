<h1>House_Price_BH</h1>
Tratamento de dados, análise exploratória, seleção e construção de um modelo para previsão de preços de imóveis em Belo Horizonte utilizando uma  <a href='https://www.kaggle.com/datasets/guilherme26/house-pricing-in-belo-horizonte'>base de dados disponibilizada no Kaggle</a>.

<p align = center> 
    <a href = '#objetivo'>Objetivo</a> •
    <a href = '#notebook1'>Notebook 1</a> •
    <a href = '#notebook2'>Notebook 2</a> •
    <a href = '#conclusão'>Conclusão</a>
</p>

<h2 id = 'objetivo'>Objetivo</h2>

O objetivo deste projeto foi colocar em prática o meu aprendizado no processo de machine learning relacionado a regressão. Passando desde tratamento dos dados, análise exploratória, escolha da melhor classe de modelo e seus hiper parâmetros, testes estatísticos de hipótese, validação final e avaliação dos resultados. Para isso foi decidido escolher uma base de dados da cidade que eu moro, Belo Horizonte, selecionando modelos de regressão como Random Florest Regressor, Gradient Booster Regressor, dentre outros.


<h3 id = 'notebook1'><a href='https://github.com/lukasoares/House_Price_BH/blob/main/Notebook_1%20_Tratamento_e_limpeza_dos_dados/Treatment_House_Pricing_BH.ipynb'>Notebook 1 - Tratamento e limpeza dos dados</a></h3>
Neste notebook se encontra todo o processo de tratamento dos dados. Desde da retirada de dados nulos ou inválidos, limpeza utilizando diversor recursos do Python e Pandas. E a remoção de erros de entrada utilizando box plots. Também neste notebook foi criado uma nova coluna "zones" que contém as regiões administrativas de cada bairro para facilitar ou até possibilitar
uma análise mais clara, já que a base de dados original não continha nenhuma variável qualitativa que possibilitasse um estudo por grupos.

<h3 id = 'notebook2'>Notebook 2 - Análise dos dados e seleção do melhor modelo de regressão</h3>
<p>Aqui esta presente análises gráficas do banco de dados, utilizando histogramas, box plots e gráficos de barra por agrupamentos regionais. Após esta etapa, foi efetuada a transformação logarítima da variável dependente ou observável "price" e a vetorização das variáveis independentes ("one-hot") categóricas.</p>
<img src ="https://user-images.githubusercontent.com/110298606/221657828-b65925b4-58a4-4611-8c8d-a5609568832a.png" width = 800px/> 
 
<p>Com os dados transformados, foi utilizado o método "Nested Cross Validation" que separa a base de dados entre treino e teste. O objetivo deste processo, é manter a base de teste apenas para a validação do modelo, enquanto a base de treino é utilizada para a escolha da melhor classe de modelo com cross validation e para a escolha dos melhores hyper parametros utilizando GridSearchCV. Desta maneira é possível obter uma validação mais realista do modelo final.</p><p>Após o cross validation e GridSearchCV, foi feito testes estatísticos de hipótese de normalidade e de média. Gradient Boosting Regressor foi a classe que teve o melhor desempenho.</p>Chegamos então na validação  final do modelo com o dataset de teste e obteve um resultado de R^2 = 0.84 e um RMSE =420044.70.
Também foi feito um estudo gráfico dos resídiuos do modelo e um teste de normalidade, tendo um resultado negativo nesse sentido e de provável necessidade de melhora.
<img src ="https://user-images.githubusercontent.com/110298606/221668460-178396d7-3977-4785-ae0d-ce5daab92a68.png" width = 800px/>

<h3 id = 'conclusão'>Conclusão</h3>



