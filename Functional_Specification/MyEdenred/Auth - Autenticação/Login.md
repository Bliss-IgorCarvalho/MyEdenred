### **\[Auth\] Login**

1. **Funcionalidade**  
   1. O utilizador deve poder iniciar sessão na aplicação introduzindo o seu **email** e **password**. Em determinadas circunstâncias (mobile, sessões novas) é solicitado um segundo fator de autenticação (MFA) via OTP.

2. **Requisitos Funcionais (As-Is)**  
   1. O ecrã de login solicita **email** e **password**.  
   2. A partir do ecrã de login estão disponíveis as opções **"Recuperar password"** e **"Criar conta"**.  
   3. Contas **sem produtos associados não permitem acesso/navegação** após login — o utilizador é direcionado a adicionar pelo menos um produto.  
   4. O login utiliza o email validado mais recentemente; se houver uma alteração de email pendente de validação, o **email anterior** é o que permanece em vigor.

3. **Pressupostos**  
   1. O Identity Provider externo será **Ping Identity**.  
   2. A camada de envio de SMS OTP continua a ser **InfoBip**.

4. **Questões e requisitos em aberto**  
   1. O MFA passará a ser obrigatório em todos os logins, ou apenas periodicamente (a confirmar com cliente)?

---
