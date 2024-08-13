# Requisito Funcional (RF001) - Cadastro de Usuário

## Descrição
O sistema deve permitir que novos usuários se cadastrem criando uma conta.

## Justificativa
Necessário para que os usuários possam acessar o sistema e utilizar suas funcionalidades.

## Critérios de Aceitação
- O usuário deve fornecer nome, email e senha.
- O sistema deve enviar um email de confirmação para o endereço fornecido.
- O cadastro deve ser confirmado apenas após a verificação do email.

## Prioridade
Alta

## Dependências
Nenhuma

## Status
Em progresso

## Versão
1.0

## Data de Fechamento da Versão
01/09/2024

## Responsáveis
- Nome: João Silva
- Assinatura: [assinatura digital ou campo para assinatura]

---

# Requisitos Funcionais e Não Funcionais

## F001 – Cadastro de Usuário
**Oculto:** Não
**Descrição:** O sistema deve permitir que novos usuários se cadastrem criando uma conta.

## Requisitos Não Funcionais
**Nome:** Tempo de Resposta
**Restrição:** O tempo de resposta para o cadastro deve ser inferior a 2 segundos.
**Categoria:** Desempenho
**Desejável:** Sim
**Permanente:** Sim

---

# Casos de Uso

## Alto nível

**Nome:** CDU001: Cadastro de Usuário
**Ator(es):** Usuário
**Descrição:** O usuário se cadastra no sistema fornecendo suas informações pessoais.
**Referência cruzada:** RF001

## Expansão dos casos de uso

**CDU001 - Cadastro de Usuário**
**Ator(es):** Usuário
**Interessado e interesses:**
- **Usuário:** Deseja acessar o sistema e utilizar suas funcionalidades.
**Pré-condições:** 
- O usuário deve ter acesso à internet.
**Pós-condições:**
- O usuário tem uma conta ativa no sistema.
**Fluxo principal (cenário de sucesso):**
1. O usuário acessa a página de cadastro.
2. O usuário preenche o formulário com nome, email e senha.
3. O sistema valida as informações fornecidas.
4. O sistema envia um email de confirmação.
5. O usuário confirma o cadastro através do link enviado no email.
**Fluxo(s) alternativo(s):**
- **2a.** O usuário não preenche todos os campos obrigatórios:
  - **2a1.** O sistema exibe uma mensagem de erro.
- **3a.** O email fornecido já está em uso:
  - **3a1.** O sistema exibe uma mensagem de erro.
**Exceções:**
- **4.1:** Falha no envio do email:
  - **4.1.1:** O sistema tenta reenviar o email após alguns minutos.
**Variantes:**
- **5.1:** O usuário não confirma o cadastro em 24 horas:
  - **5.1.1:** O sistema exclui o cadastro pendente.
**Requisitos especiais:**
- **Segurança:** O sistema deve criptografar as senhas dos usuários.
**Variações tecnológicas e de dados:**
- **Tecnologia:** O sistema pode ser acessado via desktop e mobile.
**Frequência de ocorrência:** Alta
**Problema(s) em aberto:** Nenhum

---

# Conceitos

## Modelo Conceitual Preliminar

### Tabela de manutenção de conceito

| Conceito | I | A | E | C | Observação | Referência cruzada |
|----------|---|---|---|---|-------------|--------------------|
| Cadastro de Usuário | X | X | X | X | Contém informações básicas do usuário | RF001 |

---

# Consultas e Relatórios

**Nome:** Relatório de Novos Cadastros
**Referência cruzada:** RF001, NF001

