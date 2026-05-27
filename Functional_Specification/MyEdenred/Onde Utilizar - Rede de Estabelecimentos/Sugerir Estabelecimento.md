### **\[Onde Utilizar\] Sugerir Estabelecimento**

1. **Funcionalidade**  
   1. O utilizador deve poder sugerir um novo estabelecimento para ser incluído na rede Edenred, através de um formulário que cria uma lead no Salesforce da equipa comercial Edenred.

2. **Requisitos Funcionais (As-Is)**  
   1. A opção **"Sugerir estabelecimento"** está disponível na secção "Onde utilizar".  
   2. O formulário pede: NIF do estabelecimento, nome, contacto.  
   3. O envio cria uma **lead no Salesforce** Edenred.  
   4. O utilizador recebe uma resposta de sucesso/insucesso (no fluxo da app).  
   5. A funcionalidade está disponível tanto para Cartões como para Wallets, mas:  
      1. Em **Cartão Refeição / Flexível**, a sugestão aparece em **primeiro lugar** na lista.  
      2. Em **Wallets** (Educação), a sugestão aparece em **último lugar**.

3. **Pressupostos**  
   1. A integração com **Salesforce** mantém-se.  
   2. A definição do **HTML do formulário** é fornecida pela Edenred

4. **Gaps (To-Be)**  
   1. Tornar a funcionalidade **"Sugerir Parceiro" configurável** (ativável/desativável) via **feature flag**.

5. **Questões e requisitos em aberto**  
   1. O fluxo despoletado pelo Salesforce (resposta ao utilizador, follow-up comercial) gera notificação ao utilizador na app?  
   2. Pendente confirmar se já há acesso à API

---

# Vantagens

## **Epic \[Vantagens\] Vantagens Edenred**

---
