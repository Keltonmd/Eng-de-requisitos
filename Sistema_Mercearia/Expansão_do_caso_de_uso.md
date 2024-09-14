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
* **E2**: Falha ao gerar o relatório.  
  1. O sistema informa o erro ao usuário e tenta gerar o relatório novamente.  
  2. Se a falha persistir, o operador ou gerente é orientado a contatar o suporte técnico.
* **E3**: O formato de exportação selecionado não é suportado.  
  1. O sistema exibe uma mensagem de erro ao usuário.  
  2. O usuário escolhe outro formato de exportação (por exemplo, de CSV para PDF).

---

## UC05: Gerenciar Estoque

### Ator(es):
* Operador de estoque
* Gerente da loja

### Interessado(s) e interesse(s):
* **Operador de estoque**: Monitorar a quantidade de produtos disponíveis e realizar ajustes, como adicionar novos itens ou remover itens obsoletos.
* **Gerente da loja**: Garantir que o estoque esteja bem organizado e atualizado, permitindo a reposição eficiente e a gestão adequada de produtos.

### Pré-condições:
* O sistema de gerenciamento de estoque deve estar disponível e acessível.
* O operador deve ter permissões adequadas para modificar o estoque.

### Pós-condições:
* O estoque é atualizado conforme as ações realizadas (adição, remoção ou ajuste de quantidades).
* Relatórios de estoque podem ser gerados para análise.

### Questões em aberto:
* Existe uma função de aviso para alertar quando certos produtos atingem níveis mínimos de estoque?
* O sistema permite importação de dados de inventário em massa?

### Fluxo Principal:

1. O operador de estoque acessa a funcionalidade de gerenciamento de estoque no sistema.
2. [IN] O operador seleciona a opção de adicionar, remover ou ajustar a quantidade de um produto específico.
3. [OUT] O sistema exibe uma lista de produtos cadastrados e suas respectivas quantidades.
4. [IN] O operador busca o produto desejado e seleciona a ação necessária (adição, remoção ou ajuste de quantidade).
5. [OUT] O sistema registra a ação e atualiza o inventário com as novas informações.
6. [IN] O operador confirma a operação e o sistema finaliza a atualização do estoque.

### Variantes:

**6.1 Adição de novo produto**  
6.1.1. O operador seleciona a opção de adicionar um novo produto ao sistema.  
6.1.2. O sistema solicita informações sobre o produto (nome, código de barras, preço, categoria, etc.).  
6.1.3. O operador insere as informações necessárias.  
6.1.4. O sistema adiciona o novo produto ao inventário.

**6.2 Remoção de produto obsoleto**  
6.2.1. O operador seleciona a opção de remover um produto do sistema.  
6.2.2. O sistema solicita a confirmação da remoção.  
6.2.3. O operador confirma a remoção, e o produto é excluído do inventário.

**6.3 Ajuste de quantidade**  
6.3.1. O operador acessa a opção de ajustar a quantidade de um produto no estoque.  
6.3.2. O operador insere o novo valor de quantidade.  
6.3.3. O sistema atualiza o inventário com a nova quantidade do produto.

### Exceções:

* **E1**: O sistema falha ao atualizar o estoque.  
  1. O operador tenta realizar a operação novamente.  
  2. Se a falha persistir, o operador informa ao gerente e ao suporte técnico.

* **E2**: Produto não encontrado no sistema.  
  1. O operador verifica se o produto está cadastrado corretamente.  
  2. Caso não esteja, o operador deve registrar o produto antes de realizar a ação desejada.

* **E3**: Quantidade inserida é inválida (ex.: valor negativo).  
  1. O sistema exibe uma mensagem de erro informando que a quantidade inserida não é válida.  
  2. O operador deve corrigir o valor inserido e tentar novamente.

---

## UC06: Aplicar Desconto

### Ator(es):
* Operador do caixa

