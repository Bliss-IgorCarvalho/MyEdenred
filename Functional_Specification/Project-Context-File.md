# Visão Geral

# **Visão Geral**

---

## **O Sistema/Aplicação**

**MyEdenred** é a aplicação mobile (iOS \+ Android) e portal web que permite a utilizadores finais gerir os benefícios sociais e extra-salariais atribuídos pelas suas entidades empregadoras via Edenred Portugal. É o principal ponto de contacto digital entre a Edenred e o utilizador final (o trabalhador/colaborador).

O sistema inclui também um Backoffice usado por equipas internas da Edenred (Marketing & Media e Customer Support) para suporte operacional e gestão de comunicações e conteúdos.

---

## **O Utilizador**

### **App / Portal Web (utilizador final)**

1. **Quem é o utilizador**  
   1. Colaborador/trabalhador de uma empresa portuguesa que recebe benefícios sociais (subsídio de refeição, benefícios de creche/educação, etc.) através da Edenred. Tipicamente acede via app mobile, pontualmente via portal web.

2. **Contexto de utilização**  
   1. Uso recorrente em mobilidade — consultar saldo antes de pagar uma refeição (geralmente com picos de utilização no final/início do mês, de dia 25 a dia 5 do mês seguinte), verificar movimentos, gerir o cartão. Frequência tipicamente diária ou semanal. O utilizador espera respostas imediatas (saldo atualizado, transações listadas) e fluxos curtos.

3. **Perfis do Sistema**  
   1. **Titular (Utilizador Registado)**  
      1. Descrição: Utilizador final que criou conta, adicionou pelo menos um produto e completou o onboarding. É o detentor primário dos produtos associados à sua conta.  
      2. Notas: Pode consultar saldo e movimentos, bloquear/desbloquear cartão, gerir PIN, fazer pagamentos, adicionar/remover produtos, consultar a rede de estabelecimentos, aceder a vantagens, autorizar utilizadores associados, gerir perfil e consentimentos. 

   2. **Utilizador Associado (Segundo Titular)**  
      1. Descrição: Utilizador com permissão de leitura sobre o cartão de outro utilizador (o titular principal). Caso de uso típico: cônjuge que acompanha o saldo do cartão do parceiro. Aplicável apenas a Cartões — Wallets não admitem Utilizador Associado.  
      2. Notas: Pode consultar saldo e movimentos do cartão partilhado. Não pode bloquear o cartão, alterar PIN nem realizar pagamentos com o cartão do titular. 

### **Backoffice (utilizador interno Edenred)**

1. **Quem é o utilizador**  
   1. Equipas internas da Edenred Portugal — Marketing & Media (campanhas, comunicações, programa de vantagens) e Customer Support (apoio operacional aos utilizadores finais).

2. **Contexto de utilização**  
   1. Uso em ambiente de escritório, em desktop, durante o horário de trabalho. Sessões mais longas que as do utilizador final, focadas em tarefas operacionais (criar campanha, tratar pedido de cliente, atualizar conteúdo).

3. **Perfis do Sistema**  
   1. **Administrador** \- Tem acesso a todas as áreas do sistema  
   2. **Call Center** \- Tem acesso à Gestão de Utilizadores  
   3. **Marketing** \- Tem acesso às Notificações e Segmentos

---

## **O Projeto**

O projeto atual consiste no **redesign e reconstrução completa** da app e portal web MyEdenred, com nova stack tecnológica, nova UX/UI, backoffice renovado e funcionalidades novas, mantendo todas as funcionalidades existentes.

**Dentro do escopo:**

* App mobile **Flutter** (iOS \+ Android)  
* Portal web (versão browser da app)  
* Backoffice (módulo único, em Umbraco) com dois domínios funcionais: Marketing & Media e Customer Support  
* Analytics integrado via **Piano.io**

**Fora do escopo:**

* **Portal do Cliente** empresarial (sistema separado para a empresa empregadora que contrata Edenred)  
* **App Global Edenred** (plataforma de grupo, projeto paralelo gerido centralmente). No contexto deste projeto esta app apenas é base de benchmark.  
* Infraestrutura de processamento financeiro (mantida em sistemas externos — Novo Banco, Paytec)  
* Integração MBWay

---

# Arquitetura

# **Arquitetura**

---

## **Componentes Principais (escopo do projeto)**

