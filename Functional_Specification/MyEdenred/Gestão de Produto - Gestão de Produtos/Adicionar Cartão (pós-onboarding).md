### **\[Benefícios\] Adicionar Cartão (pós-onboarding)**

1. **Funcionalidade**  
   1. O utilizador autenticado deve poder adicionar um novo Cartão à sua conta a partir da área dos seus benefícios, mediante a introdução do número de cartão (16 dígitos).

2. **Requisitos Funcionais (As-Is)**  
   1. Está disponível a opção "Adicionar benefício" / "Adicionar produto" a partir da área dos meus benefícios.  
   2. O utilizador introduz o número de cartão (16 dígitos).  
   3. O sistema chama o backend **Novo Banco** para validação do cartão.  
   4. Se o cartão já estiver associado a outra conta, despoleta o fluxo de **Utilizador Associado** (ver Feature 10).  
   5. Após adição, é apresentado ecrã de sucesso e o cartão fica disponível no carrossel de produtos.

3. **Gaps (To-Be)**  
   1. Adicionar **mecanismo anti-fraude** (ex.: limite de 3 tentativas, captcha) para mitigar tentativas automatizadas de adição de números de cartão (Penetration Test).

---