### Interessado(s) e interesse(s):
* **Cliente**: Obter desconto no valor total da compra (por promoções ou outros critérios definidos pela loja).
* **Operador do caixa**: Aplicar corretamente os descontos de acordo com as políticas da loja.

### Pré-condições:
* A compra deve estar em andamento no sistema, com todos os produtos registrados.
* O operador do caixa deve ter permissão para aplicar descontos.

### Pós-condições:
* O valor total da compra é ajustado conforme o desconto aplicado.
* O desconto é registrado no sistema para fins de auditoria.

### Questões em aberto:
* Quais são os limites de desconto que o operador pode aplicar?  
* O desconto é percentual ou valor fixo?

### Fluxo Principal:

1. O cliente solicita um desconto ao operador do caixa.
2. [IN] O operador acessa a opção de aplicar desconto no sistema de vendas.
3. [OUT] O sistema exibe as opções de desconto (por exemplo, desconto em percentual ou valor fixo).
4. [IN] O operador escolhe a opção adequada e insere o valor ou percentual do desconto.
5. [OUT] O sistema calcula o novo valor total da compra, considerando o desconto.
6. [IN] O operador confirma o desconto aplicado.
7. [OUT] O sistema registra o desconto no histórico da venda e exibe o valor final ao cliente.

### Variantes:

**6.1 Desconto percentual**  
6.1.1. O operador seleciona a opção de aplicar um desconto percentual.  
6.1.2. O sistema solicita o percentual a ser aplicado.  
6.1.3. O operador insere o percentual, e o sistema recalcula o valor total da compra.

**6.2 Desconto em valor fixo**  
6.2.1. O operador seleciona a opção de aplicar um desconto em valor fixo.  
6.2.2. O sistema solicita o valor do desconto a ser aplicado.  
6.2.3. O operador insere o valor, e o sistema ajusta o valor total da compra.

### Exceções:

* **E1**: O sistema não aceita o desconto inserido (ex.: valor fora dos limites permitidos).  
  1. O sistema informa ao operador que o desconto não é válido.  
  2. O operador ajusta o valor ou percentual conforme as políticas da loja e tenta novamente.

* **E2**: O sistema falha ao calcular o valor total após aplicar o desconto.  
  1. O operador do caixa tenta recalcular o valor.  
  2. Se o erro persistir, o operador deve reportar o problema ao suporte técnico e continuar a venda sem o desconto até que o problema seja resolvido.

* **E3**: O cliente não aceita o valor final com desconto aplicado.  
  1. O operador pode oferecer outra solução ou reverter o desconto, se aplicável.

## UC07: Gerar Relatório de Vendas

### Ator(es):
* Gerente da loja
* Operador do caixa

### Interessado(s) e interesse(s):
* **Gerente da loja**: Acompanhar o desempenho de vendas, identificar tendências e tomar decisões estratégicas com base nos dados gerados.
* **Operador do caixa**: Facilitar a geração de relatórios operacionais para auditorias ou análises diárias.

### Pré-condições:
* O sistema de vendas deve estar funcionando corretamente e possuir acesso aos dados de transações.
* O usuário deve ter permissão para acessar e gerar relatórios.

### Pós-condições:
* O relatório é gerado com sucesso e pode ser exportado, impresso ou salvo para futuras análises.

### Questões em aberto:
* Quais tipos de relatórios o sistema permite gerar? (ex.: vendas diárias, mensais, por categoria de produto)
* O sistema gera gráficos e estatísticas ou apenas dados brutos?

### Fluxo Principal:

1. O gerente ou operador acessa a funcionalidade de relatórios no sistema.
2. [IN] O usuário seleciona o tipo de relatório desejado (ex.: relatório diário de vendas, relatório de produtos mais vendidos).
3. [OUT] O sistema solicita os parâmetros de geração do relatório (ex.: período, filtro por categoria ou operador).
4. [IN] O usuário insere os parâmetros e confirma a geração do relatório.
5. [OUT] O sistema processa os dados e gera o relatório solicitado.
6. [OUT] O relatório é exibido na tela para visualização.
7. [IN] O usuário pode optar por exportar o relatório ou imprimi-lo.

