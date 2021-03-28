# Risknow

A Risknow é uma empresa de desenvolvimento de software, voltado para Inteligência Artificial como apoio à avaliação de Risco da Carteira de Créditos Imobiliarios.
Este documento é uma forma de apresentar um resultado ao teste solicitado pelo Giulliano Soares, para especificação para entrega de um determinado produto.

Para este resultado, estarão sendo utilizados os conhecimentos adquiridos até o momento por mim, Daniel Lima, como forma de exibição do potencial de desenvolvimento da função de Product Owner pela Risknow.

# Início do Cenário Hipotético: "Dashboard de Desempenho do Time de Suporte Técnico"

# A Empresa

A Swift Consulting presta serviço de suporte técnico a grandes provedores e operadoras de Internet no Brasil, e divide suas atividades entre "Suporte Técnico" e "Implantações/Mudanças" na rede de seus clientes. Além disto, mantém um monitoramento básico da rede destes clientes, adquirindo dados sobre o estado atual da rede para atuação proativa em determinados casos.

# Iniciativa

O Produto "Dashboard de Desempenho do Time de Suporte Técnico" para Empresa Swift Consulting, terá como objetivo auxiliar a empresa a entender melhor o cenário das suas atividades, e atendimento aos contratos estabelecidos com seus clientes. Com isto, a Swift Consulting pretende definir a melhor utilização de seus recursos, e melhorar sua estratégia de precificação de serviços.

# Pré-Requisitos:

  # Banco de Dados: 
  
    #1 Lista de tickets, contendo:
    
      "Ticket",
        Tipo: Numero Inteiro, até 32 caracteres;
        
      "Cliente",
        Tipo: Texto, até 32 caracteres;

      "Data de Abertura", 
        Tipo: Data, aaaa-mm-dd

      "Data de Encerramento", 
        Tipo: Data; aaaa-mm-dd

      "Tipo", 
        Tipo: Número Inteiro, contendo as opções;
          1, como "1 - Suporte";
          2, como "2 - Implantação";
          3, como "3 - Monitoramento";

      "Assunto", 
          Tipo: Texto, até 64 caracteres;

      "Solicitação",
          Tipo: Texto, até 2048 caracteres;
            
      #2 Lista de Contratos, contendo:
      
        "Cliente",
         Tipo: Texto, até 32 caracteres;
         
         "Franquia de Horas Contratadas",
         Tipo: Numero decimal;
         
         "Regime de Franquia de Horas",
         Tipo: Numero Inteiro, contendo as opções;
         1, como "1 - Mensal";
         2, como "2 - Anual";
         
         "Valor do Contrato",
         Tipo: Numero Decimal;
         
         "Início do Contrato";
         Tipo: Data, aaaa-mm-dd;
         
         "Fim do Contrato";
         Tipo: Data, aaaa-mm-dd;
         
       #3 Apontamentos, contendo:
       
        "Analista",
        Tipo: Texto, até 32 caracteres;
        
        "Ticket",
        Tipo: Número inteiro, até 32 caracteres;
        
        "Data do Apontamento",
        Tipo: Data, aaaa-mm-dd;
        
        "Hora Inicial",
        Tipo: Hora, hh:mm;
        
        "Hora Final",
        Tipo: Hora, hh:mm;
        
        #4 Contratos de Analistas, contendo:
       
        "Analista",
        Tipo: Texto, até 32 caracteres;
        
        "Data do Contrato",
        Tipo: Data, aaaa-mm;
        
        "Horas Contratadas",
        Tipo: Numero inteiro        

# Estórias de Usuário

Serão descritas abaixo algumas estórias já discutidas com a Swift Consulting, que serão objeto de trabalho nas próximas Sprints:

  Story #1: Lista de Tickets;
    "Como um Gestor, quero consultar a lista de tickets de um cliente, para entender a quantidade de solicitações feitas pelos clientes"
    
      Cenário #1.1: Cliente válido
      Dado que o Gestor consulta a Lista de Tickets
      E insere um Cliente válido
      Quando clicar em Consultar
      Ou apertar "Enter"
      Então a lista de tickets é exibida
      E a contagem de tickets é exibida
      
      Cenário #1.2: Cliente inválido
      Dado que o Gestor consulta Lista de Tickets
      E insere um Cliente inválido
      Quando clicar em Consultar
      Ou apertar"Enter
      Então a mensagem informando "Cliente inválido" deverá ser exibida
      
      Cenário #1.3: Tickets no período
      Dado que o Gestor consulta o Lista de Tickets
      E insere um Cliente válido
      E insere uma Data Início
      E insere uma Data Fim
      Quando clicar em Consultar
      Ou apertar Enter
      Então uma tabela onde cada linha conterá os tickets do Cliente, cuja Data de Abertura seja maior que Data Início e menor que Data Fim será exibida
      E uma contagem de número de tickets será exibida
  
  Story #2: Franquias;
    "Como um Gestor, quero consultar o consumo da franquia de um contrato, para entender o comportamento de um cliente"
    
      Cenário #2.1: Consultar Franquias do Período
      Dado que o Gestor consulta a Lista de Contratos
      E insere o Ano
      Ou insere o Ano
      E insere o Mês
      Quando clicar em Consultar
      Ou apertar Enter
      Então uma tabela contendo os contratos vigentes com data maior que "Ano" ou maior que "Ano+Mês" será exibida
      E uma soma do valor de todos os contratos será exibida
      E uma soma da Franquia de Horas será exibida
      E uma soma do Consumo de Horas será exibida
      E um gráfico em Barras e Linhas dos Contratos será exibido
      
      Cenário #2.2: Exibir Gráfico de Barras e Linhas dos Contratos
      Dado que o Gestor solicita o gráfico Barras e Linhas dos Contratos
      E insere o Cliente
      E insere o Ano
      Ou insere o Ano
      E insere o Mês
      Quando o gráfico for enviado
      Então exibirá um Gráfico de Barras e Linhas será exibido
      
        Critérios:
        O eixo X do gráfico informa os Clientes
        O eixo Y do gráfico informa a Franquia de Horas do Contrato
        Os valores de barra do gráfico informam a soma dos Apontamentos de Horas para cada cliente
        Os valores de linha do gráfico informam a porcentagem de consumo, comparando a Soma das Horas Apontadas dividido pela Franquia de Horas do Contrato
        O eixo Y tem o valor máximo sendo o maior valor de Franquia do período
        Os valores de barra do gráfico terão a cor variando do Vermelho-Escuro para o Verde-Claro, de acordo com o maior valor de Apontamento de Horas
        Os valores de linha terão a cor variando do Roxo-Escuro para o Amarelo-Claro, de acordo com o maior valor de porcentagem de Consumo de Franquias 
  
  
  Story #3: Aproveitamento de Horas;
    "Como um Gestor, quero consultar o índice de aproveitamento de horas contratadas com os analistas, para entender o desempenho de cada analista"
        
        Cenário #3.1: Exibir Aproveitamento de Horas dos Analistas
        Dado que o Gestor consulta o Aproveitamento de Horas dos Analistas
        E insere o Ano
        E insere o Mês
        Quando clicar em Consultar
        Ou apertar Enter
        Então uma tabela com a lista de Analistas, contendo a coluna de Horas Contratadas neste Ano/Mes, a coluna de soma Horas Apontadas neste Ano/Mes, e o valor de aproveitamento dado por Horas Apontadas / Horas Contratadas será exibido, em porcentagem.

# Fim
