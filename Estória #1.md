# Story #1: Lista de Tickets;
  
  "Como um Gestor, quero consultar a lista de tickets de um cliente, para entender a quantidade de solicitações feitas pelos clientes"

    Cenário #1.1: Cliente válido
    Dado que o Gestor consulta a Lista de Tickets
    E insere um Cliente válido
    Quando clicar em Consultar
    Ou apertar "Enter"
    Então a lista de tickets é exibida
    E a contagem de tickets é exibida

;

    Cenário #1.2: Cliente inválido
    Dado que o Gestor consulta Lista de Tickets
    E insere um Cliente inválido
    Quando clicar em Consultar
    Ou apertar"Enter
    Então a mensagem informando "Cliente inválido" deverá ser exibida

;

    Cenário #1.3: Tickets no período
    Dado que o Gestor consulta o Lista de Tickets
    E insere um Cliente válido
    E insere uma Data Início
    E insere uma Data Fim
    Quando clicar em Consultar
    Ou apertar Enter
    Então uma tabela onde cada linha conterá os tickets do Cliente, cuja Data de Abertura seja maior que Data Início e menor que Data Fim será exibida
    E uma contagem de número de tickets será exibida


Endpoints para API:

        /tickets;
          Recebe:
            Cliente;
            Data Início;
            Data Fim;
          Retorna:
            Tickets; Cliente;
