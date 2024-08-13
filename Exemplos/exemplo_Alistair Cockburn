# Caso de Uso: Sistema de Supermercado

## Atores:
- **Cliente:** Pessoa que compra produtos no supermercado.
- **Caixa:** Funcionário que realiza o checkout e finaliza as compras.
- **Gerente:** Pessoa responsável por gerenciar o estoque e registrar novos produtos.
- **Sistema:** O software que automatiza as funções do supermercado.

---

## UC01: Registro de Novo Produto

### Descrição:
O gerente registra um novo produto no sistema para que ele esteja disponível para venda.

### Fluxo Principal:
1. O gerente acessa o sistema de gerenciamento de produtos.
2. O gerente insere as informações do produto (nome, categoria, preço, quantidade em estoque).
3. O sistema valida as informações e registra o produto.
4. O sistema confirma o registro do produto.

### Fluxo Alternativo:
- **3a.** Se as informações do produto forem inválidas, o sistema exibe mensagens de erro e retorna ao passo 2.

### Pré-condições:
- O gerente deve estar autenticado no sistema.

### Pós-condições:
- O produto deve estar disponível no sistema para venda e estoque atualizado.

---

## UC02: Gerenciamento de Estoque

### Descrição:
O gerente atualiza o estoque de produtos no sistema.

### Fluxo Principal:
1. O gerente acessa a seção de gerenciamento de estoque.
2. O gerente seleciona o produto a ser atualizado.
3. O gerente insere a nova quantidade em estoque.
4. O sistema valida as informações e atualiza o estoque.
5. O sistema confirma a atualização do estoque.

### Fluxo Alternativo:
- **3a.** Se a quantidade em estoque for inválida, o sistema exibe mensagens de erro e retorna ao passo 3.

### Pré-condições:
- O gerente deve estar autenticado no sistema.
- O produto deve estar previamente registrado no sistema.

### Pós-condições:
- O estoque do produto é atualizado no sistema.

---

## UC03: Processo de Compra

### Descrição:
O cliente seleciona produtos para compra e finaliza a compra no caixa.

### Fluxo Principal:
1. O cliente seleciona os produtos nas prateleiras e os leva ao caixa.
2. O caixa escaneia os códigos de barras dos produtos.
3. O sistema calcula o total da compra.
4. O cliente escolhe a forma de pagamento (cartão, dinheiro, etc.).
5. O caixa finaliza a compra e o sistema atualiza o estoque dos produtos comprados.
6. O sistema gera um recibo e o entrega ao cliente.

### Fluxo Alternativo:
- **4a.** Se a forma de pagamento for cartão e ele for recusado, o sistema solicita uma nova forma de pagamento.
- **5a.** Se o sistema detectar que um produto não tem estoque suficiente, o caixa deve informar o cliente e remover o item da compra.

### Pré-condições:
- O sistema deve estar operando normalmente.
- Os produtos devem estar previamente registrados e com estoque disponível.

### Pós-condições:
- O cliente finaliza a compra e recebe o recibo.
- O estoque dos produtos comprados é atualizado.

---

## UC04: Devolução de Produto

### Descrição:
O cliente devolve um produto e o caixa processa a devolução.

### Fluxo Principal:
1. O cliente solicita a devolução de um produto no caixa.
2. O caixa verifica as condições de devolução (prazo, estado do produto, recibo).
3. O sistema processa a devolução e atualiza o estoque do produto.
4. O sistema emite um comprovante de devolução e reembolsa o valor ao cliente.

### Fluxo Alternativo:
- **2a.** Se as condições de devolução não forem atendidas, o sistema informa o cliente e a devolução é recusada.

### Pré-condições:
- O produto deve ter sido comprado no supermercado.
- O cliente deve apresentar o recibo de compra.

### Pós-condições:
- O produto é devolvido ao estoque, e o cliente é reembolsado.

---

## UC05: Relatório de Vendas

### Descrição:
O gerente gera relatórios de vendas diários, semanais ou mensais.

### Fluxo Principal:
1. O gerente acessa a seção de relatórios do sistema.
2. O gerente seleciona o período do relatório (diário, semanal, mensal).
3. O sistema gera o relatório de vendas com os dados solicitados.
4. O sistema exibe e permite o download do relatório em formato PDF.

### Fluxo Alternativo:
- **3a.** Se não houver vendas no período selecionado, o sistema informa que não há dados disponíveis.

### Pré-condições:
- O gerente deve estar autenticado no sistema.
- Devem existir registros de vendas no período selecionado.

### Pós-condições:
- O gerente obtém um relatório detalhado das vendas.

---

# Requisitos Associados

## RF01: Cadastro de Produtos
- **Descrição:** O sistema deve permitir o cadastro de novos produtos com as informações necessárias (nome, categoria, preço, estoque).
- **Prioridade:** Alta

## RF02: Controle de Estoque
- **Descrição:** O sistema deve permitir o gerenciamento do estoque, com atualização automática após as vendas.
- **Prioridade:** Alta

## RF03: Processamento de Compras
- **Descrição:** O sistema deve processar compras, calcular o total, e atualizar o estoque automaticamente.
- **Prioridade:** Alta

## RF04: Geração de Relatórios
- **Descrição:** O sistema deve gerar relatórios de vendas para análise gerencial.
- **Prioridade:** Média

## RNF01: Segurança de Dados
- **Descrição:** O sistema deve proteger todas as informações com criptografia.
- **Prioridade:** Alta

## RNF02: Performance
- **Descrição:** O sistema deve processar as operações em tempo real, sem atrasos perceptíveis para o usuário.
- **Prioridade:** Alta
