# Milestone-1-SSC0219-BetterView
Milestone 1 da disciplina Introdução a Web Development (SSC0219) - ICMC USP. Protótipo SPA de e-commerce de óculos (BetterView).
## 1. Requisitos Específicos do Projeto
Além dos requisitos padrões de Clientes, Administradores e Carrinho de Compras, nossa aplicação implementa:
* **Funcionalidade Específica (Filtro por Formato de Rosto):** Mecanismoque permite ao usuário filtrar o catálogo de óculos de acordo com o formato do seu rosto (Quadrado, Redondo ou Oval), alterando dinamicamente o DOM para exibir apenas os produtos compatíveis.

## 2. Descrição do Projeto e Arquitetura SPA
A aplicação foi feita seguindo o modelo de Single-Page Application (SPA), centralizando a estrutura em um único arquivo principal . 

 **Nota Importante para a Milestone 1:** Como as funções de alternância dinâmica do JavaScript (manipulação do DOM para ocultar/exibir seções) serão implementadas e avaliadas apenas nas próximas fases do projeto, **todas as interfaces obrigatórias desta entrega (Vitrine, Área do Cliente/Checkout e Painel Administrativo) foram colocadas na mesma página**. Isso permite a validação imediata do design, Nas próximas entregas, essas áreas serão devidamente trabalhadas e atualizadas.

### Navegação :
1. **Home (Vitrine):** Tela pública onde qualquer usuário pode visualizar os óculos disponíveis, aplicar o Filtro por Formato de Rosto e acessar a modal/tela de Login.
2. **Área do Cliente:** Permite revisar os itens adicionados ao carrinho, selecionar a forma de pagamento (PIX, Cartão ou PayPal) e simular a finalização da compra.
3. **Área do Administrador:** Interface exclusiva com a tabela CRUD estruturada para o gerenciamento de estoque (visualização inicial de ID, preços, estoque e ações de edição/exclusão).

### Diagrama :
```
                  [ TELA 1: HOME / VITRINE ] 
                   (Pública para Visitantes)
                             │
            ┌────────────────┴────────────────┐
            ▼                                 ▼
    [ Filtro de Rosto ]               [ Menu de Navegação ]
 (Filtra óculos na tela)                      │
                                              ▼
                                       [Alternar Telas]
                                              │
                      ┌───────────────────────┴───────────────────────┐
                      ▼                                               ▼
         [ TELA 2: ÁREA DO CLIENTE ]                     [ TELA 3: ÁREA DO ADMINISTRADOR ]
                      │                                               │
         ┌────────────┴────────────┐                     ┌────────────┴────────────┐
         ▼                         ▼                     ▼                         ▼
   [ Carrinho ]            [ Forma Pagto ]         [ Tabela CRUD ]         [ Estoque ]
 (Exibe Produtos)       (PIX/Cartão/PayPal)     (Editar/Excluir)         (Visualizar)
```


