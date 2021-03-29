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