### Variantes:

**6.1 Exportação de relatório**  
6.1.1. O usuário escolhe a opção de exportar o relatório.  
6.1.2. O sistema oferece opções de formato (ex.: PDF, CSV, Excel).  
6.1.3. O usuário seleciona o formato e confirma a exportação.  
6.1.4. O sistema gera o arquivo e disponibiliza para download.

**6.2 Impressão de relatório**  
6.2.1. O usuário seleciona a opção de imprimir o relatório.  
6.2.2. O sistema prepara o relatório para impressão.  
6.2.3. O relatório é enviado para a impressora configurada.

### Exceções:

* **E1**: Falha ao gerar o relatório.  
  1. O sistema exibe uma mensagem de erro ao usuário e sugere tentar novamente.  
  2. Se a falha persistir, o usuário deve contatar o suporte técnico.

* **E2**: Relatório gerado sem dados.  
  1. O sistema informa ao usuário que não há dados para o período ou parâmetros inseridos.  
  2. O usuário pode modificar os parâmetros e tentar gerar o relatório novamente.

* **E3**: Falha ao exportar o relatório.  
  1. O sistema exibe uma mensagem de erro informando o problema ao usuário.  
  2. O usuário pode tentar outro formato de exportação ou reiniciar o processo.

---

## UC08: Repor Estoque

### Ator(es):
* Operador de estoque
* Gerente da loja
* Fornecedor (externo ao sistema)

### Interessado(s) e interesse(s):
* **Operador de estoque**: Garantir que os produtos estejam disponíveis para venda, monitorando os níveis de estoque e iniciando a reposição quando necessário.
* **Gerente da loja**: Coordenar o processo de reposição de estoque, analisando as demandas e evitando faltas ou excessos de produtos.
* **Fornecedor**: Receber e processar os pedidos de reposição, garantindo o envio de mercadorias conforme acordado.

### Pré-condições:
* O sistema de gerenciamento de estoque deve estar funcional e atualizado com os níveis atuais de produtos.
* O operador de estoque ou gerente deve ter permissão para realizar pedidos de reposição.

### Pós-condições:
* O pedido de reposição é registrado no sistema, e o estoque é atualizado após o recebimento das mercadorias.
* O sistema registra o pedido e o status da reposição.

### Questões em aberto:
* O sistema permite a integração com fornecedores para pedidos automáticos?
* Quais notificações o sistema gera quando o nível de estoque atinge o mínimo?

### Fluxo Principal:

1. O operador de estoque ou gerente acessa a funcionalidade de reposição no sistema.
2. [IN] O usuário consulta os produtos cujo estoque está abaixo do mínimo permitido.
3. [OUT] O sistema exibe a lista de produtos que necessitam de reposição.
4. [IN] O operador ou gerente seleciona os produtos a serem repostos.
5. [OUT] O sistema calcula a quantidade necessária com base nos parâmetros de estoque mínimo e máximo.
6. [IN] O operador confirma o pedido de reposição.
7. [OUT] O sistema registra o pedido e o envia ao fornecedor (se integrado).
8. [OUT] O sistema atualiza o status do pedido, aguardando o recebimento da mercadoria.

### Variantes:

**6.1 Reposição manual**  
6.1.1. O operador seleciona a opção de reposição manual, onde define a quantidade de reposição sem base nos níveis calculados pelo sistema.  
6.1.2. O sistema atualiza o pedido conforme a quantidade definida manualmente.  
6.1.3. O pedido é registrado no sistema e enviado ao fornecedor.

**6.2 Reposição automática**  
6.2.1. O sistema identifica automaticamente os produtos abaixo do nível mínimo e sugere o pedido de reposição.  
6.2.2. O operador revisa o pedido sugerido e confirma.  
6.2.3. O sistema processa automaticamente o pedido com o fornecedor.

