### **\[BO-Utilizadores\] Lista, Pesquisa, Filtros e Exportação**

1. **Funcionalidade**  
   1. O colaborador Call Center / Admin deve poder consultar a lista de utilizadores MyEdenred, com pesquisa por email/produto ID e filtros por estado/data/opt-in. Deve poder exportar a lista filtrada.

2. **Requisitos Funcionais (As-Is)**  
   1. Tabela com colunas: nome, data de registo, último login, estado (Ativo/Suspenso), opt-in marketing.  
   2. **Pesquisa** por nome, email ou por **product ID** (número de cartão ou Wallet ID).  
   3. **Filtros** por  estado, data de registo, último login, estado do opt-in,.  
   4. **Exportação** da lista para Excel.

3. **Gaps (To-Be)**  
   1. Implementar **política de data purging** / eliminação de contas inativas há muito tempo — referido na Demo como necessidade para mitigar problema atual de segmentos morosos (Notas Manuais).  
   2. *Sugestão:* Adicionar **filtro por NIF** do utilizador (atualmente não está disponível como filtro direto).

4. **Pressupostos**  
   1. Em produção, a aplicação atual contém mais de 1 milhão de utilizadores (dados acumulados desde o lançamento — sem data purging).

5. **Questões e requisitos em aberto**  
   1. Definir os critérios para considerar "utilizador inativo" e os parâmetros do data purging.  
   2. Considerando que o opt-in passará a ser gerido em CMP, o estado de consentimento ainda deve estar disponível como dado visível e filtro neste ecrã? Se sim, especificar quais consentimentos devem ser utilizados para estes fins.

---
