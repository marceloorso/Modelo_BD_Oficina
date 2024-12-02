# Sistema de Controle e Gerenciamento de Ordens de Serviço para Oficina Mecânica

## Narrativa

O sistema gerencia a execução de ordens de serviço em uma oficina mecânica, abrangendo os seguintes pontos:

1. **Recebimento de Veículos**  
   - Clientes levam veículos à oficina mecânica para serem consertados ou para passarem por revisões periódicas.

2. **Designação de Equipe**  
   - Cada veículo é designado a uma equipe de mecânicos que identifica os serviços a serem executados e preenche uma Ordem de Serviço (OS) com a data de entrega.

3. **Cálculo de Custos**  
   - A partir da OS, calcula-se o valor de cada serviço, consultando-se uma tabela de referência de mão de obra.  
   - O valor de cada peça também compõe o total da OS.

4. **Autorização do Cliente**  
   - O cliente autoriza a execução dos serviços.

5. **Execução dos Serviços**  
   - A mesma equipe que avaliou o veículo executa os serviços definidos na OS.

6. **Pagamentos**  
   - O cliente pode realizar pagamentos referentes às Ordens de Serviço de diferentes formas, como:
     - Cartão de crédito ou débito.
     - Transferência bancária.
     - Dinheiro.  
   - Cada OS pode ser paga com uma ou mais formas de pagamento.  
   - As informações de pagamento incluem:
     - Forma de pagamento.
     - Data do pagamento.
     - Valor pago.

7. **Informações sobre Mecânicos**  
   - Os mecânicos possuem os seguintes atributos: código, nome, endereço e especialidade.

8. **Detalhes da Ordem de Serviço (OS)**  
   - Cada OS possui:
     - Número único.
     - Data de emissão.
     - Valor total.
     - Status.
     - Data prevista para a conclusão dos trabalhos.

9. **Relação entre OS, Serviços e Peças**  
   - Uma OS pode ser composta por vários serviços, e um mesmo serviço pode estar contido em mais de uma OS.  
   - Uma OS pode incluir vários tipos de peças, e uma mesma peça pode estar presente em mais de uma OS.

---

## Requisitos do Modelo de Banco de Dados

### Entidades e Relacionamentos

1. **Cliente**
   - Cada cliente pode ter um ou mais veículos.

2. **Veículo**
   - Um veículo é associado a um cliente e pode ter uma ou mais ordens de serviço.

3. **Ordem de Serviço (OS)**
   - Uma OS é associada a um veículo e pode incluir múltiplos serviços e peças.

4. **Serviço**
   - Serviços são atribuídos a OSs e possuem informações sobre o custo de mão de obra.

5. **Peça**
   - Peças são registradas e associadas a OSs, compondo o custo total.

6. **Mecânico**
   - Mecânicos são atribuídos às OSs e trabalham na execução dos serviços.

7. **Pagamento**
   - Cada pagamento está associado a uma OS e pode incluir:
     - Valor pago.
     - Data do pagamento.
     - Forma de pagamento (cartão, transferência, dinheiro).
   - Uma OS pode ter vários pagamentos, permitindo múltiplas formas de quitação.

### Relacionamentos

- **Cliente e Veículo**: 1:N  
- **Veículo e Ordem de Serviço**: 1:N  
- **Ordem de Serviço e Serviço**: N:M  
- **Ordem de Serviço e Peça**: N:M  
- **Ordem de Serviço e Mecânico**: N:M  
- **Ordem de Serviço e Pagamento**: 1:N  

---

## Funcionalidades

- Cadastro de clientes e veículos.  
- Criação e gerenciamento de ordens de serviço.  
- Registro e cálculo do custo de mão de obra e peças.  
- Acompanhamento de status e prazos de conclusão.  
- Controle de mecânicos responsáveis pelos serviços.  
- Registro de pagamentos associados às OSs.  

---

## Considerações Técnicas

- Utilize o formato de diagrama ERD para modelar o banco de dados.
- Acompanhe as relações entre as entidades com chaves primárias e estrangeiras.
- Inclua tabelas associativas para as relações N:M (ex.: OS_Servico, OS_Peca, OS_Mecanico).
- Implemente um relacionamento 1:N entre OS e Pagamentos.