### Exceções:

* **E1**: Produto não disponível no fornecedor.  
  1. O sistema informa ao operador que o fornecedor não possui o produto em estoque.  
  2. O operador deve buscar outra opção de fornecedor ou esperar a reposição do fornecedor original.

* **E2**: Falha na comunicação com o fornecedor.  
  1. O sistema exibe uma mensagem de erro informando a falha no envio do pedido.  
  2. O operador tenta reenviar o pedido ou contata o fornecedor diretamente.

* **E3**: Pedido de reposição excede o limite máximo de estoque.  
  1. O sistema informa que a quantidade solicitada excede a capacidade de estoque da loja.  
  2. O operador ajusta o pedido para atender aos limites de estoque.

---

## UC09: Registrar Cliente

### Ator(es):
* Operador do caixa
* Cliente

### Interessado(s) e interesse(s):
* **Cliente**: Ser registrado no sistema para obter benefícios, como participação em programas de fidelidade, promoções e histórico de compras.
* **Operador do caixa**: Registrar as informações do cliente de forma rápida e correta, garantindo que ele receba os benefícios oferecidos pela loja.

### Pré-condições:
* O sistema de registro de clientes deve estar disponível e funcional.
* O operador deve ter acesso à funcionalidade de cadastro de clientes.

### Pós-condições:
* O cliente é registrado no sistema com todos os seus dados pessoais e preferências.
* O cliente recebe um identificador exclusivo para futuras compras.

### Questões em aberto:
* Quais dados são obrigatórios para o registro? (ex.: nome, CPF, e-mail)
* O sistema permite associar o cliente a programas de fidelidade ou promoções automaticamente?

### Fluxo Principal:

1. O cliente solicita o registro no sistema de clientes.
2. [IN] O operador acessa a funcionalidade de registro de clientes no sistema.
3. [OUT] O sistema solicita as informações do cliente (ex.: nome, CPF, e-mail, telefone).
4. [IN] O operador insere os dados do cliente.
5. [OUT] O sistema valida as informações inseridas.
6. [OUT] O cliente é registrado e recebe um identificador único (cartão fidelidade, QR code, etc.).
7. [IN] O operador finaliza o processo de registro, e o sistema confirma a inclusão do cliente.

### Variantes:

**6.1 Registro com programa de fidelidade**  
6.1.1. O operador associa o cliente a um programa de fidelidade durante o registro.  
6.1.2. O sistema atualiza o cadastro do cliente com os benefícios do programa.  
6.1.3. O cliente começa a acumular pontos ou receber descontos em compras futuras.

### Exceções:

* **E1**: Falha ao validar os dados do cliente (ex.: CPF inválido).  
  1. O sistema informa o erro ao operador, que corrige os dados inseridos.  
  2. Se o erro persistir, o operador orienta o cliente a verificar seus dados e tenta novamente.

* **E2**: Cliente já registrado no sistema.  
  1. O sistema informa que o cliente já possui um registro ativo.  
  2. O operador verifica os dados e, se necessário, atualiza o cadastro existente.
* **E3**: Falha no sistema durante o registro.  
  1. O operador informa ao cliente sobre o erro e tenta novamente realizar o registro.  
  2. Se a falha persistir, o operador orienta o cliente a retornar mais tarde e reporta o problema ao suporte técnico.

---

## UC10: Emitir Nota Fiscal

### Ator(es):
* Operador do caixa
* Cliente

### Interessado(s) e interesse(s):
* **Cliente**: Receber a nota fiscal de sua compra para fins de garantia, troca ou dedução de impostos.
* **Operador do caixa**: Emitir corretamente a nota fiscal, garantindo que os dados da compra e do cliente estejam completos e corretos.

### Pré-condições:
* A compra deve ter sido finalizada e registrada no sistema.
* O sistema de emissão de nota fiscal deve estar integrado ao sistema de vendas.

