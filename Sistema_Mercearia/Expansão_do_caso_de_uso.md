# Casos de Uso

## UC01: Realizar Venda

### Ator(es):
* Cliente
* Operador do caixa
* Sistema de pagamento

### Interessado(s) e interesse(s):
* **Cliente**: Efetuar a compra de produtos de forma rápida e eficiente.
* **Operador do caixa**: Processar a venda de maneira correta e garantir o pagamento adequado.
* **Sistema de pagamento**: Facilitar a transação financeira com segurança.

### Pré-condições:
* O sistema de mercearia está em pleno funcionamento.
* O cliente selecionou os produtos que deseja comprar e está pronto para finalizar a compra.
* As formas de pagamento aceitas (dinheiro, cartões, Pix, vale refeição) estão disponíveis.

### Pós-condições:
* A venda foi registrada no sistema.
* O pagamento foi processado corretamente.
* O comprovante de pagamento foi emitido para o cliente.

### Questões em aberto:
* Quais são os limites para pagamentos com vale refeição?
* O sistema deve registrar informações específicas sobre clientes recorrentes?
* Existe alguma integração com programas de fidelidade?

### Fluxo Principal:

1. O cliente seleciona os produtos e dirige-se ao caixa.
2. [IN] O operador do caixa registra os itens no sistema.
3. [OUT] O sistema calcula e exibe o valor total da compra.
4. [IN] O operador do caixa confirma o fechamento da compra.
5. [OUT] O sistema exibe as formas de pagamento disponíveis.
6. [IN] O cliente escolhe a forma de pagamento e procede com a transação.
   6.1. Pagamento em dinheiro.  
   6.2. Pagamento com cartão de débito.  
   6.3. Pagamento com cartão de crédito.  
   6.4. Pagamento via Pix.  
   6.5. Pagamento com vale refeição.
7. [OUT] O operador do caixa valida o pagamento e entrega o comprovante ao cliente.

### Variantes:

**6.1 Pagamento em dinheiro**  
6.1.1. O cliente entrega o valor em espécie.  
6.1.2. O operador do caixa registra o valor recebido no sistema.  
6.1.3. O sistema calcula o troco, se aplicável.  
6.1.4. O operador do caixa devolve o troco ao cliente, se houver.

**6.2 Pagamento com cartão de débito**  
6.2.1. O cliente insere o cartão na máquina de pagamento.  
6.2.2. O sistema envia os dados de pagamento para a operadora de cartões.  
6.2.3. A operadora autoriza a transação.  
6.2.4. O sistema confirma a realização do pagamento.

**6.3 Pagamento com cartão de crédito**  
6.3.1. O cliente insere o cartão na máquina de pagamento.  
6.3.2. O sistema exibe as opções de parcelamento, se houver.  
6.3.3. O cliente seleciona a opção desejada.  
6.3.4. O sistema envia os dados para a operadora de cartões.  
6.3.5. A operadora aprova a transação e autoriza o parcelamento.

**6.4 Pagamento via Pix**  
6.4.1. O sistema gera um código QR para a transação.  
6.4.2. O cliente utiliza seu aplicativo bancário para escanear o QR e realizar o pagamento.  
6.4.3. O sistema de pagamento confirma a transação.  
6.4.4. O sistema registra o pagamento.

**6.5 Pagamento com vale refeição**  
6.5.1. O cliente insere o cartão de vale refeição na máquina de pagamento.  
6.5.2. O sistema envia os dados para a operadora de cartões.  
6.5.3. A operadora autoriza a transação.  
6.5.4. O sistema confirma o pagamento.

### Exceções:

* **E1**: O sistema de pagamento está indisponível.  
  1. O operador do caixa solicita ao cliente outro método de pagamento ou orienta a tentar novamente mais tarde.
* **E2**: O cartão de crédito ou débito é recusado.  
  1. O operador informa ao cliente que a transação foi negada e sugere o uso de outra forma de pagamento.
* **E3**: O cliente não possui saldo suficiente no vale refeição.  
  1. O operador do caixa informa o cliente sobre o saldo insuficiente e oferece a possibilidade de pagar a diferença com outro método.
* **E4**: Falha na leitura do cartão de crédito/débito/vale refeição.  
  1. O operador do caixa solicita ao cliente que insira ou aproxime o cartão novamente.  
  2. Se o erro persistir, o operador pede ao cliente que use outro método de pagamento ou tente outro cartão.
* **E5**: O sistema não gera o código QR para pagamento via Pix.  
  1. O operador do caixa tenta gerar um novo código QR.  
  2. Se o erro continuar, o operador sugere ao cliente o uso de outra forma de pagamento.
* **E6**: O cliente não consegue completar o pagamento via Pix (ex.: falha na internet ou no aplicativo bancário).  
  1. O operador oferece ao cliente a opção de usar outro método de pagamento ou tentar novamente em outro momento.  
  2. Se o problema persistir, a venda pode ser cancelada e reiniciada.
* **E7**: O sistema não calcula corretamente o troco para pagamento em dinheiro.  
  1. O operador do caixa verifica manualmente o valor do troco e devolve ao cliente.  
  2. O operador reporta o erro ao suporte técnico para futura correção.
