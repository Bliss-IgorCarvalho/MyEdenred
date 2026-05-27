### **\[BO-Utilizadores\] Registo de Atividade do Utilizador**

1. **Funcionalidade**  
   1. O colaborador deve poder consultar o histórico de atividade do utilizador MyEdenred, ações realizadas (login, logout, confirmação de email, etc.) com data/hora e canal (app, web, backoffice).

2. **Requisitos Funcionais (As-Is)**  
   1. Tab "Registo de Atividade" no detalhe do utilizador.  
   2. Cada entrada exibe data/hora e **canal**.  
   3. Existem filtros (tipo de atividade, data, canal).  
   4. Atualmente as ações feitas pelo Backoffice ficam marcadas com canal "backoffice", mas **não há identificação clara do colaborador** que executou a ação (apenas o canal).

3. **Gaps (To-Be)**  
   1. **Identificar o colaborador (operador) específico** que executou cada ação no Backoffice — ponto crítico levantado em auditoria interna Edenred (Demo Backoffice).  
   2. *Sugestão:* Definir **política de retenção** dos logs de atividade *(questão das Notas Manuais)*.

4. **Questões e requisitos em aberto**  
   1. Confirmar se o auditoria atual já regista o operador na BD (mesmo que não exposto no BO).  
   2. Quais as ações que devem ficar auditadas? As mesmas disponíveis no filtro atual?

---

# BO \- Gestão de Colaboradores

## **Epic \[BO — Colaboradores\] Gestão de Colaboradores do Backoffice**

---