### Pós-condições:
* A nota fiscal é gerada e entregue ao cliente.
* O sistema registra a emissão da nota fiscal para fins contábeis e fiscais.

### Questões em aberto:
* O sistema permite a emissão de notas fiscais eletrônicas (NF-e)?
* Existe a possibilidade de enviar a nota fiscal por e-mail ou apenas imprimi-la?

### Fluxo Principal:

1. Após a finalização da compra, o cliente solicita a emissão da nota fiscal.
2. [IN] O operador do caixa acessa a funcionalidade de emissão de nota fiscal no sistema.
3. [OUT] O sistema solicita os dados do cliente (ex.: CPF, CNPJ, endereço).
4. [IN] O operador insere ou confirma os dados do cliente no sistema.
5. [OUT] O sistema gera a nota fiscal com base nas informações da compra e do cliente.
6. [OUT] O sistema exibe a nota fiscal para revisão e confirmação.
7. [IN] O operador confirma a emissão da nota fiscal.
8. [OUT] A nota fiscal é emitida e entregue ao cliente, seja impressa ou enviada por e-mail.

### Variantes:

**6.1 Envio de nota fiscal por e-mail**  
6.1.1. O operador pergunta ao cliente se deseja receber a nota fiscal por e-mail.  
6.1.2. O cliente fornece o e-mail, e o operador insere o endereço no sistema.  
6.1.3. O sistema gera a nota fiscal eletrônica (NF-e) e a envia automaticamente para o e-mail fornecido.

**6.2 Impressão da nota fiscal**  
6.2.1. O operador seleciona a opção de imprimir a nota fiscal.  
6.2.2. O sistema prepara a nota fiscal para impressão.  
6.2.3. A nota fiscal é enviada para a impressora, e o operador a entrega ao cliente.

### Exceções:

* **E1**: Falha ao gerar a nota fiscal.  
  1. O sistema informa ao operador sobre a falha e tenta gerar a nota fiscal novamente.  
  2. Se a falha persistir, o operador orienta o cliente a contatar o suporte técnico da loja ou emitir a nota fiscal posteriormente.

* **E2**: Dados do cliente incorretos ou incompletos.  
  1. O sistema exibe um aviso de erro e solicita a correção dos dados.  
  2. O operador corrige as informações e tenta emitir a nota fiscal novamente.

* **E3**: Falha ao enviar a nota fiscal por e-mail.  
  1. O sistema informa ao operador que o envio por e-mail falhou.  
  2. O operador pergunta ao cliente se deseja receber a nota fiscal impressa ou se o envio deve ser tentado novamente.
## UC11: Gerenciar Preços de Produtos

### Ator(es):
* Gerente da loja
* Operador do sistema

### Interessado(s) e interesse(s):
* **Gerente da loja**: Garantir que os preços dos produtos estejam atualizados e de acordo com as políticas da loja, promoções e fornecedores.
* **Operador do sistema**: Facilitar a inserção e atualização de preços no sistema para garantir que as operações de venda reflitam os preços corretos.

### Pré-condições:
* O sistema de gerenciamento de preços deve estar disponível e funcional.
* O usuário deve ter permissão para alterar os preços dos produtos.

### Pós-condições:
* Os preços dos produtos são atualizados no sistema e refletem-se imediatamente nas vendas.
* O sistema mantém um histórico das alterações de preços para futuras auditorias.

### Questões em aberto:
* O sistema permite agendar mudanças de preço? (ex.: para promoções futuras)
* Existe algum limite de alteração de preço em relação ao valor anterior?

### Fluxo Principal:

