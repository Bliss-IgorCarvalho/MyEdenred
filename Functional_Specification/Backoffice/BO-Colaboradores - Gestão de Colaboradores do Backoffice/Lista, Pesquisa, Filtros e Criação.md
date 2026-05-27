### **\[BO-Colaboradores\] Lista, Pesquisa, Filtros e Criação**

1. **Funcionalidade**  
   1. O Admin (e Admin Call Center, dependendo do contexto) deve poder consultar a lista de colaboradores do Backoffice, pesquisar/filtrar, e criar novos colaboradores.

2. **Requisitos Funcionais (As-Is)**  
   1. Tabela com colunas: nome, perfil (Admin, Call Center, etc.), data de registo, último login, estado.  
   2. **Filtros** para pesquisa (Perfil, Estado, Data de Registo, Data de Último Login).  
   3. Botão **Novo** para criar colaborador.  
   4. O fluxo de criação solicita: **nome**, **username**, **password** (definida pelo Admin ou gerada automaticamente), **perfil**.  
   5. **Não existe fluxo de ativação por email** — a conta é criada já ativa, e cabe ao colaborador alterar a password na primeira utilização (no perfil).

3. **Gaps (To-Be)**  
   1. Remover fotografia.  
   2. *Sugestão:* Introduzir fluxo de **ativação por email** ou **password temporária forçada a redefinir no primeiro login**, alinhado com boas práticas de segurança.

---
