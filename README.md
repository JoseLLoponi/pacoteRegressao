# ME918 - Projeto 2

Lucas dos Santos Tomaz - 239931  
Bianca de Barros Bonifácio - 232129  
José Lucas Bueno Loponi - 204301  
Guilherme Fratin Medina - 135954

## Introdução

Olá mundo! Este pacote tem como objetivo ajustar modelos de regressão
linear múltipla, realizar predições e construir gráficos de diagnóstico.

Para reproduzir os exemplos contidos neste arquivo, foi utilizado o
banco de dados simulados “sodad.rda”, disponível no pacote.

## Instalação

Você pode instalar este pacote através do Github com o auxílio do
[devtools](https://github.com/hadley/devtools).

    devtools::install_github("JoseLLoponi/PacoteRegressao")

## Instruções para uso

1.  Para ajustar o modelo de regressão, use a função
    `regressao(X, Y, dados)`. Onde `X` é um vetor de caracteres com os
    nomes das colunas do banco de dados contendo as variáveis
    preditoras, `Y` é uma string contendo o nome da coluna da variável
    resposta e `dados` é o conjunto de dados. A função retorna as
    estimativas de quadrados mínimos dos coeficientes, os valores
    preditos da variável resposta, os resíduos do modelo e o erro padrão
    dos coeficientes.

#### Exemplo:

    ajuste1 <- regressao(X = c('B'), Y = 'A', dados = sodad)
    ajuste1
    ajuste2 <- regressao(X = c('A', 'B'), Y = 'C', dados = sodad)
    ajuste2
    ajuste3 <- regressao(X = c('A', 'B', 'D'), Y = 'E', dados = sodad)
    ajuste3
    ajuste4 <- regressao(X = c('A', 'C', 'D', 'E'), Y = 'B', dados = sodad)
    ajuste4

1.  Para fazer predições para novos valores com o modelo, use a função
    `predicao(regressao, predicao)`, onde `regressao` é um modelo
    ajustado com a função `regressao()` e `predicao` é um vetor numérico
    com os valores desejados dos preditores, na mesma ordem em que foram
    especificados no ajuste do modelo.

#### Exemplo:

    predicao(ajuste1, c(1))
    predicao(ajuste2, c(1, 2))
    predicao(ajuste3, c(1, 2, 3))
    predicao(ajuste4, c(1, 2, 3, 4))

1.  Também é possível construir gráficos de diagnóstico para avaliar a
    qualidade do ajuste. Para fazer um gráfico de valores preditos x
    valores observados, use a função `grafico_pred_obs(regressao)`, onde
    `regressao` é o modelo de regressão ajustado com a função
    `regressão()`.

#### Exemplo:

    grafico_pred_obs(ajuste1)
    grafico_pred_obs(ajuste2)
    grafico_pred_obs(ajuste3)
    grafico_pred_obs(ajuste4)

1.  Além disso, é possível construir um Q-Q plot dos resíduos do modelo
    para avaliar a suposição de normalidade. Para isso, use a função
    `grafico_qq(regressao)`, com `regressao` sendo o modelo ajustado com
    a função `regressão()`.

#### Exemplo:

    grafico_qq(ajuste1)
    grafico_qq(ajuste2)
    grafico_qq(ajuste3)
    grafico_qq(ajuste4)