1. O gerente ou operador acessa a funcionalidade de gerenciamento de preços no sistema.
2. [IN] O usuário consulta a lista de produtos ou busca um produto específico.
3. [OUT] O sistema exibe o preço atual do produto selecionado.
4. [IN] O usuário insere o novo preço do produto.
5. [OUT] O sistema valida a alteração de preço conforme regras internas (ex.: limites mínimos ou máximos permitidos).
6. [OUT] O preço do produto é atualizado e refletido no sistema de vendas.
7. [IN] O usuário confirma a atualização do preço.

### Variantes:

**6.1 Alteração em lote de preços**  
6.1.1. O operador seleciona múltiplos produtos para atualização simultânea.  
6.1.2. O sistema permite a inserção de novos preços para todos os produtos selecionados.  
6.1.3. O sistema atualiza os preços em lote e confirma a operação.

**6.2 Agendamento de alteração de preços**  
6.2.1. O operador escolhe a opção de agendar uma alteração de preço para uma data futura (ex.: início de promoção).  
6.2.2. O sistema registra a alteração e ativa os novos preços automaticamente na data programada.

### Exceções:

* **E1**: Falha ao validar o novo preço.  
  1. O sistema informa ao operador que o preço inserido não atende às regras (ex.: abaixo do mínimo permitido).  
  2. O operador ajusta o preço conforme as regras estabelecidas ou solicita aprovação especial do gerente.

* **E2**: Falha na atualização de preços.  
  1. O sistema informa ao operador que houve uma falha na atualização, como problemas de conexão com o banco de dados.  
  2. O operador tenta novamente ou contata o suporte técnico.

* **E3**: Produto inexistente.  
  1. O sistema informa que o produto inserido não está cadastrado no sistema.  
  2. O operador revisa os dados do produto ou realiza o cadastro antes de atualizar o preço.

---

## UC12: Aplicar Promoções

### Ator(es):
* Gerente da loja
* Operador do sistema
* Cliente

### Interessado(s) e interesse(s):
* **Gerente da loja**: Implementar promoções para aumentar as vendas de determinados produtos, girar estoque ou atrair mais clientes.
* **Operador do sistema**: Facilitar a inserção de promoções no sistema para garantir que os clientes aproveitem os descontos oferecidos.
* **Cliente**: Obter vantagens nas compras durante o período promocional.

### Pré-condições:
* O sistema de vendas deve estar integrado com a funcionalidade de promoções.
* O usuário deve ter permissão para cadastrar promoções.

### Pós-condições:
* A promoção é aplicada aos produtos no sistema e refletida automaticamente nas vendas.
* O sistema registra as promoções aplicadas para futuras análises de desempenho.

### Questões em aberto:
* As promoções podem ser aplicadas automaticamente em determinados horários ou dias?
* O sistema permite combinações de promoções (ex.: descontos acumulativos)?

### Fluxo Principal:

1. O gerente ou operador acessa a funcionalidade de promoções no sistema.
2. [IN] O usuário seleciona os produtos ou categorias a serem incluídos na promoção.
3. [OUT] O sistema solicita os parâmetros da promoção (ex.: desconto percentual, preço fixo, datas de início e fim).
4. [IN] O operador insere as informações da promoção e confirma.
5. [OUT] O sistema valida a promoção e atualiza os preços dos produtos afetados.
6. [OUT] O sistema exibe os produtos promocionados na tela de vendas, destacando os descontos.
7. [IN] O operador finaliza o cadastro da promoção.

### Variantes:

**6.1 Promoção por tempo limitado**  
6.1.1. O operador define um período específico para a promoção (ex.: promoção válida apenas no final de semana).  
6.1.2. O sistema ativa a promoção automaticamente no período definido e desativa ao final.

**6.2 Promoção com regras especiais**  
6.2.1. O operador define regras adicionais para a promoção, como "compre 1, leve 2" ou descontos progressivos.  
6.2.2. O sistema aplica as regras automaticamente ao realizar as vendas.

### Exceções:

* **E1**: Promoção conflitante com outra ativa.  
  1. O sistema informa ao operador que a promoção inserida entra em conflito com outra já existente (ex.: produtos com descontos diferentes).  
  2. O operador ajusta a promoção ou revê as promoções ativas.