* **E8**: Falta de energia elétrica ou falha no sistema no meio da venda.  
  1. O operador do caixa informa ao cliente sobre o problema.  
  2. Se houver gerador ou sistema de backup, o processo é retomado a partir do ponto em que parou.  
  3. Caso contrário, o operador orienta o cliente a esperar ou voltar em outro momento.
* **E9**: O sistema de pagamento por cartão/Pix está lento ou apresenta latência.  
  1. O operador do caixa solicita ao cliente que aguarde o processamento.  
  2. Se o tempo de espera exceder um limite aceitável, o operador oferece ao cliente a opção de pagar em dinheiro ou com outro método.

---

## UC02: Cancelar Venda

### Ator(es):
* Operador do caixa
* Cliente

### Interessado(s) e interesse(s):
* **Cliente**: Cancelar uma compra por motivos diversos (por exemplo, erro na escolha do produto ou indisponibilidade financeira).
* **Operador do caixa**: Concluir o processo de cancelamento de forma precisa e rápida.

### Pré-condições:
* A venda deve estar registrada no sistema, mas ainda não deve ter sido finalizada (sem emissão de comprovante).

### Pós-condições:
* A venda é cancelada e os produtos retornam ao inventário.
* Nenhum pagamento é processado, ou o valor é estornado.

### Questões em aberto:
* Existe algum prazo ou política de cancelamento após a finalização da venda?

### Fluxo Principal:

1. O cliente solicita o cancelamento da venda ao operador do caixa.
2. [IN] O operador do caixa acessa o sistema de vendas e seleciona a venda atual.
3. [OUT] O sistema exibe os itens da venda em processo.
4. [IN] O operador do caixa confirma o cancelamento da venda.
5. [OUT] O sistema cancela a venda e reverte os itens ao estoque.
6. [IN] Se o pagamento já tiver sido realizado, o sistema inicia o processo de estorno ou devolução do valor.
   6.1. Estorno no caso de pagamento via cartão de crédito/débito.  
   6.2. Devolução em dinheiro se o pagamento tiver sido em espécie.  
   6.3. Cancelamento imediato no caso de Pix ou vale refeição.

### Variantes:

**6.1 Estorno no cartão de crédito/débito**  
6.1.1. O sistema envia os dados da transação de estorno para a operadora de cartões.  
6.1.2. A operadora confirma o estorno.  
6.1.3. O sistema registra a conclusão do estorno.

**6.2 Devolução em dinheiro**  
6.2.1. O operador do caixa devolve o valor total ao cliente em espécie.  
6.2.2. O sistema registra que a venda foi cancelada e o pagamento restituído.

**6.3 Cancelamento do Pix**  
6.3.1. O sistema envia a solicitação de cancelamento para o sistema de pagamentos Pix.  
6.3.2. O sistema confirma o cancelamento e atualiza o status da venda.

**6.4 Cancelamento de vale refeição**  
6.4.1. O sistema reverte a transação junto à operadora de cartões de vale refeição.  
6.4.2. A operadora confirma o cancelamento.  
6.4.3. O sistema registra o cancelamento e o estorno do saldo.

### Exceções:

* **E1**: O estorno no cartão de crédito/débito é recusado pela operadora.  
  1. O operador informa ao cliente sobre o erro e tenta realizar o estorno novamente.  
  2. Se a recusa persistir, o operador orienta o cliente a entrar em contato com a operadora de cartões ou sugere um outro método de estorno (por exemplo, devolução em dinheiro).

* **E2**: Falha no estorno via Pix.  
  1. O operador do caixa informa ao cliente que o estorno via Pix falhou.  
  2. O sistema tenta reenviar a solicitação de estorno.  
  3. Se a falha continuar, o operador orienta o cliente sobre outros métodos de devolução do valor.

* **E3**: O sistema falha ao cancelar a venda.  
  1. O operador do caixa reinicia o processo de cancelamento.  
  2. Se o problema persistir, o operador deve reportar a falha ao suporte técnico e informar o cliente sobre o ocorrido.

* **E4**: O sistema não encontra a transação de venda para cancelar.  
  1. O operador do caixa verifica manualmente o registro da venda no sistema.  
  2. Se o erro persistir, o operador reporta o problema ao suporte técnico e informa o cliente.  
  3. O cliente é orientado a esperar até que o problema seja resolvido ou a buscar uma solução alternativa (por exemplo, cancelar a venda manualmente).

---

## UC03: Devolver Produto

### Ator(es):
* Cliente
* Operador do caixa

### Interessado(s) e interesse(s):
* **Cliente**: Devolver um ou mais produtos adquiridos que não atendem às suas expectativas ou que apresentam defeito.  
* **Operador do caixa**: Registrar a devolução de produtos no sistema e realizar o estorno ou troca.

### Pré-condições:
* A venda original deve estar registrada no sistema.
* O cliente deve apresentar o comprovante de compra, conforme as políticas da loja.

