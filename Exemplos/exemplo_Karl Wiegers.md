# Requisitos Funcionais e Não Funcionais para Sistema de Supermercado

## Requisitos Funcionais (RF)

### RF01: Cadastro de Produtos

- **Descrição:** O sistema deve permitir o cadastro de novos produtos no inventário do supermercado.
- **Entrada:** Nome do produto, Categoria, Preço, Quantidade em estoque, Código de barras.
- **Saída:** Confirmação de cadastro do produto no sistema.
- **Pré-condições:** O produto deve possuir um código de barras único e válido.
- **Pós-condições:** O produto é registrado no banco de dados e está disponível para venda.

### RF02: Atualização de Preços

- **Descrição:** O sistema deve permitir a atualização do preço de produtos existentes.
- **Entrada:** Código de barras, Novo preço.
- **Saída:** Confirmação de atualização do preço.
- **Pré-condições:** O produto deve estar previamente cadastrado no sistema.
- **Pós-condições:** O preço do produto é atualizado no sistema e refletido nas vendas.

### RF03: Controle de Estoque

- **Descrição:** O sistema deve controlar a quantidade de produtos em estoque e alertar quando um produto estiver abaixo do nível mínimo.
- **Entrada:** Quantidade de produtos vendidos.
- **Saída:** Atualização automática do estoque, Alerta de baixo estoque (se aplicável).
- **Pré-condições:** O produto deve estar cadastrado e disponível no estoque.
- **Pós-condições:** O estoque é atualizado corretamente após cada venda.

### RF04: Processamento de Venda

- **Descrição:** O sistema deve permitir o processamento de vendas no ponto de venda (PDV).
- **Entrada:** Produtos selecionados, Quantidade, Código de barras, Forma de pagamento.
- **Saída:** Comprovante de venda, Atualização do estoque.
- **Pré-condições:** Os produtos devem estar cadastrados e disponíveis no estoque.
- **Pós-condições:** A venda é registrada, o estoque é atualizado e o pagamento é confirmado.

### RF05: Geração de Relatórios

- **Descrição:** O sistema deve permitir a geração de relatórios diários, semanais e mensais de vendas e estoque.
- **Entrada:** Período de tempo para o relatório.
- **Saída:** Relatório detalhado em formato PDF ou Excel.
- **Pré-condições:** O sistema deve estar operando corretamente com dados de vendas e estoque atualizados.
- **Pós-condições:** Relatório gerado e disponível para análise.

## Requisitos Não Funcionais (RNF)

### RNF01: Desempenho

- **Descrição:** O sistema deve processar uma venda em até 2 segundos.
- **Prioridade:** Alta
- **Critério de Medição:** Testes de desempenho devem ser realizados para garantir que o sistema atende a esse requisito.

### RNF02: Segurança

- **Descrição:** O sistema deve proteger os dados dos clientes e transações com criptografia.
- **Prioridade:** Alta
- **Critério de Medição:** Implementação de criptografia SSL/TLS em todas as transações e dados sensíveis.

### RNF03: Usabilidade

- **Descrição:** O sistema deve ser intuitivo e fácil de usar para funcionários de todos os níveis.
- **Prioridade:** Média
- **Critério de Medição:** Realizar testes de usabilidade com usuários representativos para validar a facilidade de uso.

### RNF04: Disponibilidade

- **Descrição:** O sistema deve estar disponível 99,9% do tempo durante o horário de funcionamento do supermercado.
- **Prioridade:** Alta
- **Critério de Medição:** Monitoramento contínuo da disponibilidade do sistema com alertas automáticos em caso de falhas.

### RNF05: Compatibilidade

- **Descrição:** O sistema deve ser compatível com os principais navegadores e sistemas operacionais utilizados no supermercado.
- **Prioridade:** Média
- **Critério de Medição:** Testes de compatibilidade devem ser realizados em diferentes ambientes operacionais.

---

## Fluxo de Uso (Exemplo: RF04 - Processamento de Venda)

### Atores:
- **Caixa:** Funcionário responsável pelo processamento das vendas.
- **Cliente:** Pessoa que está comprando produtos.

### Fluxo Principal:
1. O caixa seleciona os produtos comprados pelo cliente.
2. O sistema lê o código de barras de cada produto.
3. O sistema calcula o total da compra.
4. O cliente escolhe a forma de pagamento (dinheiro, cartão de crédito, débito, etc.).
5. O caixa processa o pagamento.
6. O sistema gera e imprime o comprovante de venda.
7. O sistema atualiza o estoque com as quantidades vendidas.

### Fluxo Alternativo:
- **4a.** Se o pagamento for recusado, o sistema exibe uma mensagem de erro e retorna ao passo 4 para que o cliente tente outra forma de pagamento.

### Pré-condições:
- Os produtos devem estar cadastrados no sistema e disponíveis em estoque.

### Pós-condições:
- A venda é registrada, o estoque é atualizado e o cliente recebe o comprovante.

---

## Modelo de Dados (Simplificado)

```markdown
# Entidades Principais

## Produto
- **Atributos:**
  - ID do Produto (Código de Barras) [PK]
  - Nome do Produto
  - Categoria
  - Preço
  - Quantidade em Estoque

## Venda
- **Atributos:**
  - ID da Venda [PK]
  - Data da Venda
  - Total da Venda
  - Forma de Pagamento

## Item da Venda
- **Atributos:**
  - ID do Item [PK]
  - ID da Venda [FK]
  - ID do Produto [FK]
  - Quantidade Vendida
  - Preço Unitário

# Relacionamentos
- **Produto** 1:N **Item da Venda**
- **Venda** 1:N **Item da Venda**
