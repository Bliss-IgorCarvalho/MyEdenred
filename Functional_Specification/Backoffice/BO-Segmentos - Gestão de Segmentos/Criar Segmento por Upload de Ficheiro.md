### **\[BO-Segmentos\] Criar Segmento por Upload de Ficheiro**

1. **Funcionalidade**  
   1. O Marketing deve poder criar um segmento importando um ficheiro Excel com **Product IDs** (números de cartão / Wallet IDs) ou **Emails**.

2. **Requisitos Funcionais (As-Is)**  
   1. Função descarregar template (atualmente não funciona)  
   2. Upload de ficheiro Excel.  
   3. Conteúdo possível: lista de **Product IDs** ou lista de **Emails**.  
   4. O sistema utiliza a primeira linha do ficheiro que estiver preenchida  
   5. É permitido apenas ficheiro xlsx de até 15 MB  
   6. É permitido o carregamento de apenas 1 ficheiro por segmento   
   7. Após upload, o segmento é processado e fica disponível.

3. **Questões e requisitos em aberto**  
   1. Qual é o formato exato do ficheiro?  
   2. Aceita apenas 1 única coluna (**Product IDs** ou **Emails**), ou tem coluna de identificação de tipo, ou uma coluna para cada?  
   3. É possível carregar um ficheiro com **Product IDs** e **Emails** em simultâneo?  
   4. Qual o fluxo de erro esperado em caso de ficheiros inválidos?  
   5. Há uma função de download de template. Onde é feito o upload deste template?

---
