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
5. Gerenciar Relatorios

## Requisitos Não Funcionais

## Requisitos Suplementares

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

---
## UC02
### Nome do Caso de Uso
Gerenciar Fornecedores

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

---

## Expansão de caso de uso crítico

## Diagrama de sequência

## Modelo conceitual

## Diagrama de classes

