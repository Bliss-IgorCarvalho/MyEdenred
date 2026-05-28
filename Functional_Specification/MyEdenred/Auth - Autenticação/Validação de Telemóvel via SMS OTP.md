---
Feature-id: 9461 
Feature-url: https://dev.azure.com/edenred-ept/Myedenred/_workitems/edit/9461
Feature-Name: Validação de Telemóvel via SMS OTP  
Status: Validation  
Devops-sync: True  
Github-sync: True  
Last-update: May 28, 2026  
---

**Descrição**

O sistema deve validar a titularidade de um número de telemóvel através do envio de um código OTP por SMS, garantindo que é controlado pelo utilizador. Trata-se de um fluxo de validação transversal, acionável a partir de diferentes áreas e fluxos da aplicação. O comportamento do fluxo de validação é independente do contexto que o aciona. 

---

**Pré-condições**

1. Existe um número de telemóvel a validar, indicado pelo utilizador no contexto que aciona a validação.

---

**Regras de Negócio e Comportamentos**

1. **Contextos de Acionamento**  
   2. O fluxo de validação de telemóvel pode ser acionado a partir de múltiplos pontos da aplicação, designadamente:  
      1. **Registo de conta** — validação do número indicado.  
      2. **Alteração de número de telemóvel no perfil** — validação do novo número.  
      3. **Pagamento via Wallet** — validação por transação, sem cache de OTP por sessão.  
      4. Outros fluxos que exijam confirmação de titularidade de telemóvel.

   3. O comportamento do fluxo de validação é **o mesmo** independentemente do contexto de acionamento. As consequências pós-validação (ex.: alteração efetiva do número, autorização da transação) são da responsabilidade da feature que aciona a validação, não deste fluxo.

4. **Características do Código OTP**  
   5. O código OTP é composto por **5 dígitos numéricos**.  
   6. A **geração e validação** do OTP é da responsabilidade da aplicação MyEdenred.  
   7. A plataforma **InfoBip** é responsável exclusivamente pelo envio do SMS.

8. **Validade do Código OTP**  
   9. O código OTP tem uma validade de **10 minutos** a partir do momento do envio.  
   10. *Se* o utilizador introduzir o código após o prazo de validade: o código é rejeitado e é disponibilizada a opção de solicitar novo envio.

11. **Tentativas e Bloqueio**  
   12. São permitidas até **3 tentativas** de introdução de código falhadas por OTP.  
   13. *Se* o utilizador esgotar as 3 tentativas: a validação é **bloqueada durante 15 minutos**.  
   14. O desbloqueio é **automático** após o período de 15 minutos, não exigindo qualquer ação adicional do utilizador.

15. **Reenvio de SMS**  
   16. O utilizador pode solicitar o **reenvio do código OTP** para o mesmo número.  
   17. Deve existir um intervalo mínimo de **60 segundos** entre cada pedido de reenvio.  
   18. Não há limite de reenvios, desde que assegurado o intervalo mínimo de tempo entre cada pedido.  
   19. *Se* um novo código for enviado (por reenvio): o **código anterior é imediatamente invalidado**, permanecendo válido apenas o mais recente.

20. **Consumo do Código**  
   21. *Após* validação bem-sucedida: o código OTP é **consumido e inutilizado**, não podendo ser reutilizado.

22. **Pressuposto Técnico**  
   23. A geração e validação do OTP e do envio do SMS é responsabilidade da da plataforma InfoBip.

---

**Pós-condições**

1. *Se* validação bem-sucedida: o número de telemóvel é marcado como validado e o controlo retorna ao fluxo que acionou a validação.  
2. Código OTP consumido e invalidado após utilização.  
3. *Se* validação não concluída (bloqueio ou abandono): o número não é validado; o efeito sobre a conta ou transação depende do contexto de acionamento. 

---