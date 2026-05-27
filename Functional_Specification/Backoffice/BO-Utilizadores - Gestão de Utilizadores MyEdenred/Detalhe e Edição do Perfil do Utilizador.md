### **\[BO-Utilizadores\] Detalhe e Edição do Perfil do Utilizador**

1. **Funcionalidade**  
   1. O colaborador Call Center / Admin deve poder consultar o detalhe completo do utilizador (dados pessoais, estado, consentimentos), e efetuar ações de apoio: reenviar email de validação, recuperar password, suspender/reativar, editar dados pessoais (incluindo apagar telemóvel), gerir opt-in.

2. **Requisitos Funcionais (As-Is)**  
   1. Página de detalhe mostra dados pessoais (nome, email, NIF, data nascimento, telemóvel, género), estado do registo, datas de registo/atualização, consentimentos, toggles para marketing.  
   2. Ações disponíveis:  
      1. **Reenviar email de validação**.  
      2. **Pedido de recuperação de password** (envio de email).  
      3. **Suspender** / **Reativar** o utilizador.  
      4. **Editar dados pessoais** (nome, email, data nascimento, código postal).  
      5. **Editar opt-in** de marketing.  
      6. **Apagar número de telefone** (não é possível definir um novo — só apagar; ao apagar, o utilizador entra em estado "aguarda informações adicionais" e é forçado a inserir e validar um novo número no próximo login).  
   3. Estados do utilizador incluem: aguarda validação email, aguarda adição de produto, aguarda opt-in, ativo, suspenso, aguarda readicionar cartão, aguarda validação alteração email, aguarda informações adicionais.

3. **Questões e requisitos em aberto**  
   1. A informação de gênero não está disponível em My Edenred e foi referido em reuniões que é um dado que não é utilizado para segmentação. Deve ser removido ou continua?  
   2. O que acontece quando no Backoffice se altera a password de um utilizador MyEdenred — fluxo, notificação, expiração?  
   3. Diferença entre **"Estado do Utilizador"** e **"Estado do Registo"** *(questão das Notas Manuais)*.  
   4. Pendente revisão e definição dos estados possíveis para o utilizador.

---
