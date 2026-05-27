### **\[Onboarding\] Registo de novo utilizador (titular)**

1. **Contexto**  
   1. O fluxo de registo de utilizador titular cria a conta MyEdenred e culmina com a adição do primeiro produto. Um utilizador sem produto associado não consegue navegar na aplicação após login.

2. **Funcionalidade**  
   1. O utilizador deve poder criar uma conta MyEdenred fornecendo os seus dados pessoais, validando contactos (email e telemóvel) e adicionando pelo menos um produto Edenred.

3. **Requisitos Funcionais (As-Is)**  
   1. O fluxo de registo está organizado em passos sequenciais:  
      1. **Passo 1 — Dados pessoais**: email, password, nome, NIF, código postal (trabalho **ou** residência — pelo menos um obrigatório), data de nascimento (opcional, com fins de marketing/segmentação).  
      2. **Passo 2 — Adicionar Benefícios**: o utilizador adiciona 1 a 3 benefícios (Cartão Refeição, Cartão Flexível, Wallet Creche/Educação).  
      3. **Passo 3 — Opt-in**: recolha de consentimento para envio de comunicações de marketing.  
   2. Antes de prosseguir, é enviada **validação de email** ao endereço indicado (o utilizador tem de clicar no link recebido por email).  
   3. É solicitada **validação OTP via SMS** para o número de telemóvel introduzido.  
   4. O **código postal** suporta a feature "Onde utilizar" — é usado como fallback de localização quando não há permissão GPS no dispositivo.  
   5. Após criação, o estado do registo pode ser: *aguarda validação email → aguarda adição de produto → aguarda opt-in → ativo* (entre outros).

4. **Gaps (To-Be)**  
   1. **Gaps (To-Be)**  
      1. O fluxo de registo passará a ser gerido pelo **Edenred Connect** (API Edenred), e não 100% pela aplicação como atualmente.  
      2. Implementar **mecanismos de limitação** (ex.: máximo de 3 tentativas) na adição de produtos durante o registo, para mitigar tentativas automatizadas de descoberta de números de cartão válidos *(identificado no Penetration Test)*.  
      3. Adicionar **mensagem de fallback** no processo de registo.  
      4. Configuração de **PIN e biometria** é introduzida no fluxo de onboarding.

   2. **Gaps (Sugestões)**  
      1. *Sugestão:* Bloquear a criação de contas para utilizadores que não possuam um produto Edenred válido associado ao seu NIF, mitigando o problema atual em que qualquer pessoa pode criar conta sem ter um produto (identificado em Notas Manuais).

5. **Pressupostos**  
   1. **Não haverá migração de dados** dos utilizadores atuais — os atuais utilizadores terão de fazer novo registo após o lançamento da nova versão (ver Sessões Globais).  
   2. O número de telemóvel passou a ser obrigatório em registos novos.

6. **Questões e requisitos em aberto**  
   1. A data de nascimento deve continuar opcional ou passa a ser obrigatória?  
   2. Confirmar os dados mínimos obrigatórios no novo fluxo.  
   3. Estados de registo no sistema — confirmar lista completa e transições válidas.

---
