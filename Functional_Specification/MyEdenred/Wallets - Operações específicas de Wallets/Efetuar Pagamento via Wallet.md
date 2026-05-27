### **\[Benefícios-Wallets\] Efetuar Pagamento via Wallet**

1. **Contexto**  
   1. As Wallets são o único produto digital com transações realizadas dentro da app MyEdenred. Cada pagamento exige validação OTP via SMS.

2. **Funcionalidade**  
   1. O utilizador owner de uma Wallet deve poder efetuar pagamentos a estabelecimentos aderentes a partir da aplicação, mediante validação OTP via SMS.

3. **Requisitos Funcionais (As-Is)**  
   1. O utilizador acede à tab "Pagar" no detalhe da wallet (apenas owner; **não disponível para associado** — embora associado não exista em wallets).  
   2. O fluxo é: nº do aluno → pesquisa de estabelecimento (ou seleção de perfil existente) → introduzir montante → confirmar → **validação OTP via SMS** → resultado.  
   3. **Valor mínimo de pagamento**: 1 cêntimo.  
   4. **Valor máximo de pagamento**: 25.000 € *(Notas Manuais)*.  
   5. Após confirmação OTP, o saldo é descontado, surge nova linha nos movimentos e (no caso do primeiro pagamento a um estabelecimento) é criado o Perfil de Pagamento.  
   6. O OTP é solicitado **a cada pagamento** (sem cache de sessão).

4. **Pressupostos**  
   1. O backend transacional continua a ser **Paytec**, com pré-validação Edenred.

5. **Questões e requisitos em aberto**  
   1. Definir o detalhe completo do fluxo MBWay In-App (UX, validações, integração).  
   2. Comportamento em caso de falha do envio OTP — retry, mudança de canal, etc.

---

# Suporte

## **Epic \[Suporte\] Informações de Suporte e Destaques**

---
