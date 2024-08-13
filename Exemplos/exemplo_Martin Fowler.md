# Padrões de Requisitos e Regras de Negócio - Sistema de Supermercado

## Padrão: Cadastro de Produtos

### Descrição
Este padrão descreve a funcionalidade de cadastro de produtos no sistema do supermercado, permitindo que gerentes e administradores insiram, editem e excluam produtos do catálogo.

### Requisitos

- **Nome do Produto:** Deve ser único dentro do sistema e descritivo.
- **Código do Produto:** Um identificador único para cada produto, utilizado para rastreamento e gestão.
- **Categoria:** O produto deve ser associado a uma categoria, como "Alimentos", "Bebidas", "Higiene", etc.
- **Preço:** O preço do produto deve ser inserido com duas casas decimais, permitindo variações por promoção ou desconto.
- **Quantidade em Estoque:** Indica a quantidade disponível do produto em estoque. Deve ser atualizada automaticamente após cada venda.
- **Data de Validade:** Para produtos perecíveis, deve ser informado o prazo de validade.
- **Fornecedor:** Associar o produto a um fornecedor cadastrado no sistema.

### Fluxo

1. O administrador acessa a página de cadastro de produtos.
2. O administrador preenche as informações requeridas (Nome, Código, Categoria, etc.).
3. O sistema valida as informações inseridas.
4. Se os dados forem válidos, o sistema armazena o novo produto no catálogo.
5. O sistema exibe uma confirmação do cadastro e redireciona o administrador para a lista de produtos.

### Exceções

- **3a.** Se o nome ou código do produto já existir, o sistema exibe uma mensagem de erro e solicita a correção.
- **3b.** Se a data de validade estiver expirada, o sistema alerta o administrador e impede o cadastro.

---

## Padrão: Gestão de Inventário

### Descrição
Este padrão define as funcionalidades de monitoramento e atualização do inventário de produtos, garantindo que as informações de estoque estejam sempre precisas.

### Requisitos

- **Atualização Automática:** O estoque deve ser atualizado automaticamente após cada venda.
- **Alertas de Baixa Quantidade:** O sistema deve gerar alertas quando a quantidade de um produto estiver abaixo de um nível mínimo definido.
- **Histórico de Movimentações:** Cada alteração no estoque deve ser registrada, incluindo data, hora, quantidade alterada, e motivo (venda, reposição, ajuste).
- **Relatórios de Inventário:** Permitir que os administradores gerem relatórios detalhados de estoque, incluindo produtos com baixa quantidade, produtos próximos da validade, e movimentações recentes.

### Fluxo

1. O sistema atualiza automaticamente o estoque após cada transação de venda.
2. O sistema verifica se algum produto atingiu o nível mínimo de estoque.
3. Se um produto estiver com baixa quantidade, o sistema envia um alerta para o administrador.
4. O administrador pode revisar o histórico de movimentações e gerar relatórios conforme necessário.

### Exceções

- **3a.** Se um produto estiver fora de estoque, o sistema desativa temporariamente sua venda até que o estoque seja reabastecido.

---

## Padrão: Processo de Compra

### Descrição
Este padrão descreve o fluxo de compras no supermercado, desde a seleção de produtos até o pagamento.

### Requisitos

- **Carrinho de Compras:** Os clientes devem poder adicionar produtos ao carrinho, visualizar o total e aplicar cupons de desconto.
- **Métodos de Pagamento:** O sistema deve suportar múltiplos métodos de pagamento, incluindo cartão de crédito, débito, e pagamentos eletrônicos.
- **Confirmar Pedido:** O cliente deve revisar o pedido antes de confirmar a compra.
- **Envio de Notificações:** Após a compra, o cliente deve receber um e-mail ou SMS confirmando o pedido, com os detalhes da compra e prazo de entrega (se aplicável).
- **Histórico de Compras:** O cliente deve poder acessar o histórico de compras no perfil.

### Fluxo

1. O cliente seleciona os produtos desejados e os adiciona ao carrinho de compras.
2. O cliente revisa os itens no carrinho e pode aplicar cupons de desconto.
3. O cliente escolhe o método de pagamento e insere os detalhes necessários.
4. O cliente confirma o pedido, e o sistema processa o pagamento.
5. O sistema atualiza o estoque conforme a quantidade de produtos vendidos.
6. O sistema envia uma confirmação de pedido ao cliente por e-mail ou SMS.

### Exceções

- **4a.** Se o pagamento for recusado, o sistema exibe uma mensagem de erro e permite que o cliente tente novamente ou escolha outro método de pagamento.
- **4b.** Se algum item no carrinho estiver fora de estoque no momento da confirmação, o sistema avisa o cliente e sugere alternativas.

---

## Regras de Negócio

### RB01: Preço Promocional

- **Descrição:** Produtos podem ter preços promocionais que substituem temporariamente o preço normal.
- **Regra:** O sistema deve permitir a definição de um período para o preço promocional, após o qual o preço retorna ao normal.
- **Prioridade:** Alta

### RB02: Limite de Quantidade por Cliente

- **Descrição:** Para evitar a escassez de produtos, alguns itens podem ter uma quantidade máxima por cliente.
- **Regra:** O sistema deve impedir que um cliente adicione ao carrinho mais do que a quantidade permitida para esses itens.
- **Prioridade:** Média

### RB03: Validade de Cupons de Desconto

- **Descrição:** Cupons de desconto possuem uma data de validade.
- **Regra:** O sistema deve verificar a validade do cupom antes de aplicá-lo ao carrinho.
- **Prioridade:** Alta

### RB04: Reabastecimento Automático de Estoque

- **Descrição:** O sistema pode sugerir automaticamente pedidos de reabastecimento para produtos que atingiram o nível mínimo de estoque.
- **Regra:** O sistema deve enviar uma sugestão de reabastecimento ao fornecedor quando o estoque estiver abaixo do nível mínimo.
- **Prioridade:** Média

### RB05: Avaliação de Produtos

- **Descrição:** Clientes podem avaliar e comentar sobre produtos comprados.
- **Regra:** O sistema deve permitir que clientes deixem avaliações após a compra e deve moderar comentários ofensivos.
- **Prioridade:** Baixa