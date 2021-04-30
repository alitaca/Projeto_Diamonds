# Projeto Diamonds

O Projeto Diamonds foi criado com o objetivo de gerar uma previsão de preços de 5000 diamantes a partir de uma base de dados de vendas de diamantes disponível.

## Começando

Rick tem 5000 diamantes e precisa de uma avaliação para cada um dos diamantes.

## Testando

O objetivo é obter uma previsão que obtenha o menor erro calculado pelo RMSE (Root Mean Square Error).

O site que faz a avaliação dos resultados está em:

* [diamonds](https://daft-oct2020-rick-diamonds.herokuapp.com/)

### Pré-requisitos

Navegador Web
Jupiter Notebook

## Desenvolvimento

### Conhecendo os dados

A base de dados a ser utilizada para a criação do modelo é dada conforme a seguir:


| Coluna  | Descrição  |
|---|---|
| Price  | Price in US dollars (326-18,823)  |
| Carat  | Weight of the diamond (0.2--5.01)  |
| Cut  | Quality of the cut (Fair, Good, Very Good, Premium, Ideal)  |
| Color  | Diamond colour, from J (worst) to D (best)  |
| Clarity  | A measurement of how clear the diamond is (I1 (worst), SI2, SI1, VS2, VS1, VVS2, VVS1, IF (best))   |
| x  | Length in mm (0--10.74)  |
| y  | Width in mm (0--58.9)  |
| z  | Depth in mm (0--31.8)  |
| Depth  | Total depth percentage = z / mean(x, y) = 2 * z / (x + y) (43--79)  |
| Table  | Width of top of diamond relative to widest point (43--95)  |

### Tratamento

Para poder utilizar um modelo de aprendizado de máquina, é necessário transformar as colunas 'Cut', 'Color' e 'Clarity' em dados numéricos. Uma vez que essas variáveis possuem uma ordem definida, os dados foram transformados em números discretos, onde o zero representa a categoria mais baixa, e as outras seguem em ordem crescente. 

### Modelo de regressão linear

Para o modelo de regressão linear, a primeira meta foi encontrar as colunas do dataset de treinamento que poderiam descrever melhor a coluna 'price'. Os testes iniciais apontaram que o melhor resultado era apresentado quando se excluíam apenas as colunas 'depth' e 'table (erro de 1288,26). Entretanto, ao desconsiderar também as colunas 'x', 'y' e 'z', o erro era muito próximo (erro: 1294,30).

A partir daí, as melhorias do modelo seriam baseadas em tratar os outliers. A primeira tentativa foi tratar os outliers da coluna 'carat'. Porém, o tratamento piorou as estimativas de preço (erro: 1587,66).

### Modelo de recomendação

Durante o desenvolvimento do modelo de regressão linear, notou-se que havia uma dificuldade de tratar os outliers. Além disso, pode-se dizer que os outliers podem sim ser uma boa estimativa para preços de diamantes.

Uma das soluções pensadas para solucionar o problema foi aplicar um modelo de recomendação. Para otimizar o cálculo, foi utilizada a função *distance.cdist* da biblioteca *scipy.spatial*.

Dispensando o tratamento de outliers, a primeira melhoria do modelo foi baseada na escolha das colunas que resultasse no menor valor de erro. A melhor combinação de colunas encontradas deu-se excluindo apenas as colunas 'depth' e 'table'.

Então, foi a vez de se determinar qual a melhor forma de calcular o preço a partir da matriz de recomendação. O método escolhido consiste em calcular a média dos preços dos 5 diamantes mais recomendados pelo algoritmo.

Por fim, foi a vez de se testar as métricas de distância do algoritmo de recomendação. Após os testes, a distância euclidiana produziu o melhor resultado (erro: 613,87).

## Construído com

As ferramentas utilizadas para criar o projeto

* [Python](https://www.python.org/) - Usado no desenvolvimento do projeto
* [Jupiter Notebook](https://jupyter.org/) - Usado no desenvolvimento do projeto

### Bibliotecas

* [pandas](https://pandas.pydata.org/)
* [numpy](https://numpy.org/)
* [matplotlib](https://matplotlib.org/)
* [tqdm](https://tqdm.github.io/)
* [scipy](https://www.scipy.org/)
* [sklearn](https://scikit-learn.org/)

### Data Sources

Os dados de entrada para o projeto estão no repositório.

```
data/diamonds.csv
data/rick_diamonds.csv
```


## Link do Repositório Online

* [Repositório](https://github.com/alitaca/Projeto_Diamonds.git) - Link para o repositório de dados.

## Autores

* **Aline** - *Trabalho Inicial* - [alitaca](https://github.com/alitaca)


## Licença

Este projeto está sob licença - veja o arquivo LICENSE.md para detalhes.

## Expressões de gratidão

* Aos professores da Ironhck, em especial a Rai e o Adriano :star_struck:
* E ao Luis, que saiu na frente de todo mundo, mas estabeleceu uma meta inalcançável para mim