### Pós-condições:
* O produto é devolvido ao estoque (se aplicável).
* O cliente é ressarcido ou recebe um novo produto em troca.

### Questões em aberto:
* Existe um prazo máximo para devolução de produtos?
* Quais produtos não são passíveis de devolução (por exemplo, produtos perecíveis ou com embalagem aberta)?

### Fluxo Principal:

1. O cliente solicita a devolução de um ou mais produtos no caixa, apresentando o comprovante de compra.
2. [IN] O operador do caixa acessa o sistema e localiza a venda original.
3. [OUT] O sistema exibe os detalhes da venda e os itens que podem ser devolvidos.
4. [IN] O operador do caixa seleciona o(s) item(ns) a ser(em) devolvido(s).
5. [OUT] O sistema registra a devolução e ajusta o estoque.
6. [IN] O operador do caixa pergunta ao cliente se deseja um reembolso ou troca.
   6.1. O cliente opta por reembolso.  
   6.2. O cliente opta por trocar o produto.
7. [OUT] O sistema processa o reembolso ou a troca.

### Variantes:

**6.1 Reembolso**  
6.1.1. O operador do caixa inicia o processo de reembolso no sistema.  
6.1.2. O sistema verifica a forma de pagamento original.  
6.1.3. Se o pagamento original foi em cartão de crédito ou débito, o sistema inicia o estorno.  
6.1.4. Se o pagamento original foi em dinheiro, o operador devolve o valor em espécie.  
6.1.5. O sistema registra a devolução e o estorno.

**6.2 Troca de produto**  
6.2.1. O cliente escolhe um novo produto em substituição ao devolvido.  
6.2.2. O operador do caixa registra a troca no sistema.  
6.2.3. O sistema ajusta o estoque, removendo o produto devolvido e registrando o novo produto.  
6.2.4. Se houver diferença de valor, o cliente paga ou recebe a diferença.  
6.2.5. O sistema finaliza o processo de troca e emite um novo comprovante de compra.

### Exceções:

* **E1**: O cliente não apresenta o comprovante de compra.  
  1. O operador do caixa verifica no sistema se há registro da venda com base em outras informações (ex.: CPF, data da compra).  
  2. Se a venda não puder ser localizada, o operador informa ao cliente que a devolução não pode ser processada sem o comprovante.

* **E2**: O produto devolvido está fora do prazo de devolução estabelecido pela loja.  
  1. O operador informa ao cliente que o prazo para devolução expirou e sugere outras soluções (ex.: troca por garantia ou reparo).

* **E3**: O sistema falha ao processar o estorno.  
  1. O operador tenta reenviar a solicitação de estorno.  
  2. Se o problema persistir, o operador orienta o cliente sobre alternativas para receber o valor da devolução (ex.: devolução manual ou voucher de crédito na loja).

* **E4**: O produto devolvido está danificado ou apresenta sinais de uso que impedem a devolução.  
  1. O operador do caixa informa ao cliente que o produto não pode ser devolvido devido ao seu estado.  
  2. O cliente é orientado a buscar uma solução junto ao fabricante ou ao suporte técnico.

---

## UC04: Consultar Histórico de Vendas

### Ator(es):
* Operador do caixa
* Gerente da loja

### Interessado(s) e interesse(s):
* **Operador do caixa**: Consultar vendas realizadas para corrigir possíveis erros ou validar informações.
* **Gerente da loja**: Verificar o desempenho de vendas e gerar relatórios para análise.

### Pré-condições:
* O sistema de vendas deve estar funcionando e com acesso aos dados das transações anteriores.

### Pós-condições:
* O histórico de vendas é exibido ao usuário.
* Relatórios podem ser gerados e exportados (se necessário).

### Questões em aberto:
* O sistema permite exportar os dados em diferentes formatos (PDF, CSV, etc.)?
* Existem filtros avançados para a pesquisa (ex.: por data, valor, operador)?

### Fluxo Principal:

1. O operador do caixa ou gerente acessa a opção de consultar o histórico de vendas no sistema.
2. [IN] O usuário seleciona o período de tempo ou critérios de busca (por exemplo, vendas por operador ou valor mínimo).
3. [OUT] O sistema exibe a lista de vendas realizadas no período solicitado.
4. [IN] O usuário seleciona uma venda específica para visualizar detalhes.
5. [OUT] O sistema exibe as informações detalhadas da venda, incluindo os produtos, valores e forma de pagamento.
6. [IN] O usuário pode optar por gerar um relatório do histórico ou exportá-lo para outro formato.

### Variantes:

**6.1 Exportação de relatório**  
6.1.1. O usuário escolhe a opção de exportar o relatório.  
6.1.2. O sistema oferece opções de formato (PDF, CSV, etc.).  
6.1.3. O usuário seleciona o formato desejado e confirma a exportação.  
6.1.4. O sistema gera o relatório e o disponibiliza para download ou impressão.

### Exceções:

* **E1**: O sistema não encontra vendas para o período especificado.  
  1. O operador ou gerente verifica se os filtros de pesquisa estão corretos.  
  2. Se não houver erro nos filtros, o sistema informa que não há registros para o período.