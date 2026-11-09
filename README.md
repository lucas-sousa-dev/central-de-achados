# Central de Achados 🛍️

Vitrine independente e responsiva de produtos divulgados por links de afiliados, com foco inicial no **Mercado Livre** e estrutura preparada para integrar a **Shopee** após aprovação e verificação de suas regras.

## Links
- Site: https://lucas-sousa-dev.github.io/central-de-achados/
- Repositório: https://github.com/lucas-sousa-dev/central-de-achados
- Portal relacionado: https://github.com/lucas-sousa-dev/cria-rj

## Funcionalidades implementadas
- Identidade visual azul e branca, cabeçalho, banner e layout responsivo.
- Pesquisa por nome, categoria e loja; filtros horizontais.
- Catálogo externo em `data/products.json`, separado da interface.
- Nove produtos iniciais do Mercado Livre, com links de afiliados fornecidos anteriormente.
- Botões de compra com identificação de publicidade e abertura da loja parceira.
- Espaço para imagem oficial; sem imagem verificada, aparece um ícone ilustrativo com aviso.
- Sem preços inventados ou descontos fictícios.

## Como testar no celular
1. Abra o link do site acima (aguarde alguns minutos após cada commit).
2. Pesquise por **Motorola** e confira o filtro **Eletrônicos**.
3. Selecione **Casa e Decoração** e veja se os produtos mudam.
4. Toque em **Ver produto** e confirme que o anúncio correto abre no Mercado Livre.
5. Se a página antiga continuar, atualize o navegador.

## Como cadastrar novos produtos
Edite `data/products.json` e acrescente um objeto ao array `products` com:
- `id`: identificador único;
- `title`: nome real do produto;
- `category`: categoria;
- `store`: loja parceira;
- `url`: link de afiliado válido;
- `icon`: ícone de fallback;
- `image`: URL HTTPS **somente quando autorizada e verificada**; caso contrário, `null`;
- `price`: preço verificado ou `null`;
- `verified`: `true` apenas quando o preço foi confirmado e permanece válido.

O site carrega esse JSON a cada abertura. Para a Central de Notícias reutilizar o catálogo, a integração deverá ler a mesma fonte e tratar eventuais falhas de carregamento.

## Situação atual e limites
- **Publicado via GitHub Pages**, conforme configuração do repositório.
- A busca atual pesquisa somente os produtos cadastrados; **não pesquisa milhões de anúncios**.
- **Não há API de Mercado Livre ou Shopee conectada**, nem descoberta automática de produtos, criação automática de links de comissão, atualização de preços ou publicação automática em redes sociais.
- Imagens reais não foram obtidas ou validadas por uma integração oficial; por isso há placeholders discretos.
- Links e disponibilidade devem ser revisados periodicamente.
- O site não processa pagamentos: a compra ocorre nas lojas parceiras.
- Nunca colocar tokens de API ou senhas no JSON ou em arquivos públicos do GitHub Pages.

## Próximas etapas
1. Validar links e imagens reais via fontes oficiais/autorizadas.
2. Ampliar catálogo e permitir importação em lote.
3. Investigar APIs e permissões dos programas de afiliados; automatizar somente o que for autorizado.
4. Compartilhar o catálogo com a seção de ofertas do portal `cria-rj`.
5. Gerar artes para WhatsApp e Instagram e estudar agendamento por integrações oficiais.
6. Incluir monitoramento de links, métricas de cliques e documentação de alterações.

## Histórico
- 2026-11-08: primeira vitrine com catálogo embutido.
- 2026-11-08: reformulação visual, catálogo JSON externo, filtros, busca e README detalhado.

## Observações
A Central de Achados é uma vitrine independente de afiliados. Marcas e plataformas citadas pertencem aos respectivos titulares. Preços, frete e disponibilidade são definidos pelos vendedores.

## Envio simplificado por link (2026-11-08)
- Foi adicionado à página inicial um campo **Envie um achado com apenas um link**.
- O usuário cola o link de afiliado e toca em **Copiar para enviar**; o texto fica pronto para colar na conversa com o Jarvis.
- **Importante:** essa ação NÃO publica o produto automaticamente nem envia dados a servidores. O cadastro é feito posteriormente pelo assistente após conferir os dados possíveis e atualizar `data/products.json` no GitHub.
- O site aceita links HTTPS de domínios conhecidos do Mercado Livre e Shopee; a validação de domínio não comprova que o link gera comissão.
- As imagens oficiais continuam pendentes até a identificação exata do anúncio e de uma fonte autorizada. Não substituir por imagem de produto semelhante.
- Não foi implementada coleta automática de páginas externas no navegador: links curtos e políticas de acesso podem impedir extração confiável de metadados.
