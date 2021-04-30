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


| Column  | Description  |
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



### Modelo de regressão linear


### Modelo de recomendação


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