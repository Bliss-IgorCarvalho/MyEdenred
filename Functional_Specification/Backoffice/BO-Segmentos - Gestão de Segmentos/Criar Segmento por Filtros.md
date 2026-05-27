### **\[BO-Segmentos\] Criar Segmento por Filtros**

1. **Funcionalidade**  
   1. O Marketing deve poder criar um segmento de utilizadores combinando filtros: produto, opt-in publicidade, localidade, género (atualmente "outdated"), data de nascimento, estado do registo, intervalo de datas de registo.

2. **Requisitos Funcionais (As-Is)**  
   1. Formulário com filtros combináveis.  
   2. **Localidade**: agrupada por distrito → concelho.  
   3. **Género** atualmente não é fiável (foi removido do registo).  
   4. **Data de nascimento** exclui utilizadores que não preencheram (campo opcional).  
   5. **Estado do registo**: ativo, intermediários (validou email mas não adicionou produto, etc.), suspensos. Normalmente usa-se estado "ativo" ou nenhum filtro.  
   6. **Intervalo de datas de registo** com presets ou customizado.  
   7. Após adicionar, o segmento entra em processamento (pode demorar minutos) e é gravado.

3. **Gaps (To-Be)**  
   1. **Excluir utilizadores inativos** automaticamente dos filtros (problema atual: segmentos consideram utilizadores antigos que nunca mais usam a plataforma, tornando o processamento moroso).  
   2. Considerar **NIF do empregador** (cliente Edenred) como filtro — pain point crítico (caso Galp/Repsol — Demo).  
   3. Remover ou ocultar o filtro **Género** se já não é fiável.

4. **Questões e requisitos em aberto**  
   1. Confirmar lista completa de estados de utilizador a expor como filtro.  
   2. Avaliar viabilidade técnica de incluir NIF empresarial como dimensão de segmentação.

---
