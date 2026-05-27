### **\[Perfil\] Visualizar e Editar Telemóvel (com OTP)**

1. **Funcionalidade**  
   1. O utilizador deve poder alterar o seu número de telemóvel, mediante validação OTP via SMS, sob pena de o número não ficar alterado.

2. **Requisitos Funcionais (As-Is)**  
   1. O utilizador introduz o novo número e o sistema envia um SMS OTP para esse novo número.  
   2. Se o OTP **não for validado**, o número **não é alterado** — permanece o anterior.  
   3. **Não existe estado "pendente"** — ou é validado de imediato, ou não há alteração.

---
