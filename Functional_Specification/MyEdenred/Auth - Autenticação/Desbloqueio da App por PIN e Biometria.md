---
Feature-id: [9462](https://dev.azure.com/edenred-ept/Myedenred/_workitems/edit/9462) 
Feature-Name: Desbloqueio da App por PIN e Biometria  
Status: Validation  
Devops-sync: True  
Github-sync: True  
Last-update: May 28, 2026  
---

**Descrição**

A aplicação mobile deve dispor de um mecanismo de **desbloqueio local** que protege o acesso à app entre utilizações, sem exigir nova autenticação remota com credenciais a cada acesso. O método base de desbloqueio é um **PIN próprio da aplicação**, de definição obrigatória, podendo o utilizador ativar adicionalmente a **biometria** (Face ID / Touch ID ou equivalente) como atalho opcional de desbloqueio. 

---

**Pré-condições**

1. O utilizador está a utilizar a aplicação **mobile**.  
2. O utilizador tem uma sessão estabelecida através de autenticação remota com credenciais (email e password).  
3. *Para ativação de biometria:* o dispositivo dispõe de hardware de biometria configurado.

---

**Regras de Negócio e Comportamentos**

1. **PIN da Aplicação (método base de desbloqueio)**  
   2. A aplicação gere um **PIN próprio**, independente do PIN do dispositivo.  
   3. O PIN é composto por **4 dígitos numéricos**.  
   4. A definição do PIN é **obrigatória** e ocorre no **final do fluxo de onboarding**.  
   5. A configuração do PIN exige a introdução do código **duas vezes** para confirmação.

6. **Biometria (atalho opcional de desbloqueio)**  
   7. A ativação de biometria é **opcional**, o utilizador pode optar por não a configurar.  
   8. A biometria utiliza os mecanismos nativos do dispositivo e funciona como **atalho** de desbloqueio, tendo o PIN da aplicação como método base e fallback sempre disponível.  
   9. *Se* o desbloqueio biométrico falhar ou não estiver disponível no momento, o utilizador desbloqueia a app com o **PIN da aplicação**.

10. **Gestão dos Métodos**  
   11. O utilizador pode gerir as definições de PIN e biometria a partir da secção **Preferências → Definições**.  
   12. O utilizador pode ativar/desativar a biometria a qualquer momento.  
   13. O utilizador pode alterar o PIN da aplicação a partir das definições.

14. **Funcionamento do Desbloqueio**  
   15. *Com* PIN (e opcionalmente biometria) configurados: o desbloqueio por estes métodos dá acesso à app sem nova autenticação remota com credenciais.  
   16. A sessão mobile é **always on**, não expira por inatividade; o PIN/biometria é a camada de proteção do acesso local à app.

17. **Invalidação da Sessão e Nova Autenticação Remota**  
   18. Nos seguintes casos, a sessão é terminada e o desbloqueio local deixa de ser suficiente, exigindo **nova autenticação remota** com email e password:  
      1. O utilizador efetua **logout explícito**.  
      2. O utilizador seleciona a opção **"Esqueci-me do código"**.

---

**Pós-condições**

1. PIN da aplicação definido e ativo (obrigatório)  
2. Biometria ativa se configurada pelo utilizador (opcional).  
3. O utilizador desbloqueia a app em utilizações subsequentes sem necessidade de nova autenticação remota com credenciais.

---