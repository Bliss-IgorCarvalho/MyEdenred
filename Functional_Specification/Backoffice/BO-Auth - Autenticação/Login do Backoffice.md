### **\[BO-Auth\] Login do Backoffice**

1. **Funcionalidade**  
   1. O colaborador interno deve poder autenticar-se no Backoffice introduzindo **username** e **password** (não email).

2. **Requisitos Funcionais (As-Is)**  
   1. O login exige **username e password**.  
   2. **Não existe** funcionalidade de "Recuperar password" para o Backoffice — em caso de esquecimento, é necessário que o Admin defina uma nova password manualmente.  
   3. Existem **4 perfis** distintos (ver Feature 73): Administrador, Administrador Call Center, Call Center, Marketing.

3. **Gaps (Sugestões)**  
   1. *Sugestão:* Avaliar introdução de **MFA no Backoffice** (alinhamento com requisitos de segurança levantados em auditoria interna referida na Demo Backoffice).  
   2. *Sugestão:* Avaliar introdução de **fluxo de recuperação de password** (atualmente apenas o Admin pode redefinir; pain point conhecido).

4. **Questões e requisitos em aberto**  
   1. É possível ter múltiplas sessões ativas?

---
