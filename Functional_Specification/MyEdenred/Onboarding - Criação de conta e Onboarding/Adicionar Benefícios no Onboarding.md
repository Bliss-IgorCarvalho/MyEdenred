### **\[Onboarding\] Adicionar Benefícios no Onboarding**

1. **Funcionalidade**  
   1. Como parte do fluxo de registo, o utilizador deve adicionar pelo menos um produto Edenred (Cartão ou Wallet) à sua conta, sem o qual não pode aceder à aplicação.

2. **Requisitos Funcionais (As-Is)**  
   1. No passo "Adicionar Benefícios" o utilizador pode adicionar **benefícios**, podendo ser Cartão Refeição, Cartão Flexível, Wallet Creche e/ou Wallet Educação.  
   2. Para **Cartão**, é solicitado o número de cartão (16 dígitos).  
   3. Para **Wallet**, são solicitados o **Wallet ID** e o **NIF**, validados primeiro pela Edenred e depois pela Paytec.  
   4. Se o utilizador remover o único produto da sua conta, esta passa a "inutilizável" — no próximo login será forçado a adicionar produto.

3. **Gaps (To-Be)**  
   1. A associação Produto ↔ Utilizador passará a ser feita por **NIF**, através de novo serviço a desenvolver pela Edenred (ver Sessões Globais — Dependências).  
   2. *Em análise:* Adicionar um **validador adicional** ao número de cartão (ex.: data de validade, últimos dígitos de um movimento, código no verso) para mitigar a inexistência atual de validador).

4. **Questões e requisitos em aberto**  
   1. Confirmar limite máximo de produtos por conta (Notas Manuais indicam **5 produtos** parametrizáveis via backend) e se o limite é por titularidade, por associação, ou ambos.

---
