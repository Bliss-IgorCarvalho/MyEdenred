### **\[Onde Utilizar\] Mapa de Estabelecimentos (Cartão)**

1. **Funcionalidade**  
   1. O utilizador titular de Cartão deve poder alternar a visualização de estabelecimentos para uma **vista em mapa**, com pins, agrupamento de resultados e possibilidade de navegação (mover o mapa para refazer pesquisa).

2. **Requisitos Funcionais (As-Is)**  
   1. O mapa é apresentado através de **Google Maps API**.  
   2. As coordenadas dos estabelecimentos são fornecidas pela MyGon  
   3. O MyEdenred armazena em BD as coordenadas conhecidas para otimizar performance.  
   4. Em portal web é possível ver lista \+ mapa em simultâneo; em mobile o utilizador alterna entre as duas vistas.  
   5. Ao mover o mapa, pode refazer a pesquisa para encontrar estabelecimentos na nova área.

3. **Pressupostos**  
   1. A integração com **Google Maps API** mantém-se.

4. **Questões e requisitos em aberto**  
   1. Quais os critérios e triggers para atualização dos dados de coordenadas armazenados em BD?

---
