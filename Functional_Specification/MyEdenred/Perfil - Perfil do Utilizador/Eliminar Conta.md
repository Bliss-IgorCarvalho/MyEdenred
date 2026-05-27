### **\[Perfil\] Eliminar Conta *(Feature Nova)***

1. **Contexto**  
   1. Atualmente o processo de eliminação de conta MyEdenred é **manual**, despoletado por envio de email para o DPO. As novas regras da Apple Store e da Google Play exigem que o utilizador possa eliminar a sua conta diretamente na aplicação.

2. **Funcionalidade**  
   1. O utilizador deve poder iniciar/solicitar o processo de eliminação da sua conta MyEdenred diretamente a partir do perfil, sem necessidade de contacto manual com o DPO.

3. **Requisitos Iniciais**  
   1. A ação "Eliminar conta" deve estar disponível a partir do ecrã de perfil.  
   2. O fluxo deve incluir confirmação explícita do utilizador.  
   3. Após eliminação, o utilizador pode criar uma nova conta normalmente (não há restrições legais nesse sentido).

4. **Pressupostos**  
   1. Não confundir com **pedido de esquecimento** (RGPD) que exige tratamento adicional caso a caso pelo DPO.

5. **Questões e requisitos em aberto**  
   1. O fluxo deve ser apenas na app/portal ou também no Backoffice (apoio a utilizador)?  
   2. Deve haver retenção de dados após eliminação (logs, histórico)? Definir política.  
   3. Comportamento esperado em caso de existência de produtos com saldo positivo?  
   4. Tem implicação no fluxo de pedido formal de **esquecimento RGPD** (diferente de eliminar conta)?  
   5. Eliminar conta com saldo positivo: Quando um utilizador tenta eliminar a conta e tem saldo positivo numa Wallet, qual o comportamento esperado? (a) bloquear a eliminação e informar o utilizador; (b) avisar o utilizador mas permitir prosseguir; (c) alguma outra estratégia?  
   6. Reactivação: Após eliminar uma conta, o utilizador pode criar uma nova conta com o mesmo email? Se sim, os benefícios anteriores ficam disponíveis para reassociação ou têm de ser adicionados de novo?

---
