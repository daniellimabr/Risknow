# Story #3: Aproveitamento de Horas;
  
  "Como um Gestor, quero consultar o índice de aproveitamento de horas contratadas com os analistas, para entender o desempenho de cada analista"

      Cenário #3.1: Exibir Aproveitamento de Horas dos Analistas
      Dado que o Gestor consulta o Aproveitamento de Horas dos Analistas
      E insere o Ano
      E insere o Mês
      Quando clicar em Consultar
      Ou apertar Enter
      Então uma tabela com a lista de Analistas, contendo a coluna de Horas Contratadas neste Ano/Mes, a coluna de soma Horas Apontadas neste Ano/Mes, e o valor de aproveitamento dado por Horas Apontadas / Horas Contratadas será exibido, em porcentagem.

  Endpoints para API:
  
          /apontamentos;
            Recebe:
              Ano;
              Mes;
            Retorna:
              Apontamentos; Analista;
;

          /analistas;
            Recebe:
              Ano;
              Mes;
            Retorna:
              Analista; Horas Contratadas;
