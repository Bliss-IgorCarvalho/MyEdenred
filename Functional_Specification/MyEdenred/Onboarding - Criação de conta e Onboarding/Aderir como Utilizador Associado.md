### **\[Onboarding\] Aderir como Utilizador Associado**

1. **Contexto**  
   1. Um Utilizador Associado é alguém com permissão de leitura sobre o cartão de outro utilizador (caso de uso típico: cônjuge). Apenas aplicável a **Cartões** — Wallets não admitem Utilizadores Associados.

2. **Funcionalidade**  
   1. Um utilizador deve poder adicionar à sua conta um cartão de que **não é titular**; nesse caso, o titular (owner) recebe um alerta e tem de aceitar a associação, após o que o segundo utilizador passa a ter acesso de leitura ao cartão.

3. **Requisitos Funcionais (As-Is)**  
   1. Quando um utilizador tenta adicionar um cartão já existente na BD, o sistema deteta a colisão e envia um **alerta ao owner por email** a pedir permissão.  
   2. O owner pode **aceitar** ou **recusar** o pedido.  
   3. Se aceitar, o cartão fica disponível na conta do segundo utilizador com **acesso de leitura** (saldo e movimentos).  
   4. O Utilizador Associado **não pode**: bloquear/desbloquear o cartão, alterar PIN, efetuar pagamentos com o cartão.  
   5. Um cartão pode ter **múltiplos Utilizadores Associados** (sem limite estrito atualmente).  
   6. Enquanto o pedido está pendente de aprovação, o cartão aparece a cinzento na conta do associado, sem informação de saldo ou movimentos, com mensagem de "pendente de permissão".  
   7. O titular pode posteriormente **remover** Utilizadores Associados a partir do detalhe do cartão.

4. **Gaps (To-Be)**  
   1. Em discussão a introdução de **limite de Utilizadores Associados por cartão** (1 ou 2 — TBC) como medida de segurança *(reunião Demo Site 14/04)*.  
   2. Em análise: opção do owner passar a convidar um associado para o cartão

5. **Questões e requisitos em aberto**  
   1. Definir o limite final de Utilizadores Associados por cartão.  
   2. O fluxo de aceitação/recusa pelo owner ocorre dentro da app (área de notificações) ou apenas por email com link?  
   3. Qual o tempo de validade do pedido pendente?  
   4. Utilizador Associado — lado da associação — Quando o titular aceita um pedido de associação, a associação fica registada apenas no MyEdenred (nosso lado) ou também no Edenred Connect? O Edenred Connect precisa de ser notificado para que o utilizador associado consiga ver o saldo do cartão?

---