* **E2**: Falha ao aplicar a promoção.  
  1. O sistema informa ao operador que houve uma falha ao tentar aplicar a promoção nos produtos selecionados.  
  2. O operador tenta novamente ou contata o suporte técnico.

* **E3**: Produto fora da promoção.  
  1. O sistema informa que um ou mais produtos selecionados não são elegíveis para a promoção (ex.: produtos em fim de estoque).  
  2. O operador revisa os produtos ou ajusta as regras da promoção.

---

## UC13: Gerenciar Devoluções de Produtos

### Ator(es):
* Operador do caixa
* Cliente
* Gerente da loja

### Interessado(s) e interesse(s):
* **Cliente**: Devolver produtos defeituosos ou indesejados de acordo com as políticas da loja.
* **Operador do caixa**: Facilitar o processo de devolução, registrando corretamente o item devolvido e gerando o reembolso ou troca.
* **Gerente da loja**: Supervisionar o processo de devolução para garantir conformidade com as políticas internas e minimizar perdas.

### Pré-condições:
* O sistema de vendas deve estar funcional e integrado com a funcionalidade de devoluções.
* O operador deve ter permissão para registrar devoluções.

### Pós-condições:
* O produto devolvido é removido do estoque, e o cliente recebe um reembolso ou troca, conforme o caso.
* O sistema registra a devolução para controle interno e análise.

### Questões em aberto:
* O sistema permite devoluções parciais (de um ou mais itens de uma compra)?
* O sistema trata automaticamente o estorno no caso de pagamentos por cartão?

### Fluxo Principal:

1. O cliente solicita a devolução de um ou mais produtos.
2. [IN] O operador acessa a funcionalidade de devoluções no sistema.
3. [OUT] O sistema solicita os detalhes da compra original (ex.: número da nota fiscal, data da compra).
4. [IN] O operador insere as informações da compra ou escaneia o código de barras do produto.
5. [OUT] O sistema verifica os produtos elegíveis para devolução.
6. [IN] O operador seleciona o produto a ser devolvido e o motivo da devolução.
7. [OUT] O sistema atualiza o estoque e registra a devolução.
8. [IN] O operador confirma se será emitido um reembolso ou troca.
9. [OUT] O sistema emite um comprovante de devolução.

### Variantes:

**6.1 Devolução parcial**  
6.1.1. O cliente solicita a devolução de apenas um ou alguns itens da compra.  
6.1.2. O sistema permite que o operador selecione apenas os produtos devolvidos, mantendo os outros itens no histórico da venda.

**8.1 Reembolso em dinheiro**  
8.1.1. O cliente solicita o reembolso em dinheiro.  
8.1.2. O operador confirma o valor a ser devolvido.  
8.1.3. O sistema registra o reembolso e o operador entrega o valor ao cliente.

**8.2 Reembolso por cartão**  
8.2.1. O cliente solicita o estorno no cartão de crédito ou débito.  
8.2.2. O sistema comunica a operadora de cartões para efetuar o estorno.  
8.2.3. O sistema confirma o estorno e o cliente recebe o comprovante.

### Exceções:

* **E1**: Produto fora do prazo de devolução.  
  1. O sistema informa que o produto excedeu o prazo permitido para devolução.  
  2. O operador comunica o cliente sobre as políticas da loja e oferece alternativas, como troca ou reparo.
* **E2**: Falha no estorno de cartão.  
  1. O sistema informa que houve uma falha ao tentar processar o estorno.  
  2. O operador tenta novamente ou oferece outro método de reembolso ao cliente.
* **E3**: Produto não elegível para devolução.  
  1. O sistema informa que o produto não pode ser devolvido (ex.: produtos em promoção final, danificados por mau uso).  
  2. O operador informa o cliente sobre as restrições e, se aplicável, oferece alternativas como troca ou reparo.
