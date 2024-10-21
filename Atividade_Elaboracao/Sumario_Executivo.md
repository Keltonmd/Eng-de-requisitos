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

## Casos de Uso

## Expansão de caso de uso crítico

## Diagrama de sequência

## Modelo conceitual

## Diagrama de classes

