# Criando de um Dashboard com o Google Data Studio
   <p align="center">
   <img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/dashboard.jpeg" height="750" width="3500">
   </p>  

## Tecnologias

* Google Chrome Versão 107.0.5304.123

## Serviços utilizados

* Google Data Studio
* Google Sheets
* https://convertio.co/pt/
* https://www.mavenanalytics.io/

## Como usar

Todos os elementos do dashboard são interativos. Pode-se utilizar os filtros para informações mais específicas, bem como clicar sobre cada elemento de um gráfico ou tabela, pois o projeto utiliza filtros cruzados.


## Features

* Modelagem relacional
* Tratamento de dados
* Bases de dados
* ETL
* Data Vizualization
* Business Inteligence
* Google Data Studio

## Versão

* 1.0.0.0

## Dashboard

  Apresento aqui o processo de elaboração de um [dashboard de vendas](https://datastudio.google.com/s/j-LsjUnXS8g) para uma pizzaria fictícia referente ao ano de 2015. Os dados foram retirados do site *Maven Analytics*, e são compostos por quatro tabelas de dados propriamente ditos - tabela de pedidos, tabela de detalhamento de pedidos, tabela de pizzas e tabela de tipos de pizzas - mais uma tabela de descrição das informações dos dados em geral. Esses dados estão presentes nos arquivos do projeto.

   O dashboard em si utiliza uma união dessas quatro tabelas, e havia duas opções: 1) Realizar essa união com o recurso de combinação de dados do Data Studio ou 2) Carregar essa base final já pronta para o Data Studio. Optei pela segunda, para melhor desempenho do dashboard - assim evita-se que o Data Studio desperdice recursos sempre preparando as tabelas antes de projetar as visualizações.Fiz isso utilizando o Google Sheets: criei uma [sheets](https://docs.google.com/spreadsheets/d/1UUHogXK8wlmQprItWgKoWVH-6MTYEr-ayiPC3C7A7ak/edit?usp=sharing) com 5 abas, uma worksheet para cada tabela de dados e outra para a unificação dessas tabelas. Esta última sendo a base de dados que o Data Studios utiliza de fato.
   
   Vale ressaltar que, apesar de nesse caso a união das tabelas ser feita de forma manual, é possível automatizar o processo, como apresentado [neste projeto](https://github.com/Matheus2510/Carga_de_Dados_-ETL-_Google_Sheets), por exemplo, e realizar a atualização da pase de dados periodicamente. Como aqui a base de dados utilizada é estática com dados retroativos, e o objetivo principal é o dashboard em si, não vi necessidade de tal procedimento.
   
   Sobre a construção do dashboard de fato, o primeiro passo foi definir um tema e layout para o projeto. Isso foi feito escolhendo-se uma imagem de pizza (aparentemente bem saborosa). A seguir são apresentadas a imagem e a paleta de cores que o Data Studio selecionou a partir dela.
   
   <p align="center">
   <img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/tema.jpg" height="100" width="100"><img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/imagem_em_branco.png" height="100" width="100"><img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/paleta_tema.png" height="100" width="300">
   </p>
   
   
   Em essência, utilizei a primeira cor da paleta para o fundo geral e bordas dos elementos. A cor preta para textos e elementos gráficos, e a terceira cor para o fundo dos elementos gráficos e imagens.
   
   Após a definição da paleta de cores, a intenção foi determinar quais informações estariam presentes para visualização. Avaliando os dados disponíveis e os objetivos do negócio, segmentei os elementos em quatro grupos: resumo de desempenho, acompanhamento ao longo do tempo, detalhes por produtos e filtros. 
   
   Para o primeiro grupo, julguei interessante destacar o total de faturamento, o número de pedidos e o número de pizzas vendidas. Para representar esses itens, utilizei scorecards (um objeto semelhante a uma caixa de texto, que contém algum indicador).
   
   Neste ponto é bom, para evitar repetições no futuro, explicitar o tratamento que todas as imagens - com exceção da imagem que serviu de tema, já que esta apenas teve sua transparência aumentada - que constam no dashboard receberam. Após ter a imagem desejada para cada caso, as converti em SVG, com auxílio do site *Convertio*. Após isso, as preenchi com a terceira cor de nossa paleta. As imagens abaixo foram as selecionadas para estilizar o visual do projeto.
   
   <p align="center">
   <img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/simbolo_vendas.svg" height="100" width="100"><img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/imagem_em_branco.png" height="100" width="100"><img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/cifrao.svg" height="100" width="100"><img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/imagem_em_branco.png" height="100" width="100"><img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/bloco_de_notas.svg" height="100" width="100"><img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/imagem_em_branco.png" height="100" width="100"><img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/fatia_pizza.svg" height="100" width="100"><img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/imagem_em_branco.png" height="100" width="100">
   </p>
   
   Voltando aos scorecards, para dar um visual mais agradável, removi as legendas que o Data Studio traz por padrão, compactei os números, e acoplei a imagem representativa de cada indicador ao seu lado esquerdo, além de preencher os fundos de todos esses elementos com a terceira cor de nossa paleta. Como acabamento, inseri um retângulo ao fundo com bordas arredondadas e sombra para um efeito adicional, preenchendo-o também com a terceira cor da paleta.
   
   <p align="center">
   <img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/scorecards.png" height="100" width="600">
   </p>
   
   Para os acompanhamentos das vendas ao longo do tempo, optei por abordar três granularidades diferentes: diária, semanal, e mensal. Para a diária, escolhi um gráfico de série temporal, pois se encaixa melhor com uma maior quantidade de pontos. Sua customização foi feita removendo a legenda padrão e ajustando a grade a um tamanho que as informações permitissem uma leitura adequada, inclusive colorindo essa própria grade com um tom suave de cinza, para um realce maior da série temporal. Há um toque adicional, que é a inclusão de uma caixa de texto contendo o título do gráfico, e a inclusão de uma linha preta, para dar um sentido de separação entre título e gráfico. Além disso, houve a inclusão de bordas arredondadas e sombra na cor primária da paleta.
   
   <p align="center">
   <img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/faturamento_diario.png" height="250" width="700">
   </p>
   
   O acompanhamento mensal teve exatamente foi construído exatamente da mesma forma. A única diferença é o tipo do gráfico, que é o de colunas. Um ponto interessante também é o recurso do Data Studio que extrai informações secundárias a partir de datas. Na base de dados utilizada, é informada apenas a data dos pedidos. Porém o Data Studio consegue extrair outras informações, como dia da semana e mês, por exemplo.
   
   <p align="center">
   <img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/faturamento_mensal.png" height="250" width="500">
   </p>   
   
   Já o acompanhamento por dia da semana foi feito utilizando-se uma tabela com mapa de calor para os valores. O truque da caixa de texto e da linha preta também esteve presente nesse elemento. A diferença aqui é que houve necessidade de incluir um retângulo auxiliar de fundo para manter a padronização com o restante do dashboard, já que as tabelas não permitem estilização completa em si mesmas.
   
   <p align="center">
   <img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/faturamento_dia_semana.png" height="250" width="350">
   </p>   
    
   Para os elementos referentes aos detalhes por produtos, preferi abordar a proporção que cada tamanho de pizza tem em relação ao total de vendas - gráfico de rosca - e as pizzas mais vendidas, em ordem decrescente - tabela com barras. Como o primeiro é um gráfico e o último é uma tabela, apenas reproduzi o que já foi abordado acima, alterando apenaos dados abordados.
   
   <p align="center">
   <img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/vendas_tamanho.png" height="250" width="200"><img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/imagem_em_branco.png" height="250" width="100"><img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/pizzas.png" height="250" width="200"> 
   </p>   
   
   Para finalizar o dashboard, inclui os flltros, que são três: filtro de meses, filtro de horas, e filtro de ingredientes. O primeiro é uma lista de tamanho fixo, em que o usuário apenas assinala ou não os meses desejados. O segundo é uma lista suspensa, com a informação adicional à direita de quantos pedidos foram realizados em cada hora. O último, por sua vez, é um filtro avançado, em que o usuário digita as primeiras letras de um ingrediente, ou mesmo a palavra completa, e o dashboard atualiza automaticamente com base apenas nas pizzas que contém aquele ingrediente. A formatação de cada um seguiu o padrão dos gráficos e tabelas.
   
   <p align="center">
   <img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/meses.png" height="250" width="100"><img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/imagem_em_branco.png" height="250" width="100"><img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/hora.png" height="250" width="150"><img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/imagem_em_branco.png" height="100" width="100"><img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/ingredientes.png" height="100" width="250">
   </p>   
   
   
   
## Autores

* Matheus Henrique de Souza: @Matheus2510 (https://github.com/Matheus2510)
