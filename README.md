# Milestone 1 - SSC0219 - BetterView
**Disciplina:** Introdução a Web Development (2026) - ICMC USP  
**Desenvolvedor:** Marcos Vinicius Rodrigues da Costa - NUSP: 18119590

### 📝 Descrição Geral da Loja
A **BetterView** é um e-commerce especializado na venda de óculos variados, focado em oferecer uma experiência personalizada de escolha de armações. O objetivo principal da plataforma é unir usabilidade simplificada e sofisticação visual, permitindo que os clientes encontrem a armação ideal e realizem compras de forma fluida através de um ecossistema digital moderno e acessível.

---

## 1. Requirements
Além dos requisitos padrão de gerenciamento fornecidos no escopo da disciplina, a nossa implementação adiciona os seguintes requisitos específicos de negócio:
* **Filtro por tipo de rosto:** Seleção dinâmica no catálogo com base no formato de rosto do usuário (Redondo, Quadrado, Oval ou Coração), exibindo apenas as armações recomendadas por especialistas.
* **Módulo de Checkout Adaptativo:** Fluxo de pagamento que oculta ou exibe campos de forma condicional (ex: oculta o campo de número do cartão se a opção selecionada for PIX ou PayPal).
* **Acessibilidade Semântica:** Utilização rigorosa de tags HTML5 estruturais e atributos `alt` descritivos e precisos em todas as mídias para compatibilidade com leitores de tela.

---

## 2. Project Description
A aplicação foi arquitetada seguindo o modelo de **Single-Page Application (SPA)**, centralizando toda a experiência do usuário dentro de um único arquivo estrutural (`index.html`). 

⚠️ **Nota para a Avaliação da Milestone 1:** Dado que os mecanismos automatizados de manipulação do DOM e alternância lógica com JavaScript serão desenvolvidos nas fases seguintes, **todas as três interfaces obrigatórias (Vitrine, Área do Cliente/Checkout e Painel Administrativo) foram dispostas sequencialmente na mesma página**. Isso visa permitir aos revisores uma avaliação imediata ,nas próximas entregas, essas áreas serão devidamente trabalhadas e atualizadas.

### A. Functionalities to be Implemented
* **Catálogo e Filtro de Rosto:** Filtragem de produtos no client-side alterando o DOM sem requisições de página.
* **Carrinho de Compras:** Adição de itens, cálculo de subtotal automático e controle de quantidade local.
* **Autenticação Fictícia:** Login do administrador (`admin/admin`) chaveando os privilégios da SPA.
* **Gerenciamento de Estoque (CRUD):** Interface tabular para inclusão, edição e exclusão de itens de forma reativa.

### B. Navigation Diagram
```text
                  [ TELA 1: HOME / VITRINE ] 
                   (Pública para Visitantes)
                             │
            ┌────────────────┴────────────────┐
            ▼                                 ▼
    [ Filtro de Rosto ]               [ Menu de Navegação ]
 (Filtra óculos na tela)                      │
                                              ▼
                               [ Alternância Dinâmica de Telas ]
                                              │
                      ┌───────────────────────┴───────────────────────┐
                      ▼                                               ▼
         [ TELA 2: ÁREA DO CLIENTE ]                     [ TELA 3: ÁREA DO ADMINISTRADOR ]
                      │                                               │
         ┌────────────┴────────────┐                     ┌────────────┴────────────┐
         ▼                         ▼                     ▼                         ▼
   [ Carrinho ]            [Forma Pagamentoto]         [ Tabela CRUD ]         [ Estoque ]
 (Exibe Produtos)       (PIX/Cartão/PayPal)           (Editar/Excluir)         (Visualizar)
```

### C. Information to be Saved on the Server
Para as etapas funcionais, mapeamos as seguintes entidades de dados que serão salvas no servidor (ou simuladas no ambiente de testes local):
* **User (Administrador / Cliente):** Nome, ID único, e-mail, telefone e endereço de entrega.
* **Product (Óculos):** ID único, nome do modelo, descrição visagista, preço unitário, URL da imagem, quantidade atual em estoque e métrica de unidades vendidas.
* **Order (Pedido):** ID do pedido, ID do cliente, array de produtos comprados, valor total final e método de pagamento utilizado.

---

## 3. Comments About the Code
* A estrutura foi modularizada utilizando seções independentes (`<section>`) identificadas por IDs exclusivos (`screen-vitrine`, `screen-cart`, `screen-admin`), o que facilitará a ocultação/exibição dinâmica por meio de classes CSS via JavaScript na Milestone 2.
* Estilizações específicas e críticas para layout em grade foram estruturadas em CSS Grid e Flexbox no início do arquivo para mitigar travamentos de renderização (layout shifts).

---

## 4. Test Plan
* **Testes Manuais:** Cenários de clique e fluxos de preenchimento de formulários serão verificados manualmente no cliente em  navegadores como o  Chrome:
* **Validação de Inputs:** Testar manualmente se os formulários de checkout aceitam dados fictícios e se disparam os alertas corretos para cada método de pagamento (PIX, PayPal, Cartão).
* **Interatividade do DOM:** Verificar se o menu dropdown de Filtro por Formato de Rosto oculta e exibe os óculos corretos na vitrine após as ações de clique.
* **Persistência Local:** Validar visualmente se os itens adicionados ao carrinho permanecem salvos durante a navegação entre os estados da SPA.

---

---

## 5. Test Results

---

## 6. Build Procedures
Por se tratar de um protótipo estritamente frontend e client-side nesta Milestone 1:
1. Realize o download ou clone este repositório público do GitHub.
2. Certifique-se de que os arquivos de mídia das imagens estejam localizados na mesma pasta raiz que o arquivo principal.
3. Dê um clique duplo no arquivo **`index.html`** para executá-lo nativamente em qualquer navegador moderno de sua escolha. Não há pré-requisitos de instalação de servidores ou compilers nesta fase.

---

## 7. Problems
* **Dimensionamento de Imagens de Estúdio:** Inicialmente, imagens com formatos heterogêneos quebraram o alinhamento das caixas, problema contornado com a implementação das propriedades CSS `object-fit: contain` e fundos em tom pastel neutro.


---

## 8. Comments
* O projeto priorizou a integridade semântica exigida pelas regras de acessibilidade da disciplina desde o primeiro dia de codificação, garantindo uma fundação sólida para a adição de regras de JavaScript interativas.
