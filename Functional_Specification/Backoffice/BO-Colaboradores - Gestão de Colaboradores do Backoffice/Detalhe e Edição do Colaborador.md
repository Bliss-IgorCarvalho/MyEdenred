### **\[BO-Colaboradores\] Detalhe e Edição do Colaborador**

1. **Funcionalidade**  
   1. O Admin deve poder consultar o detalhe de um colaborador e executar ações: editar, suspender, eliminar, renovar password, alterar username.

2. **Requisitos Funcionais (As-Is)**  
   1. Página de detalhe exibe: nome, username, estado, perfil, data de registo, último login.  
   2. Ações: **Editar** (nome, username, password, perfil), **Suspender** (bloquear acesso), **Eliminar** (remoção total).  
   3. A renovação de password ocorre via **Editar** — não há fluxo de "recuperar password".

3. **Gaps (To-Be)**  
   1. Remover fotografia.  
   2. Sugestão: Alterar o fluxo de “alteração de password” para despoletar fluxo de recuperação/redefinição de password via e-mail. Atualmente o Adim BO define manualmente a password e partilha com o colaborador, que depois pode ou não alterá-la.

---
