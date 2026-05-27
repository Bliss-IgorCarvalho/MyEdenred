### **\[BO-Notificações\] Criar Notificação**

1. **Funcionalidade**  
   1. O Marketing deve poder criar uma notificação, definindo: nome, segmento (destinatários), tipo (in-app, push, email), título e mensagem, link interno/externo opcional, e momento de envio (imediato, agendado, indefinido).

2. **Requisitos Funcionais (As-Is)**  
   1. Formulário modal de criação.  
   2. **Tipos**: in-app (obrigatório se houver push), push (obrigatoriamente acompanhada de in-app), email.  
   3. Para **email** existem 2 templates: email de **publicidade** (com unsubscribe) ou **de serviço** (sem unsubscribe).  
   4. Email atualmente raramente é usado — Edenred tem ferramenta dedicada externa para email marketing.  
   5. Para **push e in-app**: título (até 255 caracteres — limitação distinta entre push e in-app) e mensagem, em plain text. Não suporta imagem.  
   6. **Envio**: imediato, agendado para data/hora futura, ou estado "indefinido" (rascunho).  
   7. O envio é **síncrono** mas processa por segmento — em segmentos grandes (utilizadores com opt-in geral, antigos) pode demorar **muitas horas** (até 12h).  
   8. O envio push utiliza atualmente Google Mobile Services e Apple Push Notification Service diretamente.

3. **Gaps (To-Be)**  
   1. Otimizar a performance do envio de notificações em segmentos grandes, alinhado com gap de segmentos da feature “data purging”.  
   2. Avaliar suporte a **imagem na push** (atualmente texto apenas; existe suporte iOS para imagem)

4. **Pressupostos**  
   1. Envio de push notifications será migrado para InfoBip.

5. **Questões e requisitos em aberto**  
   1. Quando selecionado “*todos*” como segmento para envio de notificações, definir quais estados de utilizador devem ser considerados, para evitar envio de notificações para utilizadores inativos ou “inválidos”. 

---
