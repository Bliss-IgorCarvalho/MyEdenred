### **\[Auth\] Validação de Telemóvel via SMS OTP**

1. **Funcionalidade**  
   1. O sistema deve validar o número de telemóvel do utilizador em momentos-chave (registo, alteração no perfil, pagamentos via wallet), através de envio de código OTP via SMS.

2. **Requisitos Funcionais (As-Is)**  
   1. A validação de telemóvel ocorre nos seguintes momentos:  
      * **Registo de conta** (uma vez)  
      * **Alteração de número de telemóvel no perfil**  
      * **Cada pagamento via Wallet** (sem cache de OTP por sessão)  
   2. Se o utilizador não completar a validação OTP após alteração de telemóvel, o número **não é alterado** — o anterior permanece em vigor (não há estado "pendente").  
   3. A plataforma de envio de SMS OTP é **InfoBip**.  
   4. A geração e validação do OTP é da responsabilidade da aplicação; a InfoBip apenas envia o SMS.  
   5. O código OTP tem 5 dígitos *(a confirmar)*.

3. **Pressupostos**  
   1. A integração com a InfoBip mantém-se no novo escopo.

4. **Questões e requisitos em aberto**  
   1. O OTP tem 5 ou 6 dígitos?   
   2. Qual o tempo de validade do OTP?  
   3. Quantas tentativas falhadas são permitidas antes de bloqueio temporário?

---
