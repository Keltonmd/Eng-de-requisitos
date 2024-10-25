# Sistema de Gestão de Sorveteria
## Sumário
1. [VISÃO GERAL DO SISTEMA](#1-visão-geral-do-sistema)
2. [LEVANTAMENTO DE REQUISITOS](#2-levantamento-de-requisitos)

   2.1. [REQUISITOS FUNCIONAIS](#requisitos)
   
   2.2. [REQUISITOS NÃO FUNCIONAIS](#requisitos-não-funcionais)
   
   2.3. [REQUISITOS SUPLEMENTARES](#requisitos-suplementares)
3. [DETALHAMENTO DE REQUISITOS](#3-detalhamento-dos-requisitos)
4. [CASOS DE USO](#4-casos-de-uso)
5. [CASO DE USO EXPANDIDO](#5-caso-de-uso-expandido)
6. [DIAGRAMA DE SEQUÊNCiA](#6-diagrama-de-sequência)
7. [MODELO CONCEITUAL](#7-modelo-conceitual)
8. [DIAGRAMA DE COMUNICAÇÃO](#8-diagrama-de-comunicação)
9. [DIAGRAMA DE CLASSES](#9-diagrama-de-classes)



## 1. Visão Geral

## 2. LEVANTAMENTO DE REQUISITOS

## Requisitos
1. Gerenciar Estoque
2. Gerenciar Funcionarios
3. Gestão de Fornecedores
4. Gerenciar Caixa

### Requisitos Não Funcionais
1. O sistema deve registrar a entrada e saida de estoque.

2. O sistema deve fornecer aviso de estoque baixo automaticamente quando um produto atingir o limite mínimo configurado.

3. O sistema deve emitir avisos sobre a validade do estoque, notificando os responsáveis com pelo menos 7 dias de antecedência da data de vencimento.

4. O sistema deve cadastrar os funcionários por meio de níveis hierárquicos, definindo permissões adequadas de acordo com seus cargos na empresa.

5. Os funcionários devem se cadastrar no sistema utilizando CPF e senha, garantindo a identificação única e segura.

6. O sistema deve controlar as funções de cada funcionário e permitir acessos restritos conforme seu nível hierárquico e responsabilidades.

7. O sistema deve armazenar os seguintes dados dos fornecedores: Nome, CNPJ, Telefone, Endereço e formas de pagamento aceitas.

8. O sistema deve manter um histórico completo de compras realizadas com cada fornecedor, incluindo datas, produtos adquiridos e valores pagos.

9. O sistema deve permitir a abertura e fechamento do caixa, registrando o valor inicial e final, com histórico das transações realizadas.

10. O sistema deve suportar várias formas de pagamento, como dinheiro, cartão e pagamentos eletrônicos.

11. O sistema deve gerenciar automaticamente o troco, calculando o valor a ser devolvido ao cliente com base no pagamento realizado.

12. A abertura e fechamento de caixa deve ser realizada apenas por funcionários autorizados, de acordo com o nível de seu cargo na hierarquia.

13. O sistema deve permitir o estorno e cancelamento de produtos ou vendas, mediante autorização de um responsável.

14. O sistema deve estar totalmente integrado ao estoque, atualizando automaticamente as quantidades de produtos após cada venda.

15. O sistema deve gerar relatórios financeiros detalhados após o fechamento do caixa, mostrando total de vendas, forma de pagamento, e divergências de valores (se houver).

### Requisitos Suplementares
1. O sistema deve operar via plataforma desktop.
2. O sistema deve utilizar o banco de dados postgres.
3. O sistema deve utilizar a linguagem Java.
4. O sistema deve utilzar o Spring Security para realizar a segurança de acesso.
5. O sistema deve gerar relatorios por meio da biblioteca JasperReports.

## 3. Detalhamento dos Requisitos
| **RF1. Gerenciar Estoque** |
|:---|
| **Descrição:**<br>Este requisito estabelece a necessidade de um sistema abrangente para o gerenciamento de estoque da sorveteria, que permita o controle eficiente de entradas e saídas de produtos. O sistema deve garantir a precisão nas informações de estoque, possibilitando um acompanhamento em tempo real da quantidade disponível. Além disso, deve incluir funcionalidades para monitorar a validade dos produtos e emitir alertas automáticos quando os níveis de estoque atingirem limites críticos, evitando desperdícios e assegurando a disponibilidade de produtos para os clientes.|
| **Fontes:**<br>Departamento responsavel pelo estoque e feedback interno dos funcionarios|
| **Usuários:**<br>Funcionarios do estoque, Gerente ou Admnistrador do setor de estoque e Administradores do Sistema|
| **Informações de entrada:**<br>Dados do Produto: Informações detalhadas sobre os produtos, incluindo nome, descrição, unidade de medida, quantidade inicial e data de validade.<br>Registro de Movimentações: Dados referentes a cada movimentação de estoque, como tipo de operação, quantidade movimentada, data da operação e identificação do usuário responsável pela ação. | 
| **Informações de saída:**<br>Relatórios de Estoque: Documentos gerados que fornecem uma visão geral do estoque, incluindo quantidades disponíveis, produtos com validade próxima e um histórico detalhado de todas as movimentações.<br>Alertas de Estoque Crítico: Notificações automáticas que informam os usuários quando os níveis de estoque de produtos específicos estão abaixo do mínimo estabelecido, permitindo ações rápidas de reposição.<br>Avisos de Validade: Comunicações sobre produtos que estão próximos do vencimento, sugerindo ações como promoções ou descarte, a fim de minimizar perdas. |
| **Requisitos não funcionais:**<br>RNF 1: O sistema deve registrar a entrada e saida de estoque.<br><br>RNF 2: O sistema deve fornecer aviso de estoque baixo automaticamente quando um produto atingir o limite mínimo configurado<br><br>RNF 3: O sistema deve emitir avisos sobre a validade do estoque, notificando os responsáveis com pelo menos 7 dias de antecedência da data de vencimento.|

---

| **RF2. Gerenciar Funcionarios** |
|:---|
| **Descrição:**<br>Este requisito especifica a implementação de um sistema para gerenciar a equipe da sorveteria, permitindo o cadastro, controle e monitoramento dos funcionários. O sistema deve oferecer a capacidade de definir diferentes níveis de acesso e hierarquias, assegurando que as funções e responsabilidades sejam claramente definidas. Além disso, deve incluir funcionalidades para registro de dados pessoais, autenticação de usuários e controle de permissões, garantindo a segurança e integridade das informações.|
| **Fontes:**<br>Administradores da empresa e RH|
| **Usuários:**<br>Administradores do Sistema, Funcionários e Gerentes de Recursos Humanos|
| **Informações de entrada:**<br>Dados do Funcionário: Informações pessoais, incluindo nome, CPF, cargo, data de contratação e informações de contato.<br>Credenciais de Acesso: Cadastro de login e senha para cada funcionário, além de dados relacionados ao nível de acesso. | 
| **Informações de saída:**<br>Notificações de Acesso: Mensagens informando sobre tentativas de login, alterações nas permissões e atualizações nos dados dos funcionários.<br>Histórico de Atividades: Registros das atividades realizadas por cada funcionário dentro do sistema, permitindo auditorias e avaliações de desempenho. |
| **Requisitos não funcionais:**<br>RNF 4: O sistema deve cadastrar os funcionários por meio de níveis hierárquicos, definindo permissões adequadas de acordo com seus cargos na empresa.<br><br>RNF 5: Os funcionários devem se cadastrar no sistema utilizando CPF e senha, garantindo a identificação única e segura.<br><br>RNF 6: O sistema deve controlar as funções de cada funcionário e permitir acessos restritos conforme seu nível hierárquico e responsabilidades.|

---

| **RF3. Gestão de Fornecedores** |
|:---|
| **Descrição:**<br>Este requisito define a necessidade de um sistema para gerenciar as informações e interações com os fornecedores da sorveteria. O sistema deve permitir o cadastro detalhado de fornecedores, incluindo dados como nome, CNPJ, telefone, endereço e formas de pagamento aceitas. Além disso, deve possibilitar o acompanhamento histórico de compras realizadas, facilitando a avaliação de desempenho e a tomada de decisões estratégicas relacionadas ao abastecimento.|
| **Fontes:**<br>Setor financeiro e Gerente de compras|
| **Usuários:**<br>Gerente de Compras, Gerente Financeiro, funcionarios de estoque, gerente de estoque e admnistradores do sitema|
| **Informações de entrada:**<br>Dados do Fornecedor: Informações detalhadas, incluindo nome, CNPJ, telefone, endereço e formas de pagamento aceitas.<br>Histórico de Compras: Registros de todas as transações realizadas com cada fornecedor, incluindo data, produtos adquiridos, quantidades e valores. | 
| **Informações de saída:**<br>Relatórios de Fornecedores: Documentos que fornecem uma visão geral dos fornecedores cadastrados, incluindo informações de contato e avaliação de desempenho com base no histórico de compras.<br>Alertas de Reabastecimento: Notificações que informam sobre a necessidade de entrar em contato com fornecedores para reposição de produtos, com base nas quantidades em estoque. |
| **Requisitos não funcionais:**<br>RNF 7: O sistema deve armazenar os seguintes dados dos fornecedores: Nome, CNPJ, Telefone, Endereço e formas de pagamento aceitas.<br><br>RNF 8: O sistema deve manter um histórico completo de compras realizadas com cada fornecedor, incluindo datas, produtos adquiridos e valores pagos.|

---

| **RF4. Gerenciar Caixa** |
|:---|
| **Descrição:**<br>Este requisito estabelece a necessidade de um sistema para gerenciar as operações financeiras da sorveteria, incluindo a abertura e fechamento do caixa, registro de vendas e controle de diferentes formas de pagamento. O sistema deve permitir o acompanhamento preciso das entradas e saídas de dinheiro, garantindo a integridade financeira e facilitando a gestão de trocos. Além disso, deve oferecer funcionalidades para estorno e cancelamento de vendas, além da geração de relatórios financeiros após o fechamento do caixa.|
| **Fontes:**<br>Setor financeiro, Administradores da empresa e Setor de Vendas|
| **Usuários:**<br>Gerentes de Caixa, Funcionarios de vendas e adminstradores do sistema|
| **Informações de entrada:**<br>Dados de Venda: Informações sobre cada transação realizada, incluindo produtos vendidos, quantidades, valores e forma de pagamento.<br> Movimentações de Caixa: Registros de todas as entradas e saídas de dinheiro, como vendas, reembolsos e despesas operacionais. | 
| **Informações de saída:**<br>Relatórios Financeiros: Documentos gerados que detalham o desempenho do caixa, incluindo total de vendas, entradas e saídas, e saldo final.<br>Alertas de Troco: Notificações que informam os usuários sobre a necessidade de gerenciar o troco disponível, garantindo que a operação não seja afetada.<br>Registro de Estornos: Documentação de todas as transações de estorno e cancelamento, permitindo auditorias e controle de perdas. |
| **Requisitos não funcionais:**<br>RNF 9: O sistema deve permitir a abertura e fechamento do caixa, registrando o valor inicial e final, com histórico das transações realizadas.<br><br>RNF 10: O sistema deve suportar várias formas de pagamento, como dinheiro, cartão e pagamentos eletrônicos.<br><br>RNF 11: O sistema deve gerenciar automaticamente o troco, calculando o valor a ser devolvido ao cliente com base no pagamento realizado.<br><br>RNF 12: A abertura e fechamento de caixa deve ser realizada apenas por funcionários autorizados, de acordo com o nível de seu cargo na hierarquia.<br><br>RNF 13: O sistema deve permitir o estorno e cancelamento de produtos ou vendas, mediante autorização de um responsável.|

---

## 4. Casos de Uso

### UC01.

#### Nome do Caso de Uso: Gerenciar Funcionários

#### Atores
- **RH**: Administradores do Sistema, Funcionários autorizados e Gerentes de Recursos Humanos.

#### Descrição
Este caso de uso permite que o funcionário autorizado do sistema adicione, edite, visualize e remova informações sobre os funcionários da loja.

#### Pré-condições
- O RH deve estar autenticado no sistema.
- O RH deve ter permissões adequadas para realizar operações de gerenciamento de funcionários.

#### Pós-condições
- As informações do funcionário são atualizadas no sistema.
- O funcionário é adicionado ou removido do sistema, conforme a operação realizada.

#### Fluxo Principal
1. **Adicionar Funcionário**
   - [IN] O gerente seleciona a opção "Adicionar Funcionário".
   - [OUT] O sistema exibe um formulário para cadastro de funcionário.
   - [IN] O gerente preenche as informações necessárias (nome, cargo, telefone, e-mail).
   - [IN] O gerente clica em "Salvar".
   - [OUT] O sistema valida as informações e adiciona o funcionário à lista.
   - [OUT] O sistema exibe uma mensagem de confirmação.

2. **Editar Funcionário**
   - [IN] O gerente seleciona a opção "Gerenciar Funcionários".
   - [OUT] O sistema exibe uma lista de funcionários cadastrados.
   - [IN] O gerente escolhe um funcionário da lista e clica em "Editar".
   - [OUT] O sistema exibe um formulário com as informações do funcionário.
   - [IN] O gerente modifica as informações necessárias e clica em "Salvar".
   - [OUT] O sistema valida as informações e atualiza os dados do funcionário.
   - [OUT] O sistema exibe uma mensagem de confirmação.

3. **Visualizar Funcionário**
   - [IN] O gerente seleciona a opção "Gerenciar Funcionários".
   - [OUT] O sistema exibe uma lista de funcionários cadastrados.
   - [IN] O gerente escolhe um funcionário da lista e clica em "Visualizar".
   - [OUT] O sistema exibe as informações detalhadas do funcionário.

4. **Remover Funcionário**
   - [IN] O gerente seleciona a opção "Gerenciar Funcionários".
   - [OUT] O sistema exibe uma lista de funcionários cadastrados.
   - [IN] O gerente escolhe um funcionário da lista e clica em "Remover".
   - [OUT] O sistema solicita confirmação da remoção.
   - [IN] O gerente confirma a remoção.
   - [OUT] O sistema remove o funcionário da lista.
   - [OUT] O sistema exibe uma mensagem de confirmação.

#### Fluxo Alternativo
- **Erro ao Adicionar Funcionário**
  - [OUT] Se o gerente não preencher todos os campos obrigatórios, o sistema exibe uma mensagem de erro e solicita correção.

- **Erro ao Remover Funcionário**
  - [OUT] Se houver um erro durante a remoção (ex: funcionário com registros pendentes), o sistema exibe uma mensagem de erro informando o motivo.

#### Requisitos Não Funcionais
- RNF 4: O sistema deve cadastrar os funcionários por meio de níveis hierárquicos, definindo permissões adequadas de acordo com seus cargos na empresa.
- RNF 5: Os funcionários devem se cadastrar no sistema utilizando CPF e senha, garantindo a identificação única e segura.
- RNF 6: O sistema deve controlar as funções de cada funcionário e permitir acessos restritos conforme seu nível hierárquico e responsabilidades.

---

### UC02
#### Nome do Caso de Uso: Gerenciar Fornecedores

#### Atores
- **Funcionário Autorizado**: Gerente de Compras, Gerente Financeiro, funcionarios autoriazados do estoque, gerente do estoque e admnistradores do sitema.

#### Descrição
Este caso de uso permite que o gerente do sistema adicione, edite, visualize e remova informações sobre os fornecedores da loja de sorvetes.

#### Pré-condições
- O Funcionário Autorizado deve estar autenticado no sistema.
- O Funcionário Autorizado deve ter permissões adequadas para realizar operações de gerenciamento de fornecedores.

#### Pós-condições
- As informações do fornecedor são atualizadas no sistema.
- O fornecedor é adicionado ou removido do sistema, conforme a operação realizada.

#### Fluxo Principal
1. **Adicionar Fornecedor**
   - [IN] O gerente seleciona a opção "Adicionar Fornecedor".
   - [OUT] O sistema exibe um formulário para cadastro de fornecedor.
   - [IN] O gerente preenche as informações necessárias (nome, telefone, e-mail).
   - [IN] O gerente clica em "Salvar".
   - [OUT] O sistema valida as informações e adiciona o fornecedor à lista.
   - [OUT] O sistema exibe uma mensagem de confirmação.

2. **Editar Fornecedor**
   - [IN] O gerente seleciona a opção "Gerenciar Fornecedores".
   - [OUT] O sistema exibe uma lista de fornecedores cadastrados.
   - [IN] O gerente escolhe um fornecedor da lista e clica em "Editar".
   - [OUT] O sistema exibe um formulário com as informações do fornecedor.
   - [IN] O gerente modifica as informações necessárias e clica em "Salvar".
   - [OUT] O sistema valida as informações e atualiza os dados do fornecedor.
   - [OUT] O sistema exibe uma mensagem de confirmação.

3. **Visualizar Fornecedor**
   - [IN] O gerente seleciona a opção "Gerenciar Fornecedores".
   - [OUT] O sistema exibe uma lista de fornecedores cadastrados.
   - [IN] O gerente escolhe um fornecedor da lista e clica em "Visualizar".
   - [OUT] O sistema exibe as informações detalhadas do fornecedor.

4. **Remover Fornecedor**
   - [IN] O gerente seleciona a opção "Gerenciar Fornecedores".
   - [OUT] O sistema exibe uma lista de fornecedores cadastrados.
   - [IN] O gerente escolhe um fornecedor da lista e clica em "Remover".
   - [OUT] O sistema solicita confirmação da remoção.
   - [IN] O gerente confirma a remoção.
   - [OUT] O sistema remove o fornecedor da lista.
   - [OUT] O sistema exibe uma mensagem de confirmação.

#### Fluxo Alternativo
- **Erro ao Adicionar Fornecedor**
  - [OUT] Se o gerente não preencher todos os campos obrigatórios, o sistema exibe uma mensagem de erro e solicita correção.

- **Erro ao Remover Fornecedor**
  - [OUT] Se houver um erro durante a remoção (ex: fornecedor associado a produtos), o sistema exibe uma mensagem de erro informando o motivo.

#### Requisitos Não Funcionais
- O sistema deve ser responsivo e permitir que o gerente gerencie os fornecedores de maneira intuitiva.
- As mensagens de confirmação e erro devem ser claras e informativas.

---

### UC03 

#### Nome do Caso de Uso: Gerenciar Estoque 

#### Atores
- **Gerente**: Funcionarios autorizados do estoque, Gerente ou Admnistrador do setor de estoque e Administradores do Sistema

#### Descrição
Este caso de uso permite que o gerente do sistema adicione, edite, visualize e remova informações sobre os itens disponíveis no estoque da loja de sorvetes.

#### Pré-condições
- O gerente deve estar autenticado no sistema.
- O gerente deve ter permissões adequadas para realizar operações de gerenciamento de estoque.

#### Pós-condições
- As informações do item são atualizadas no sistema.
- O item é adicionado ou removido do estoque, conforme a operação realizada.

#### Fluxo Principal
1. **Adicionar Item ao Estoque**
   - [IN] O gerente seleciona a opção "Adicionar Item ao Estoque".
   - [OUT] O sistema exibe um formulário para cadastro de item.
   - [IN] O gerente preenche as informações necessárias (nome do produto, quantidade, preço, fornecedor).
   - [IN] O gerente clica em "Salvar".
   - [OUT] O sistema valida as informações e adiciona o item ao estoque.
   - [OUT] O sistema exibe uma mensagem de confirmação.

2. **Editar Item do Estoque**
   - [IN] O gerente seleciona a opção "Gerenciar Estoque".
   - [OUT] O sistema exibe uma lista de itens cadastrados no estoque.
   - [IN] O gerente escolhe um item da lista e clica em "Editar".
   - [OUT] O sistema exibe um formulário com as informações do item.
   - [IN] O gerente modifica as informações necessárias e clica em "Salvar".
   - [OUT] O sistema valida as informações e atualiza os dados do item.
   - [OUT] O sistema exibe uma mensagem de confirmação.

3. **Visualizar Item do Estoque**
   - [IN] O gerente seleciona a opção "Gerenciar Estoque".
   - [OUT] O sistema exibe uma lista de itens cadastrados no estoque.
   - [IN] O gerente escolhe um item da lista e clica em "Visualizar".
   - [OUT] O sistema exibe as informações detalhadas do item.

4. **Remover Item do Estoque**
   - [IN] O gerente seleciona a opção "Gerenciar Estoque".
   - [OUT] O sistema exibe uma lista de itens cadastrados no estoque.
   - [IN] O gerente escolhe um item da lista e clica em "Remover".
   - [OUT] O sistema solicita confirmação da remoção.
   - [IN] O gerente confirma a remoção.
   - [OUT] O sistema remove o item do estoque.
   - [OUT] O sistema exibe uma mensagem de confirmação.

5. **Alerta de Estoque baixo**
   -[OUT] O sistema avisa estoque baixo de um determinado produto.

6. **Gerar Relatorio**
   -[OUT] Gerar Relatorio do historico com fornecedor.

#### Fluxo Alternativo
- **Erro ao Adicionar Item**
  - [OUT] Se o gerente não preencher todos os campos obrigatórios, o sistema exibe uma mensagem de erro e solicita correção.

- **Erro ao Remover Item**
  - [OUT] Se houver um erro durante a remoção (ex: item associado a vendas pendentes), o sistema exibe uma mensagem de erro informando o motivo.

#### Requisitos Não Funcionais
- O sistema deve ser responsivo e permitir que o gerente gerencie o estoque de maneira intuitiva.
- As mensagens de confirmação e erro devem ser claras e informativas.


### Caso de uso que representa a Gerencia de Estoque, Fornecedores e Funcionarios.
![Ucestoque](Diagramas/Caso%20de%20Uso.svg)

---

### UC04

#### Nome do Caso de Uso: Gerenciar Caixa

#### Atores
**Gerente**: Usuário com permissão para realizar operações de abertura, fechamento e controle de caixa.

#### Descrição
Este caso de uso permite que o gerente do sistema gerencie as operações de caixa, incluindo a abertura e o fechamento do caixa, além de registrar entradas e saídas de dinheiro.

#### Pré-condições
- O gerente deve estar autenticado no sistema.
- O gerente deve ter permissões adequadas para realizar operações de gerenciamento de caixa.

#### Pós-condições
- O caixa é aberto ou fechado corretamente, registrando as informações necessárias.
- As entradas e saídas de dinheiro são registradas e atualizadas no sistema.

#### Fluxo Principal
1. **Abrir Caixa**
   - [IN] O gerente seleciona a opção "Abrir Caixa".
   - [OUT] O sistema exibe um formulário para registrar a abertura do caixa.
   - [IN] O gerente preenche as informações necessárias (data, valor inicial).
   - [IN] O gerente clica em "Salvar".
   - [OUT] O sistema valida as informações e registra a abertura do caixa.
   - [OUT] O sistema exibe uma mensagem de confirmação.

2. **Fechar Caixa**
   - [IN] O gerente seleciona a opção "Fechar Caixa".
   - [OUT] O sistema exibe um formulário para registrar o fechamento do caixa.
   - [IN] O gerente insere o valor total encontrado no caixa.
   - [IN] O gerente clica em "Salvar".
   - [OUT] O sistema valida as informações e registra o fechamento do caixa.
   - [OUT] O sistema exibe uma mensagem de confirmação.

3. **Registrar Entrada de Dinheiro**
   - [IN] O gerente seleciona a opção "Registrar Entrada".
   - [OUT] O sistema exibe um formulário para registrar a entrada.
   - [IN] O gerente preenche as informações necessárias (valor, descrição).
   - [IN] O gerente clica em "Salvar".
   - [OUT] O sistema valida as informações e registra a entrada no caixa.
   - [OUT] O sistema exibe uma mensagem de confirmação.

4. **Registrar Saída de Dinheiro**
   - [IN] O gerente seleciona a opção "Registrar Saída".
   - [OUT] O sistema exibe um formulário para registrar a saída.
   - [IN] O gerente preenche as informações necessárias (valor, descrição).
   - [IN] O gerente clica em "Salvar".
   - [OUT] O sistema valida as informações e registra a saída do caixa.
   - [OUT] O sistema exibe uma mensagem de confirmação.

#### Fluxo Alternativo
- **Erro ao Abrir Caixa**
  - [OUT] Se o gerente não preencher todos os campos obrigatórios, o sistema exibe uma mensagem de erro e solicita correção.

- **Erro ao Fechar Caixa**
  - [OUT] Se o valor encontrado no fechamento não corresponder ao esperado, o sistema exibe uma mensagem de erro informando o motivo.

#### Requisitos Não Funcionais
- O sistema deve ser responsivo e permitir que o gerente gerencie o caixa de maneira intuitiva.
- As mensagens de confirmação e erro devem ser claras e informativas.

![UCcaixa](Diagramas/Caso%20de%20Uso%20Venda.svg)

---

## 5. Caso de Uso Expandido

### UC Expandido 03: Gerenciar Estoque
#### Ator(es):
- Gerente: Responsável por gerenciar o estoque e garantir a disponibilidade dos produtos.
- Sistema de Estoque: Ferramenta que armazena, processa e exibe as informações de itens em estoque.
- Fornecedor: Fornece os produtos que serão adicionados ao estoque (envolvido indiretamente).
#### Interessado(s) e Interesse(s):
- Gerente: Garantir o controle adequado dos produtos em estoque, evitando faltas e excessos.
- Fornecedor: Fornecer produtos de forma contínua e garantir a reposição de itens.
- Sistema de Estoque: Armazenar e processar corretamente as informações de produtos e fornecer relatórios e alertas sobre a situação do estoque.
#### Pré-condições:
- O sistema de estoque deve estar funcionando corretamente.
- O gerente deve estar autenticado e com as permissões necessárias para gerenciar o estoque.
- O estoque deve possuir um catálogo de produtos previamente registrado no sistema.
#### Pós-condições:
- O item foi adicionado, editado, removido ou atualizado no sistema.
- O sistema registrou as transações de gerenciamento de estoque.
- O gerente recebeu alertas de estoque baixo, se aplicável.
- Relatórios de fornecedores foram gerados, se solicitado.
#### Questões em Aberto:
- Quais são os limites de quantidade para gerar um alerta de estoque baixo?
- O sistema deve registrar informações adicionais sobre fornecedores (por exemplo, histórico de entregas)?
- Existe a necessidade de gerar um relatório periódico de movimentações de estoque?
#### Fluxo Principal:
1. O gerente acessa a seção de "Gerenciar Estoque" no sistema.
2. [IN] O gerente seleciona uma das opções: adicionar, editar, visualizar ou remover um item do estoque.
3. [OUT] O sistema exibe um formulário com os campos necessários (nome do item, quantidade, preço, fornecedor, etc.).
4. [IN] O gerente preenche ou edita as informações do produto.
5. [OUT] O sistema valida os dados inseridos.
6. [IN] O gerente confirma a operação (adicionar, atualizar ou remover).
7. [OUT] O sistema registra a transação e atualiza o estado do estoque.
8. [OUT] Se aplicável, o sistema verifica o nível de estoque e exibe alertas de "Estoque Baixo" para o gerente.
#### Variantes:
- Adicionar Item ao Estoque 1.1. O gerente seleciona "Adicionar Item". 1.2. O sistema exibe o formulário de adição de item. 1.3. O gerente insere as informações do produto. 1.4. O sistema registra o novo item no estoque.

- Editar Item no Estoque 2.1. O gerente seleciona "Editar Item". 2.2. O sistema exibe o formulário com os dados atuais do produto. 2.3. O gerente altera as informações desejadas. 2.4. O sistema atualiza os dados no estoque.

- Remover Item do Estoque 3.1. O gerente seleciona "Remover Item". 3.2. O sistema solicita a confirmação da remoção. 3.3. O gerente confirma a remoção. 3.4. O sistema exclui o item do estoque e registra a transação.

- Gerar Relatório de Histórico de Fornecedores 4.1. O gerente seleciona "Gerar Relatório de Fornecedores". 4.2. O sistema coleta os dados de fornecedores e histórico de transações. 4.3. O sistema gera e exibe o relatório para o gerente.

#### Exceções:
- E1: Falha na Validação dos Dados do Produto:

   - O sistema detecta que campos obrigatórios não foram preenchidos ou valores são inválidos.
   - O sistema exibe uma mensagem de erro solicitando correção.

- E2: Tentativa de Remover Produto Vinculado a Outras Transações:

   - O sistema detecta que o item a ser removido está vinculado a vendas ou outras transações.
   - O sistema bloqueia a remoção e exibe uma mensagem ao gerente explicando o motivo.

- E3: Falha no Alerta de Estoque Baixo:

   - O sistema não dispara o alerta de estoque baixo corretamente.
   - O gerente pode configurar manualmente o limite de alerta, ou registrar uma reclamação no suporte técnico.

-  E4: Falha no Sistema de Geração de Relatórios:

   - O sistema não consegue gerar o relatório solicitado.
   - O gerente é informado sobre a falha e sugerido a tentar novamente ou contatar o suporte.

#### Fluxo de Alternativa:
-  Erro ao Adicionar ou Atualizar Produto
   - Se houver erro no cadastro ou atualização (como dados inconsistentes), o sistema exibe uma mensagem de erro e solicita correção.
---

### UC Expandido 04 - Gerenciar Caixa
#### Atores
- Gerente: Usuário responsável por realizar as operações de abertura, fechamento e controle de entradas e saídas de dinheiro no caixa.
#### Interessados e Interesses
- Gerente: Deseja garantir o controle eficiente do fluxo de caixa, incluindo a abertura, fechamento e registro de movimentações financeiras.
- Sistema: Deve registrar e gerenciar com precisão as operações de caixa, garantindo a integridade dos dados financeiros.
#### Pré-condições
- O gerente deve estar autenticado no sistema com permissões adequadas para gerenciar o caixa.
- O sistema deve estar em pleno funcionamento.
#### Pós-condições
- O caixa é aberto ou fechado com sucesso, com as informações registradas no sistema.
- Entradas e saídas de dinheiro são devidamente registradas, mantendo o saldo do caixa atualizado.
#### Questões em Aberto
- Há limites para os valores de abertura e fechamento do caixa?
- O sistema deve alertar o gerente sobre possíveis inconsistências nas entradas e saídas?
#### Fluxo Principal
1. Abrir Caixa

   - [IN] O gerente acessa a funcionalidade de abertura de caixa.
   - [OUT] O sistema exibe o formulário de abertura de caixa.
   - [IN] O gerente insere as informações requeridas, como data e valor inicial.
   - [IN] O gerente confirma a operação clicando em "Salvar".
   - [OUT] O sistema valida os dados e realiza a abertura do caixa.
   - [OUT] O sistema exibe uma mensagem de confirmação da operação.

2. Fechar Caixa

   - [IN] O gerente acessa a funcionalidade de fechamento de caixa.
   - [OUT] O sistema exibe o formulário de fechamento de caixa.
   - [IN] O gerente insere o valor total encontrado no caixa.
   - [IN] O gerente confirma a operação clicando em "Salvar".
   - [OUT] O sistema valida os dados e realiza o fechamento do caixa, registrando as movimentações.
   - [OUT] O sistema exibe uma mensagem de confirmação da operação.

3. Registrar Entrada de Dinheiro

   - [IN] O gerente acessa a funcionalidade de registrar entrada de dinheiro.
   - [OUT] O sistema exibe um formulário para registrar a entrada.
   - [IN] O gerente preenche os campos necessários, como valor e descrição da entrada.
   - [IN] O gerente confirma a operação clicando em "Salvar".
   - [OUT] O sistema valida as informações e registra a entrada no caixa.
   - [OUT] O sistema exibe uma mensagem de confirmação.

4. Registrar Saída de Dinheiro

   - [IN] O gerente acessa a funcionalidade de registrar saída de dinheiro.
   - [OUT] O sistema exibe um formulário para registrar a saída.
   - [IN] O gerente preenche os campos necessários, como valor e descrição da saída.
   - [IN] O gerente confirma a operação clicando em "Salvar".
   - [OUT] O sistema valida as informações e registra a saída no caixa.
   - [OUT] O sistema exibe uma mensagem de confirmação.

#### Fluxo Alternativo
- Erro ao Abrir Caixa
   - [OUT] Se o gerente deixar algum campo obrigatório vazio, o sistema exibe uma mensagem de erro, solicitando que os campos sejam preenchidos corretamente.
- Erro ao Fechar Caixa

   - [OUT] Se houver uma discrepância entre o valor informado pelo gerente e o valor esperado, o sistema exibe uma mensagem de erro, informando a diferença e solicitando a revisão dos dados.
#### Variantes
- Registro de Ajustes no Caixa
   - O gerente pode realizar ajustes no valor de abertura ou fechamento do caixa caso ocorra um erro de digitação ou se houver uma diferença detectada durante a contagem final.
   - [IN] O gerente acessa a funcionalidade de ajustes.
   - [OUT] O sistema exibe um formulário para correção de valores.
   - [IN] O gerente preenche o valor correto e confirma.
   - [OUT] O sistema valida o ajuste e atualiza o saldo do caixa.
#### Exceções
- E1: Falha no sistema ao abrir o caixa

   - [OUT] O sistema exibe uma mensagem de erro técnico.
   - [IN] O gerente pode tentar novamente ou contactar o suporte.

- E2: Inconsistência nos valores ao fechar o caixa

   - [OUT] O sistema exibe uma mensagem de alerta indicando discrepâncias.
   - [IN] O gerente revisa as entradas e saídas e pode corrigir o valor final.

- E3: Falha ao registrar entrada/saída

   - [OUT] Se o sistema não registrar a movimentação corretamente, uma mensagem de erro é exibida.
   - [IN] O gerente pode tentar novamente ou relatar o problema ao suporte.

#### Requisitos Não Funcionais
- O sistema deve ser acessível em dispositivos móveis e desktops.
- As operações de caixa devem ser realizadas de forma intuitiva e rápida.
- O sistema deve gerar relatórios detalhados de caixa, acessíveis para auditoria.
- As mensagens de erro e confirmação devem ser claras e compreensíveis.

---

## 6. Diagrama de sequência

### Diagrama de sequência para o caso de uso expandido Estoque;

![DiagramaEx](Diagramas/diagramaSeq-estoque.svg)


### Diagrama de sequência para o caso de uso expandido Caixa;
     
![DiagramaSeq6](Diagramas/diagramaSeq-Venda.svg)

---

## 7. Modelo conceitual
![DiagramaSeq4](Diagramas/Modelo_Conceitual.svg)

---

## 8. Diagrama de comunicação
### Venda
![DiagramaSeq4](Diagramas/Diagrama_de_Comunicacao.svg)
### Reabastecimento de Estoque
![DiagramaSeq4](Diagramas/Diagrama%20de%20comunicação2.svg)

---

## 9. Diagrama de classes
### Venda
![DiagramaSeq4](Diagramas/Diagrama%20de%20classes.svg)
### Reabastecimento de Estoque
![DiagramaSeq4](Diagramas/diagrama%20de%20classes2.svg)