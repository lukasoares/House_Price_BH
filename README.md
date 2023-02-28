<h1>House_Price_BH</h1>
Tratamento de dados, análise exploratória, seleção e construção de um modelo para previsão de preços de imóveis em Belo Horizonte utilizando uma  <a href='https://www.kaggle.com/datasets/guilherme26/house-pricing-in-belo-horizonte'>base de dados disponibilizada no Kaggle</a>.

<p align = center> 
    <a href = '#objetivo'>Objetivo</a> •
    <a href = '#notebook1'>Notebook 1</a> •
    <a href = '#notebook2'>Notebook 2</a> •
    <a href = '#conclusão'>Conclusão</a>
</p>

<h2 id = 'objetivo'>Objetivo</h2>

O objetivo deste projeto foi colocar em prática o meu aprendizado no processo de machine learning relacionado a regressão. Passando desde tratamento dos dados, análise exploratória, escolha da melhor classe de modelo e seus hiper parâmetros, testes estatísticos de hipótese, validação final e avaliação dos resultados. Para isso foi escolhido uma base de dados da cidade que eu resido, Belo Horizonte, selecionando modelos de regressão como Random Florest Regressor, Gradient Booster Regressor, dentre outros.


<h3 id = 'notebook1'><a href='https://github.com/lukasoares/House_Price_BH/blob/main/Notebook_1%20_Tratamento_e_limpeza_dos_dados/Treatment_House_Pricing_BH.ipynb'>Notebook 1 - Tratamento e limpeza dos dados</a></h3>
Neste notebook se encontra todo o processo de tratamento dos dados. Desde da retirada de dados nulos ou inválidos, limpeza utilizando diversor recursos do Python,  Pandas e a remoção de erros de entrada utilizando box plots. Também neste notebook foi criado uma nova coluna "zones" que contém as regiões administrativas de cada bairro para facilitar ou até possibilitar
uma análise mais clara, já que a base de dados original não continha nenhuma variável qualitativa que possibilitasse um estudo por grupos.

<h3 id = 'notebook2'><a href='https://github.com/lukasoares/Real_Estate_Pricing_Model_BH/blob/main/Notebook_2%20_An%C3%A1lise_e_treinamento/Real_Estate_Price_Analysis_and_Training_BH.ipynb'>Notebook 2 - Análise Exploratória, Escolha de Modelo e Validação</a></h3>
<p>Nesta parte do projeito estão presentes análises gráficas do banco de dados, utilizando histogramas, box plots e gráficos de barras por agrupamentos regionais. Após essa etapa, foi efetuada a transformação logarítmica da variável dependente ou observável "price" e a vetorização das variáveis independentes categóricas ("one-hot").</p>
<img src ="https://user-images.githubusercontent.com/110298606/221657828-b65925b4-58a4-4611-8c8d-a5609568832a.png" width = 800px/> 
<p>Como parte do processo de avaliação de análise das variáveis foi realizado um teste de correlação de Pearson.</p>
<img src ="https://user-images.githubusercontent.com/110298606/221703057-bb241997-dee4-4c8b-865b-bffdf779573d.png"/>

<p>Com os dados transformados, utilizamos o método "Nested Cross Validation" para separar a base de dados entre treino e teste. O objetivo deste processo é manter a base de teste para a validação do modelo, enquanto a base de treino é usada para escolher a melhor classe de modelo com cross validation e para selecionar os melhores hiperparâmetros utilizando o GridSearchCV. Desta forma, é possível obter uma validação mais realista do modelo final.</p><p>Após o cross validation e o GridSearchCV, foram realizados testes estatísticos de hipótese de normalidade e média. A classe Gradient Boosting Regressor apresentou o melhor desempenho.</p>Em seguida, realizamos a validação final do modelo com o dataset de teste e obtivemos um resultado de R^2 = 0,84 e um RMSE = 420044,70. Também fizemos um estudo gráfico dos resíduos do modelo e um teste de normalidade, que teve resultado negativo, indicando a provável necessidade de melhorias.
<img src ="https://user-images.githubusercontent.com/110298606/221668460-178396d7-3977-4785-ae0d-ce5daab92a68.png" width = 800px/>

<h3 id = 'conclusão'>Conclusão</h3>

Apesar da limitação da base de dados com informações insuficientes sobre a estrutura do imóvel e uma distribuição geográfica não homogênea, com maior representatividade da Zona Centro-Sul, o resultado de 0,84 de R2 é considerado positivo, embora não ideal, devido a algumas anomalias e falhas no teste de resíduos. A inclusão de informações adicionais, como número de banheiros, quantidade de andares, materiais utilizados e idade do imóvel, juntamente com uma amostra maior de outras zonas, como Barreiro e Venda Nova, pode aprimorar significativamente o modelo.

Uma alternativa para aprimorar a distribuição de preços assimétrica seria criar um modelo de regressão específico para grupos de renda ou faixas de valores de imóveis. Além disso, foi observado que a influência das regiões no modelo de previsão de preços foi insignificante, exceto pela Zona Centro-Sul, que apresentou algum peso relevante de 0,1.



