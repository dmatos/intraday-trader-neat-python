# Dados para testes na NEAT

## Contexto e definições

### NEAT
- testes iniciais serão realizados com os valores default do sistema

### Contexto de dados para testes:

* histórico de ações de um único ticker para treinamento e teste de performance sobre o dados de uma semana deste ticker [1->1]
* histórico de ações de todos os tickers para treinamento e teste de performance sobre uma semana de negócios do ticker no item anterior [n->1]
* histórico de ações de todos os ticker para treinamento e teste de performance sobre uma semana de negócios de todos os tickers [n->n]

### Dados que serão utilizados para treinamento na NEAT:

- macd e sinal
- velas* de 3 minutos
- velas* de 5 minutos

*velas**: as velas devem ser criadas para cada minuto, diferente das velas consolidadas que exibimos no front.
Ou seja, uma única vela passará por 5 minutos sendo utilizada, porém com valores atualizados a cada tick.
Nesse caso a vela não terá toda a janela, mas talvez seja possível para a NEAT apostar dentro da vela.

### Dados de validação:

- preço do ativo no minuto em que se decide comprar/vender

# #TODO
* Testar o primeiro cenário com BBAS3
* Controller para baixar o csv dos dados (macd+sinal e velas) dentro de um range de datas para um ticker qualquer pelo id do ticker
* A primeira coluna do CSV deve ser o timestamp
* O nome do arquivo deve ser tickerCode-dataInicio-to-dataFim.csv
* O front deve entregar o arquivo assincronamente como é feito na Unidocs
* Adaptar o código deste projeto para tudo o que foi descrito acima
