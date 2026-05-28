---
Feature-id: 9457 
Feature-url: https://dev.azure.com/edenred-ept/Myedenred/_workitems/edit/9457 
Feature-Name: Logout  
Status: Validation  
Devops-sync: True  
Github-sync: True  
Last-update: May 28, 2026  
---

**Descrição**

O utilizador autenticado deve poder terminar a sua sessão na aplicação MyEdenred de forma explícita, através de uma opção acessível no menu de utilizador. 

---

**Pré-condições**

1. O utilizador está autenticado na aplicação.

---

**Regras de Negócio e Comportamentos**

1. **Ponto de Acesso**  
   2. A opção **"Terminar sessão"** deve estar disponível na área de perfil de utilizador.

3. **Gestão de Sessão — Mobile**  
   4. A sessão mobile é **always on** — não expira por inatividade.  
   5. O logout explícito pelo utilizador termina a sessão e inválida a autenticação por PIN/biometria, exigindo nova autenticação com credenciais completas no próximo acesso.

6. **Gestão de Sessão — Web (Portal)**  
   7. A sessão web expira automaticamente após **60 minutos de inatividade** *(a confirmar com o cliente)*.  
   8. *Se* a sessão expirar por inatividade: o utilizador é redirecionado para o ecrã de login.

---

**Pós-condições**

1. Sessão terminada e invalidada.  
2. Utilizador redirecionado para o ecrã de login.

---

**Questões e Requisitos Pendentes**

1. Confirmar com tempo (60 minutos) para logout automático por inatividade.

---