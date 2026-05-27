### **\[Auth\] Validação de Email**

1. **Funcionalidade**  
   1. O sistema deve validar o endereço de email do utilizador no momento do registo de conta e em cada alteração de email no perfil, garantindo que o endereço associado à conta é controlado pelo utilizador.

2. **Requisitos Funcionais (As-Is)**  
   1. Durante o registo, é enviado um email com link/CTA de confirmação para o endereço indicado pelo utilizador.  
   2. O utilizador só consegue concluir o registo após clicar no link de confirmação.  
   3. Na alteração de email no perfil, é enviado um email para o **novo endereço** que aguarda validação.  
   4. Enquanto a validação do novo email não for concluída, o **email anterior** permanece em vigor (utilizado para login e comunicações).  
   5. O estado "pendente de validação" **não tem tempo limite** — pode permanecer indefinidamente sem invalidar a alteração.

3. **Gaps (To-Be)**  
   1. *Sugestão:* Definir um **tempo limite** para a validação do novo email (ex.: 24h), expirando a alteração e mantendo o email anterior caso o novo não seja validado dentro do prazo — mitiga o problema atual de estado "pendente" indefinido (identificado em Notas Manuais).

4. **Questões e requisitos em aberto**  
   1. O tempo limite de validação a aplicar (24h, 48h, 7 dias)?

---
