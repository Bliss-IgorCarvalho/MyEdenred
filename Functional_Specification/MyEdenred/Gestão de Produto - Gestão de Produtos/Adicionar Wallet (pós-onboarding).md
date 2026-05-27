### **\[Benefícios\] Adicionar Wallet (pós-onboarding)**

1. **Funcionalidade**  
   1. O utilizador autenticado deve poder adicionar uma nova Wallet (Creche ou Educação) à sua conta, mediante a introdução do **Wallet ID** e do **NIF**.

2. **Requisitos Funcionais (As-Is)**  
   1. O utilizador introduz **Wallet ID** e **NIF**.  
   2. O sistema realiza **pré-validação na Edenred** dos dados.  
   3. Após pré-validação, chama o backend **Paytec** para obter informações da wallet.  
   4. Uma Wallet apenas pode ter **um titular** — não admite Utilizadores Associados.  
   5. Após sucesso, a wallet aparece no carrossel de produtos.

3. **Pressupostos**  
   1. A integração com Paytec mantém-se.

4. **Questões e requisitos em aberto**  
   1. Pendente confirmar: Uma Wallet com formato Creche **e** Educação partilha o mesmo Wallet ID, mas é apresentada como dois produtos no carrossel.

---
