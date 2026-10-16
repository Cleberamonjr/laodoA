# LADO A — Integração Shopify

## Arquitetura
- Frontend atual: `index.html` (landing page) e `loja.html` (catálogo + sacola).
- Backend comercial: Shopify `xsc9cb-iv.myshopify.com`.
- Moeda: BRL.
- A loja utiliza a Storefront GraphQL API; o checkout é operado pela Shopify.

## Ativação (pendente)
1. No Admin Shopify, habilitar o canal/aplicativo de venda Headless e gerar **token público** da Storefront API.
2. No GitHub, abrir `loja.html` e preencher `CONFIG.publicStorefrontToken` com o token **público**. Jamais usar token da Admin API, chave privada, ou senha.
3. Cadastrar produtos reais na Shopify com foto, descrição, variantes, preço e disponibilidade; disponibilizá-los ao canal de vendas Headless.
4. Configurar pagamentos, frete, políticas, impostos e domínio na Shopify; escolher plano apropriado antes de vender.
5. Testar a compra ponta a ponta com produto de teste e método de pagamento de testes; verificar checkout, estoque, pedido, confirmação e e-mails.

## Estado atual e limites
- Navegação de LP para a loja: implementada.
- Catálogo, variantes, sacola e encaminhamento ao checkout: código implementado, mas **não testado ponta a ponta**, pois o catálogo está vazio e o token público não foi fornecido.
- Os campos de mídia, logística, preços e políticas não devem ser preenchidos com fatos fictícios.
- Para dropshipping: validar fornecedor, origem, prazo real, rastreabilidade, tributos, devoluções e regras de atendimento antes da publicação.
- O frontend deve continuar usando somente a Storefront API com token público; ações administrativas nunca devem ser expostas no navegador.

## Critérios de aceite para lançamento
- Produtos ativos e disponíveis no canal Headless.
- Carrinho persistente, adição/edição de variantes e checkout funcionando em mobile e desktop.
- Frete e pagamentos configurados para o mercado de destino.
- Políticas comerciais e contato da loja verificados.
- Compra de teste validada (pedido, pagamento, estoque, comunicação).

## Próximas melhorias técnicas
- Página de produto com fotos, material, medidas, cuidados e política de troca.
- Filtros por categoria, material, banho, cor e faixa de preço.
- Implementação de SEO de catálogo, analytics, eventos de funil e desempenho web.
- Acessibilidade do modal da sacola: contenção de foco e restauração do foco ao botão originador.
- Revisão de tratamento de erros e paginação de produtos (atualmente primeira página de até 80 produtos).
