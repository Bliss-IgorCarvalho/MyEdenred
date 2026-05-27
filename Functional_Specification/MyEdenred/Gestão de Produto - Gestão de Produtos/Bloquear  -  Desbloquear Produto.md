### **\[Benefícios\] Bloquear / Desbloquear Produto**

1. **Funcionalidade**  
   1. O utilizador owner de um produto deve poder bloquear e desbloquear o produto a partir da aplicação, por exemplo em caso de perda ou suspeita de fraude.

2. **Requisitos Funcionais (As-Is)**  
   1. A ação **"Bloquear cartão"** está disponível no detalhe do cartão para o **owner**.  
   2. O bloqueio é refletido no serviço externo do Novo Banco (impede transações reais).  
   3. O **Utilizador Associado não pode** bloquear nem desbloquear o cartão.  
   4. Wallets também podem ser bloqueadas (refletido na Paytec).

3. **Questões e requisitos em aberto**  
   1. Cartões bloqueados por utilizadores do Backoffice devem assumir o mesmo estado “bloqueado” ou deve existir um estado de bloqueio específico para quando a ação é realizada via Backoffice?

---
