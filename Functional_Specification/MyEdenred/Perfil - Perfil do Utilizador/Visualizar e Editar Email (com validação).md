### **\[Perfil\] Visualizar e Editar Email (com validação)**

1. **Funcionalidade**  
   1. O utilizador deve poder alterar o seu email, mediante envio de email de validação para o novo endereço. O email anterior permanece em vigor até a alteração ser validada.

2. **Requisitos Funcionais (As-Is)**  
   1. O utilizador introduz o novo email; o sistema envia link de validação para esse endereço.  
   2. Enquanto o novo email não é validado, o **email anterior** permanece em vigor para todos os efeitos (login, comunicações).  
   3. O estado "pendente de validação" pode permanecer indefinidamente sem timeout.  
   4. Atualmente **não existe alerta visual** no perfil a relembrar a alteração pendente.

3. **Gaps (To-Be)**  
   1. *Sugestão:* Introduzir **tempo limite** para validação do novo email — ver Feature 5\.  
   2. *Sugestão:* Adicionar **indicador visual** no perfil enquanto a alteração estiver pendente.

---
