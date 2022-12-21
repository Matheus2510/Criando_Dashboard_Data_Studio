# Criando de um Dashboard com o Google Data Studio

## Tecnologias


## Serviços utilizados



## Como usar



## Features



## Versão



# Dashboard

  Apresento aqui o processo de elaboração de um [dashboard de vendas](https://datastudio.google.com/s/j-LsjUnXS8g) para uma pizzaria fictícia referente ao ano de 2015. Os dados foram retirados do site *Maven Analytics*, e são compostos por quatro tabelas de dados propriamente ditos - tabela de pedidos, tabela de detalhamento de pedidos, tabela de pizzas e tabela de tipos de pizzas - mais uma tabela de descrição das informações dos dados em geral. Esses dados estão presentes nos arquivos do projeto.

   O dashboard em si utiliza uma união dessas quatro tabelas, e havia duas opções: 1) Realizar essa união com o recurso de combinação de dados do Data Studio ou 2) Carregar essa base final já pronta para o Data Studio. Optei pela segunda, para melhor desempenho do dashboard - assim evita-se que o Data Studio desperdice recursos sempre preparando as tabelas antes de projetar as visualizações.Fiz isso utilizando o Google Sheets: criei uma [sheets](https://docs.google.com/spreadsheets/d/1UUHogXK8wlmQprItWgKoWVH-6MTYEr-ayiPC3C7A7ak/edit?usp=sharing) com 5 abas, uma worksheet para cada tabela de dados e outra para a unificação dessas tabelas. Esta última sendo a base de dados que o Data Studios utiliza de fato.
   
   Vale ressaltar que, apesar de nesse caso a união das tabelas ser feita de forma manual, é possível automatizar o processo, como apresentado [neste projeto](https://github.com/Matheus2510/Carga_de_Dados_-ETL-_Google_Sheets), por exemplo, e realizar a atualização da pase de dados periodicamente. Como aqui a base de dados utilizada é estática com dados retroativos, e o objetivo principal é o dashboard em si, não vi necessidade de tal procedimento.
   
   Sobre a construção do dashboard de fato, o primeiro passo foi definir um tema e layout para o projeto. Isso foi feito escolhendo-se uma imagem de pizza (aparentemente bem saborosa). A seguir são apresentadas a imagem e a paleta de cores que o Data Studio selecionou a partir dela.
   
   <p align="center">
   <img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/tema.jpg" height="100" width="100">       <img src="https://github.com/Matheus2510/Criando_Dashboard_Data_Studio/blob/main/imagens/paleta_tema.png" height="100" width="300">
   </p>
   
   Em essência, utilizei a primeira cor da paleta para o fundo geral e bordas dos elementos. A cor preta para textos e elementos gráficos, e a terceira cor para o fundo dos elementos gráficos e imagens.
   
   Neste ponto é bom, para evitar repetições no futuro, explicitar o tratamento que todas as imagens - com exceção da imagem que serviu de tema, já que esta apenas teve sua transparência aumentada - que constam no dashboard receberam. Após ter a imagem desejada para cada caso, as converti em SVG, com auxílio do site *Convertio*. Após isso, as preenchi com a terceira cor de nossa paleta.
   
   Após a definição da paleta de cores, a intenção foi determinar quais informações estariam presentes para visualização. Avaliando os dados disponíveis e os objetivos do negócio, segmentei os elementos em quatro grupos: resumo de desempenho, acompanhamento ao longo do tempo, detalhes por produtos e filtros. 
   
   Para o primeiro grupo, julguei interessante destacar o total de faturamento, o número de pedidos e o número de pizzas vendidas. Para representar esses pontos, utilizei scorecards (um objeto semelhante a uma caixa de texto, que contém algum indicador).


## Autores

* Matheus Henrique de Souza: @Matheus2510 (https://github.com/Matheus2510)
