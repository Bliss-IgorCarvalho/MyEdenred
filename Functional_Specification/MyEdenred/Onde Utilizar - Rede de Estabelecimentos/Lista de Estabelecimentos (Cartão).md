### **\[Onde Utilizar\] Lista de Estabelecimentos (Cartão)**

1. **Contexto**  
   1. A funcionalidade "Onde Utilizar" apresenta a rede de estabelecimentos onde o utilizador pode usar os seus produtos.

2. **Funcionalidade**  
   1. O utilizador titular de um Cartão deve poder consultar uma lista paginada de estabelecimentos aderentes, ordenada por distância à localização atual ou ao código postal do perfil.

3. **Requisitos Funcionais (As-Is)**  
   1. A lista é gerada com base em dados da **MyGon**.  
   2. Apenas são apresentados estabelecimentos que aceitam os **produtos associados à conta do utilizador**.  
   3. A localização usada segue a seguinte ordem de precedência:   
      1. localização GPS (se autorizada)  
      2. código postal do perfil (trabalho).  
      3. código postal do perfil (residência).  
   4. A lista é paginada (≈ 20-30 estabelecimentos por página).  
   5. Cada estabelecimento exibe: nome, morada, distância, categoria, indicação de promoção (se aplicável).

4. **Pressupostos**  
   1. Para **Cartões**, os dados vêm da **MyGon** (atualizados periodicamente, não em tempo real). O fluxo é diferente do das Wallets.  
   2. A integração com a **MyGon mantém-se**; os dados não são editáveis pelo Backoffice MyEdenred.

5. **Questões e requisitos em aberto**  
   1. A periodicidade de atualização dos dados MyGon do lado MyEdenred (cache em BD para coordenadas) — confirmar lógica e tempo de refresh.  
   2. Os campos exibidos na lista de estabelecimento Wallet devem ser os mesmos exibidos atualmente?

---
