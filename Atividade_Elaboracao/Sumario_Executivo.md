# Sistema de Gestão de Sorveteria
## Sumário
1. [VISÃO GERAL DO SISTEMA](#1-visão-geral-do-sistema)
2. [LEVANTAMENTO DE REQUISITOS](#3-levantamento-de-requisitos)

   2.1. [REQUISITOS FUNCIONAIS](#31-requisitos-funcionais)
   
   2.2. [REQUISITOS NÃO FUNCIONAIS](#32-requisitos-não-funcionais)
   
3. [DETALHAMENTO DE REQUISITOS](#4-detalhamento-de-requisitos)
4. [CASOS DE USO](#5-casos-de-uso)
5. [DIAGRAMA DE SEQUÊNCUA ](#6-diagramas-de-sequência)
6. [

## Visão Geral

## Requisitos
1. Gerenciar Estoque
2. Gerenciar Funcionarios
3. Gestão de Fornecedores
4. Gerenciar Caixa

## Requisitos Não Funcionais
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

## Requisitos Suplementares
1. O sistema deve operar via plataforma desktop.
2. O sistema deve utilizar o banco de dados postgres.
3. O sistema deve utilizar a linguagem Java.
4. O sistema deve utilzar o Spring Security para realizar a segurança de acesso.
5. O sistema deve gerar relatorios por meio da biblioteca JasperReports.

## Detalhamento dos Requisitos
| **RF1. Gerenciar Estoque** |
|:---|
| **Descrição:**<br>Este requisito estabelece a necessidade de um sistema abrangente para o gerenciamento de estoque da sorveteria, que permita o controle eficiente de entradas e saídas de produtos. O sistema deve garantir a precisão nas informações de estoque, possibilitando um acompanhamento em tempo real da quantidade disponível. Além disso, deve incluir funcionalidades para monitorar a validade dos produtos e emitir alertas automáticos quando os níveis de estoque atingirem limites críticos, evitando desperdícios e assegurando a disponibilidade de produtos para os clientes.|
| **Fontes:**<br>Departamento responsavel pelo estoue e feedback interno dos funcionarios|
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

## UC01.

### Nome do Caso de Uso: Gerenciar Funcionários

### Atores
- **Gerente**: Usuário com permissão para adicionar, editar, visualizar e remover funcionários.

### Descrição
Este caso de uso permite que o gerente do sistema adicione, edite, visualize e remova informações sobre os funcionários da loja.

### Pré-condições
- O gerente deve estar autenticado no sistema.
- O gerente deve ter permissões adequadas para realizar operações de gerenciamento de funcionários.

### Pós-condições
- As informações do funcionário são atualizadas no sistema.
- O funcionário é adicionado ou removido do sistema, conforme a operação realizada.

### Fluxo Principal
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

### Fluxo Alternativo
- **Erro ao Adicionar Funcionário**
  - [OUT] Se o gerente não preencher todos os campos obrigatórios, o sistema exibe uma mensagem de erro e solicita correção.

- **Erro ao Remover Funcionário**
  - [OUT] Se houver um erro durante a remoção (ex: funcionário com registros pendentes), o sistema exibe uma mensagem de erro informando o motivo.

### Requisitos Não Funcionais
- O sistema deve ser responsivo e permitir que o gerente gerencie os funcionários de maneira intuitiva.
- As mensagens de confirmação e erro devem ser claras e informativas.

![UCfuncionario](Diagramas/UCfuncionario.png)

---
## UC02
### Nome do Caso de Uso Gerenciar Fornecedores

### Atores
- **Gerente**: Usuário com permissão para adicionar, editar, visualizar e remover fornecedores.

### Descrição
Este caso de uso permite que o gerente do sistema adicione, edite, visualize e remova informações sobre os fornecedores da loja de sorvetes.

### Pré-condições
- O gerente deve estar autenticado no sistema.
- O gerente deve ter permissões adequadas para realizar operações de gerenciamento de fornecedores.

### Pós-condições
- As informações do fornecedor são atualizadas no sistema.
- O fornecedor é adicionado ou removido do sistema, conforme a operação realizada.

### Fluxo Principal
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

### Fluxo Alternativo
- **Erro ao Adicionar Fornecedor**
  - [OUT] Se o gerente não preencher todos os campos obrigatórios, o sistema exibe uma mensagem de erro e solicita correção.

- **Erro ao Remover Fornecedor**
  - [OUT] Se houver um erro durante a remoção (ex: fornecedor associado a produtos), o sistema exibe uma mensagem de erro informando o motivo.

### Requisitos Não Funcionais
- O sistema deve ser responsivo e permitir que o gerente gerencie os fornecedores de maneira intuitiva.
- As mensagens de confirmação e erro devem ser claras e informativas.

![UCfornecedor](Diagramas/UCfornecedor.png)

---

## Expansão de caso de uso crítico

## Diagrama de sequência

## Modelo conceitual

## Diagrama de classes

