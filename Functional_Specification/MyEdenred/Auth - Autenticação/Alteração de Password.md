---
Feature-id: [9459](https://dev.azure.com/edenred-ept/Myedenred/_workitems/edit/9459) 
Feature-Name: Alteração de Password  
Status: Validation  
Devops-sync: True  
Github-sync: True  
Last-update: May 28, 2026  
---

**Descrição**

O utilizador autenticado deve poder alterar a sua password a partir da área de perfil. A alteração mantém a sessão atual ativa e invalida imediatamente as sessões ativas noutros dispositivos, garantindo a segurança da conta.

---

**Pré-condições**

1. O utilizador está autenticado na aplicação.

---

**Regras de Negócio e Comportamentos**

1. **Ponto de Acesso**  
   2. A funcionalidade é acionada através da ação **"Alterar password"**, disponível no ecrã de perfil do utilizador.

3. **Fluxo de Alteração**  
   4. O utilizador deve seguir o seguinte fluxo para efetuar a alteração:  
      1. Inserir password atual (Esta credencial é suficiente para autorizar a operação, não sendo necessária validação adicional por email ou SMS).  
      2. Inserir nova password (Aplicam-se as mesmas regras de complexidade e formato do registo e recuperação).  
      3. Confirmar nova password.

5. **Mensagem de Confirmação**  
   6. Uma **mensagem de confirmação** é exibida após a alteração de password ser bem-sucedida.

7. **Invalidação de Sessões**  
   8. Após alteração de password bem-sucedida, **todas as sessões ativas noutros dispositivos são imediatamente invalidadas**, garantindo a segurança. 

9. **Manutenção da Sessão Actual**  
   10. A sessão atual mantém-se ativa. O utilizador não precisa fazer novo login na sessão atual após alterar a password.

---

**Pós-condições**

1. Password alterada com sucesso.  
2. Sessões ativas noutros dispositivos terminadas e invalidadas.  
3. Utilizador permanece autenticado no dispositivo onde efetuou a alteração.

---