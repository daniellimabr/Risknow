# Story #2: Franquias;
  
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

;

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

Endpoints para API:

        /contratos;
          Recebe:
            Ano;
            Mes;
          Retorna:
            Contratos; Cliente; Franquia;

;

         /apontamentos;
          Recebe:
            Ano;
            Mes;
          Retorna:
            Apontamentos; Analista; Cliente;