* **App Mobile (Flutter)**  
  * **Papel**: Interface principal do utilizador final em iOS e Android.  
  * **Notas**: Cross-platform com Flutter; entregue em paralelo para as duas plataformas a partir do mesmo código-base.

* **Portal Web**  
  * **Papel**: Versão browser da app, para utilizadores finais que prefiram desktop ou que precisem de aceder fora do contexto mobile.  
  * **Notas**: Paridade funcional com a app mobile.

* **Backoffice**  
  * **Papel**: Interface interna usada pelas equipas Edenred (Marketing & Media e Customer Support) para gestão operacional do produto.  
  * **Notas**: Módulo único, implementado em Umbraco. Inclui gestão de segmentos, notificações, banners/carrossel, programa de vantagens, contas de utilizadores e auditoria. As ações ficam registadas com canal "backoffice".

---

## **Integrações e Sistemas Externos**

* **App Gateway / APIM**  
  * **Papel**: Ponto de entrada unificado para todas as chamadas à API Edenred a partir das interfaces (App, Portal, Backoffice).  
  * **Notas**: Gere os rate limits de autenticação. Os rate limits de associação de produto são geridos pela aplicação, não pelo APIM.

* **Ping Identity**  
  * **Papel**: Utilizado como Identity Provider / Identity Server

* **Novo Banco**  
  * **Papel**: Backend transacional dos produtos da categoria Cartão (Cartão Refeição, Cartão Flexível).  
  * **Notas**: Responsável pela camada transacional e processamento financeiro dos cartões físicos.

* **Paytec**  
  * **Papel**: Backend transacional dos produtos da categoria Wallet (Wallet Creche, Wallet Educação).  
  * **Notas**: A pré-validação de operações é feita pela Edenred antes de chegar à Paytec.

* **MyGon**  
  * **Papel**: Parceiro tecnológico que fornece a rede de estabelecimentos aderentes e a camada de vantagens dos cartões.  
  * **Notas**:  
    * Gere georreferenciação, base de dados de estabelecimentos, vantagens e promoções (Cartão Flexível) e filtros de pesquisa na secção "onde utilizar". Os dados da MyGon **não são editáveis** pelo Backoffice MyEdenred.  
    * Pode vir a ser descontinuada, sendo substituída por serviços da API Google Maps.

* **Salesforce**  
  * **Papel**: Sistema de sugestão de estabelecimentos.  
  * **Notas**: Mantida do escopo atual. O fluxo de sugestão de estabelecimentos não é uma integração direta via API, mas sim um processo de *Web to Lead* feito através de um formulário em HTML fornecido pela Edenred e enviado ao Salesforce.

* **InfoBip**   
  * Plataforma externa de envio de SMS OTP. Usada no registo (validação de telemóvel) e na autenticação MFA.

* **Piano.io**  
  * Plataforma externa de analytics comportamental selecionada para o novo projeto. Permite monitorizar comportamentos e interações dos utilizadores dentro da app (por menu, por ação/feature). Substitui o papel de analytics que o Firebase tinha anteriormente.

