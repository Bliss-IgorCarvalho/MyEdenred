---
Feature-id: [9460](https://dev.azure.com/edenred-ept/Myedenred/_workitems/edit/9460) 
Feature-Name: Validação de Email via OTP  
Status: Validation  
Devops-sync: True  
Github-sync: True  
Last-update: May 28, 2026  
---

**Descrição**

O sistema deve validar a titularidade de um endereço de email através do envio de um código OTP para esse endereço, garantindo que é controlado pelo utilizador. Trata-se de um fluxo de validação transversal, acionável a partir de diferentes áreas e fluxos da aplicação. O comportamento do fluxo de validação é independente do contexto que o aciona.

---

**Pré-condições**

1. Existe um endereço de email a validar, indicado pelo utilizador no contexto que aciona a validação.

---

**Regras de Negócio e Comportamentos**

1. **Contextos de Acionamento**  
   2. O fluxo de validação de email pode ser acionado a partir de múltiplos pontos da aplicação, designadamente:  
      1. **Registo de conta** — validação do email indicado.  
      2. **Alteração de email no perfil** — validação do novo endereço.  
      3. Outros fluxos que exijam confirmação de titularidade de email.

   3. O comportamento do fluxo de validação é **o mesmo** independentemente do contexto de acionamento. As consequências pós-validação (ex.: ativação da conta, substituição do email anterior) são da responsabilidade da feature que aciona a validação, não deste fluxo.

4. **Características do Código OTP**  
   5. O código OTP é composto por **5 dígitos numéricos**.

6. **Validade do Código OTP**  
   7. O código OTP tem uma validade de **10 minutos** a partir do momento do envio.  
   8. *Se* o utilizador introduzir o código após o prazo de validade: o código é rejeitado e é disponibilizada a opção de solicitar novo envio.

9. **Tentativas e Bloqueio**  
   10. São permitidas até **3 tentativas** de introdução de código falhadas por OTP.  
   11. *Se* o utilizador esgotar as 3 tentativas: a validação é **bloqueada durante 15 minutos**.  
   12. O desbloqueio é **automático** após o período de 15 minutos, não exigindo qualquer ação adicional do utilizador.

13. **Reenvio do Código**  
   14. O utilizador pode solicitar o **reenvio do código OTP** para o mesmo endereço.  
   15. Deve existir um intervalo mínimo de **60 segundos** entre cada pedido de reenvio.  
   16. Não há limite de reenvios, desde que assegurado o intervalo mínimo de tempo entre cada pedido.  
   17. *Se* um novo código for enviado (por reenvio): o **código anterior é imediatamente invalidado**, permanecendo válido apenas o mais recente.

18. **Consumo do Código**  
   19. *Após* validação bem-sucedida: o código OTP é **consumido e inutilizado**, não podendo ser reutilizado.

20. **Pressupostos Técnicos**  
   21. O envio de E-mail OTP é assegurado pela plataforma **InfoBip**.

---

**Pós-condições**

1. *Se* validação bem-sucedida: o endereço de email é marcado como validado e o controlo retorna ao fluxo que acionou a validação.  
2. Código OTP consumido e invalidado após utilização.  
3. *Se* validação não concluída (bloqueio ou abandono): o endereço não é validado; o efeito sobre a conta depende do contexto de acionamento.

---
