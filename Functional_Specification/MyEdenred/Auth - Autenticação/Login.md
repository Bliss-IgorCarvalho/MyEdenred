---
Feature-id: 9456 
Feature-url: https://dev.azure.com/edenred-ept/Myedenred/_workitems/edit/9456 
Feature-Name: Login  
Status: Validation  
Devops-sync: True  
Github-sync: True  
Last-update: May 28, 2026  
---

**Descrição**

O utilizador deve poder iniciar sessão na aplicação MyEdenred introduzindo o seu email e password. Em função da plataforma (mobile ou web) e do tempo decorrido desde a última autenticação, pode ser solicitado um segundo fator de autenticação (MFA) via OTP, garantindo a segurança do acesso à conta.

---

**Pré-condições**

1. O utilizador possui uma conta MyEdenred ativa.  
2. O email associado à conta está validado.

---

**Regras de Negócio e Comportamentos**

1. **Ecrã de Login**  
   2. O ecrã solicita os campos **email** e **password**.  
   3. Estão disponíveis as seguintes CTAs secundárias:  
      1. **"Recuperar password"** — inicia o fluxo de recuperação de password.  
      2. **"Criar conta"** — inicia o fluxo de registo de novo utilizador.

4. **Autenticação — Email em vigor**  
   5. O login utiliza o **email validado mais recentemente**.  
   6. *Se* existir uma alteração de email pendente de validação: o email **anterior** permanece em vigor para efeitos de login.

7. **MFA — Mobile**  
   8. O segundo fator de autenticação é efetuado via **OTP por SMS**.  
   9. O MFA é solicitado após a introdução de email e password.  
   10. A sessão mobile é **always on** — não expira por inatividade.  
   11. O MFA é solicitado **a cada 180 dias**.

12. **MFA — Web (Portal)**  
   13. O segundo fator de autenticação é efetuado via **OTP por email**.  
   14. O MFA é solicitado após a introdução de email e password.  
   15. O utilizador pode optar por **confiar no browser** atual, dispensando o MFA por um período de **90 dias** (parâmetro configurável).

16. **Acesso após Login**  
   17. *Se* a conta não tiver produtos associados: o utilizador **não pode navegar** na aplicação e é direcionado para adicionar pelo menos um produto.  
   18. *Se* a conta tiver pelo menos um produto associado: o utilizador acede normalmente ao dashboard.

19. **Pressupostos Técnicos**  
   20. O Identity Provider externo utilizado é o **Ping Identity**.  
   21. O envio de SMS OTP é assegurado pela plataforma **InfoBip**.

---

**Pós-condições**

1. Sessão autenticada iniciada com sucesso.  
2. Utilizador redirecionado para a home page do sistema (ou para o fluxo de adição de produto, se aplicável).

---