* **Firebase / Crashlytics**  
  * Plataforma Google usada **exclusivamente para Crashlytics** (monitorização e reporte de crashes da app). Não desempenha o papel de analytics — essa função é da [Piano.io](http://Piano.io).

* **Google Maps API**  
  * Utilizado para apresentação dos estabelecimentos parceiros mais próximos do utilizador em google maps.

* **OneTrust**  
  * Plataforma de Gestão de Consentimentos (CMP) a ser utilizada pela aplicação.

---

# Glossário

# **Glossário**

---

### **MyEdenred**

* **Descrição**:  
  * A aplicação mobile e portal web que o utilizador final usa para gerir benefícios, consultar saldos, movimentos e aceder a vantagens. É o produto a ser reconstruído neste projeto.  
* **Sinónimos**:  
  * "a app", "MyEden", "MER", "My Edenred App"  
* **Não confundir com**:  
  * Global App Edenred (produto do grupo, distinto);   
    Portal do Cliente (interface para empresas empregadoras, fora do escopo deste projeto).

---

### **Cliente Edenred**

* **Descrição**:  
  * A empresa empregadora que contrata os serviços Edenred e é responsável pelo carregamento de benefícios nos cartões/wallets dos seus colaboradores.  
* **Sinónimos**:  
  * "cliente", "empresa cliente", "empregador"  
* **Pressupostos**:  
  * O Cliente tem acesso a um portal próprio (Portal do Cliente), distinto do MyEdenred. O presente projeto não toca nesse portal.

---

### **Produto Edenred**

* **Descrição**:  
  * Benefício atribuído pela empresa empregadora ao utilizador final. Divide-se em duas categorias tecnicamente distintas: **Cartão** (físico, suportado pelo Novo Banco) e **Wallet** (digital, suportada pela Paytec). Atualmente existem 4 produtos disponíveis: Cartão Refeição, Cartão Flexível, Wallet Creche, Wallet Educação.  
* **Pressupostos**:  
  * Atualmente existem 4 produtos no total, e irá evoluir para 6\.  
  * A associação de Produto a Utilizador é feita através do NIF, fornecida por um novo serviço a desenvolver pela Edenred.

---

### **Cartão**

* **Descrição**:  
  * Categoria de Produto Edenred, instrumento físico (plástico) emitido pela Edenred. Identificado por número de cartão de 16 dígitos. Utilizado em pontos de venda e estabelecimentos aderentes.  
* **Sinónimos**:  
  * "Cartão Edenred"  
* **Pressupostos**:  
  * O cartão chega ao utilizador **ativo**, é utilizável no ponto de venda sem qualquer passo na app. Adicionar o cartão à app é opcional e serve apenas para consulta e gestão (saldo, movimentos, bloqueio, PIN).  
  * **Não suporta** integração com Apple Pay / Google Pay (limitação do esquema de cartão — não é VISA/Mastercard aberto).  
  * Permite alteração de PIN diretamente na app.  
  * Backend: Novo Banco.  
  * Tipos atuais de Cartão:  
    * **Cartão Refeição**: Subsídio de alimentação. Isento de IRS e Segurança Social até ao limite legal diário. Produto mais utilizado.  
    * **Cartão Flexível**: Multi-benefício. Permite gastos em diferentes categorias (Saúde, Educação, Apoio Social).

---

### **Wallet**

* **Descrição**:  
  * Categoria de Produto Edenred, instrumento puramente digital, sem cartão físico. Identificada por **Wallet ID**.  
* **Sinónimos**:  
  * "e-Wallet", "carteira digital"  
* **Pressupostos**:  
  * **Não Suporta** Apple Pay e Google Pay; a adesão é feita dentro da app.  
  * Não admite Utilizador Associado — apenas o titular tem acesso.  
  * Backend: Paytec, com pré-validação pela Edenred.  
  * Tipos atuais de Wallet:  
    * **Wallet Creche**: Pagamento de creche para crianças em idade pré-escolar.  
    * **Wallet Educação**: Despesas educativas para estudantes em ensino básico, secundário ou superior.

---

### **Cartão Digital**

* **Descrição**:  
  * Esta é uma versão exclusivamente digital do cartão (sem suporte físico), planeada para o futuro. Embora a sua implementação ainda não tenha ocorrido e não integre o âmbito do presente projeto, é fundamental assegurar que os fluxos agora concebidos permitam a sua integração futura sem comprometer a interoperabilidade do sistema.

---

### **Segmento**

* **Descrição**:  
  * Agrupamento de utilizadores criado no Backoffice através de filtros (produto, localidade, estado, opt-in, etc.) ou por upload de ficheiro Excel com product IDs ou emails. Usado como destino para envio de notificações ou campanhas.

---

### **App Global Edenred**

* **Descrição**:  
  * Aplicação do grupo Edenred, gerida internacionalmente. Projeto distinto e paralelo ao MyEdenred PT.  
* **Pressupostos**:  
  * A equipa PT não esteve envolvida na concepção da App Global.  
  * No contexto deste projeto esta app apenas é base de benchmark.

---

# Pressupostos Gerais

# **Pressupostos Gerais**

---

1. **Não haverá migração de dados de utilizadores.** Os atuais utilizadores do MyEdenred terão de fazer novo registo após o lançamento.

2. **A associação Produto ↔ Utilizador é feita por NIF**, através de um novo serviço a desenvolver pela Edenred.

3. **NIF não é fiável** como identificador único no estado atual (existem múltiplos utilizadores com o mesmo NIF na BD). Está prevista uma operação Edenred para corrigir os NIFs errados.

4. **Edenred Connect**: Serviço atual de autenticação que será descontinuado e substituído pelo Ping Identity.

---

