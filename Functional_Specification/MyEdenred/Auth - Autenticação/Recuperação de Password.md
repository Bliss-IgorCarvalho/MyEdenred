---
Feature-id: [9458](https://dev.azure.com/edenred-ept/Myedenred/_workitems/edit/9458) 
Feature-Name: Recuperação de Password  
Status: Validation  
Devops-sync: True  
Github-sync: True  
Last-update: May 28, 2026  
---

**Descrição**

O utilizador deve poder recuperar o acesso à sua conta caso tenha esquecido a password, através de um fluxo de redefinição iniciado a partir do ecrã de login. O processo é desencadeado pelo envio de um link de recuperação para o email associado à conta.

---

**Pré-condições**

1. O utilizador possui uma conta MyEdenred ativa.  
2. O utilizador tem acesso ao ecrã de login.  
3. O utilizador tem acesso ao email associado à conta.

---

**Regras de Negócio e Comportamentos**

1. **Início do Fluxo**  
   2. A CTA **"Recuperar password"** está disponível no ecrã de login.  
   3. O utilizador introduz o email associado à conta para iniciar o processo.

4. **Método de Envio**  
   5. O link/token de recuperação é enviado **apenas por email**, para o endereço associado à conta.  
   6. *Se* o email introduzido não corresponder a nenhuma conta existente: o sistema deve responder de forma neutra, sem revelar se o email existe ou não na base de dados *(boas práticas de segurança)*.

7. **Validade do Link**  
   8. O link de recuperação tem validade de **24 horas** *(sujeito a revisão com o Grupo Edenred e de acordo com as boas práticas de segurança)*.  
   9. *Se* o utilizador aceder ao link após o prazo de validade: exibir mensagem de erro e disponibilizar opção de solicitar novo link.

10. **Regras de Definição de Nova Password**  
   11. Aplicam-se as regras globais de complexidade e formato de password. (ainda pendente definição)

12. **Pressupostos Técnicos**  
   13. O Identity Provider externo utilizado é o **Ping Identity**.  
   14. O envio de SMS OTP é assegurado pela plataforma **InfoBip**.

---

**Pós-condições**

1. Email de recuperação enviado para o endereço associado à conta.  
2. Após redefinição bem-sucedida: password atualizada e utilizador redirecionado para o ecrã de login.

---

**Questões e Requisitos Pendentes**

1. Regras de definição de password aguardam confirmação das políticas de segurança do Grupo Edenred.  
2. Conformação do tempo de validade de 24 horas para o link de recuperação.  
3. Definição de regras globais de complexidade e formato de password.

---