### **\[Benefícios\] Visualizar e Selecionar Produtos**

1. **Funcionalidade**  
   1. O utilizador deve poder visualizar todos os seus produtos na área principal dos benefícios e selecionar qual o produto ativo para consulta detalhada.

2. **Requisitos Funcionais (As-Is)**  
   1. A área principal de benefícios apresenta um **carrossel** com todos os produtos do utilizador (titular \+ associado).  
   2. Cada produto exibe: nome do benefício, tipo de cartão, número do cartão, estado e saldo.  
   3. O utilizador pode navegar entre produtos no carrossel.  
   4. Em portal web, o número do cartão aparece 100% visível (não cifrado).  
   5. Em mobile, o número aparece cifrado (apenas início e fim visíveis); o número completo só aparece no detalhe.

3. **Gaps (To-Be)**  
   1. **Cifrar o número do cartão** também na versão web (apresentar apenas início e fim com meio anonimizado, em paridade com o mobile) — alinhado com a observação levantada nas demos.  
   2. *Sugestão:* Avaliar a possibilidade de **ocultar cartões** com saldo residual (cartões antigos com poucos cêntimos) na homepage.

---
