# Teste Técnico -- QA Tester

Este repositório contém o relatório de análise exploratória do
microssistema disponibilizado no teste técnico para a vaga de **QA
Tester**.

O objetivo da análise foi identificar **bugs funcionais**,
**inconsistências de experiência do usuário**, **possíveis problemas de
segurança** e **classificar/priorizar os problemas encontrados**.

Sistema analisado: https://qa-play-sim.lovable.app/

------------------------------------------------------------------------

## Objetivo

Realizar uma análise exploratória do sistema com foco em:

-   Identificar bugs funcionais
-   Avaliar inconsistências de experiência do usuário (UX)
-   Detectar problemas básicos de segurança
-   Classificar e priorizar os problemas encontrados

------------------------------------------------------------------------

## Resumo dos Problemas Identificados

Durante os testes exploratórios foram identificados **9 problemas** no
sistema.

  Severidade   Quantidade
  ------------ ------------
  Crítico      3
  Alto         3
  Médio        3
  Baixo        0

A maioria dos problemas encontrados está relacionada à **falta de
validação de dados no formulário de cadastro**, permitindo a criação de
contas com informações incompletas ou inválidas.

------------------------------------------------------------------------

## Ambiente de Testes

Os testes foram realizados no seguinte ambiente:

-   Sistema Operacional: Windows
-   Navegador: Google Chrome
-   Tipo de teste: Teste exploratório manual

------------------------------------------------------------------------

## Metodologia de Teste

Durante a análise foram realizados:

-   Testes exploratórios
-   Testes de validação de formulário
-   Testes de consistência de dados
-   Testes básicos de segurança
-   Testes de experiência do usuário (UX)

------------------------------------------------------------------------

## Tipos de Problemas Identificados

Durante a análise foram encontrados problemas nas seguintes categorias:

-   Falta de validação de campos obrigatórios
-   Falta de validação de formato de dados
-   Problemas de integridade de dados (email duplicado)
-   Problemas de experiência do usuário
-   Possíveis riscos de segurança

------------------------------------------------------------------------

# Bugs Encontrados

## Bug 1 --- Sistema permite criar conta sem preencher os campos obrigatórios

**Descrição**\
O sistema permite criar uma conta mesmo quando nenhum campo do
formulário é preenchido.

**Passos para reproduzir**

1.  Acessar a página de cadastro\
2.  Não preencher nenhum campo\
3.  Clicar em **Criar Conta**

**Resultado atual**\
A conta é criada mesmo com todos os campos vazios.

**Resultado esperado**\
O sistema deve impedir o cadastro e exibir mensagens informando que os
campos são obrigatórios.

**Severidade:** Crítico\
**Prioridade:** Alta

------------------------------------------------------------------------

## Bug 2 --- Campo "Nome Completo" não é obrigatório

**Descrição**\
O sistema permite finalizar o cadastro sem preencher o campo **Nome
Completo**.

**Passos para reproduzir**

1.  Acessar a tela de cadastro\
2.  Preencher os outros campos\
3.  Deixar **Nome Completo** vazio\
4.  Clicar em **Criar Conta**

**Resultado atual**\
Conta criada normalmente.

**Resultado esperado**\
O sistema deve exigir o preenchimento do nome completo.

**Severidade:** Alto\
**Prioridade:** Alta

------------------------------------------------------------------------

## Bug 3 --- Campo "Telefone" não é obrigatório

**Descrição**\
O sistema permite criar uma conta sem preencher o campo telefone.

**Passos para reproduzir**

1.  Acessar cadastro\
2.  Preencher os outros campos\
3.  Deixar o campo **Telefone** vazio\
4.  Criar conta

**Resultado atual**\
Cadastro realizado com sucesso.

**Resultado esperado**\
O sistema deve exigir o preenchimento ou informar que o campo é
opcional.

**Severidade:** Médio\
**Prioridade:** Média

------------------------------------------------------------------------

## Bug 4 --- Campo Email não possui validação obrigatória

**Descrição**\
O sistema permite criar uma conta sem preencher o campo email.

**Passos para reproduzir**

1.  Acessar cadastro\
2.  Preencher outros campos\
3.  Deixar o campo **Email** vazio\
4.  Criar conta

**Resultado atual**\
Conta criada sem email.

**Resultado esperado**\
O sistema deve exigir um email válido para cadastro.

**Severidade:** Crítico\
**Prioridade:** Alta

------------------------------------------------------------------------

## Bug 5 --- Campo Senha não é obrigatório

**Descrição**\
O sistema permite criar conta sem definir uma senha.

**Passos para reproduzir**

1.  Acessar cadastro\
2.  Preencher outros campos\
3.  Deixar o campo **Senha** vazio\
4.  Criar conta

**Resultado atual**\
Conta criada sem senha.

**Resultado esperado**\
O sistema deve exigir senha para criação da conta.

**Severidade:** Crítico\
**Prioridade:** Alta

------------------------------------------------------------------------

## Bug 6 --- Sistema permite cadastro com email já existente

**Descrição**\
O sistema permite criar múltiplas contas utilizando o mesmo email.

**Passos para reproduzir**

1.  Criar uma conta com um email\
2.  Voltar para a tela de cadastro\
3.  Tentar criar nova conta com o mesmo email

**Resultado atual**\
O sistema permite o cadastro duplicado.

**Resultado esperado**\
O sistema deve impedir cadastro com email já existente e informar o
usuário.

**Severidade:** Alto\
**Prioridade:** Alta

------------------------------------------------------------------------

## Bug 7 --- Sistema aceita email em formato inválido

**Descrição**\
O campo de email aceita valores que não seguem o padrão de email válido.

**Passos para reproduzir**

1.  Acessar cadastro\
2.  Inserir no campo email: teste ou teste@teste\
3.  Criar conta

**Resultado atual**\
O sistema aceita o email inválido.

**Resultado esperado**\
O sistema deve validar o formato do email.

**Severidade:** Alto\
**Prioridade:** Alta

------------------------------------------------------------------------

## Bug 8 --- Sistema permite senha fraca

**Descrição**\
O sistema aceita senhas muito simples e curtas.

**Passos para reproduzir**

1.  Acessar cadastro\
2.  Inserir senha como: 1 ou 123\
3.  Criar conta

**Resultado atual**\
Cadastro realizado.

**Resultado esperado**\
O sistema deveria exigir regras mínimas de segurança para senha.

Exemplo:

-   mínimo de 8 caracteres\
-   letras e números

**Severidade:** Médio\
**Prioridade:** Média

------------------------------------------------------------------------

## Bug 9 --- Sistema aceita campos com apenas espaços

**Descrição**\
Campos podem ser preenchidos apenas com espaços e ainda assim serem
aceitos como válidos.

**Passos para reproduzir**

1.  No campo nome inserir apenas espaços\
2.  Preencher os outros campos\
3.  Criar conta

**Resultado atual**\
O sistema aceita o cadastro.

**Resultado esperado**\
O sistema deve remover espaços antes da validação e impedir esse tipo de
entrada.

**Severidade:** Médio\
**Prioridade:** Média

------------------------------------------------------------------------

# Bugs Prioritários

## 1 --- Criação de conta sem campos obrigatórios

Esse problema compromete a integridade dos dados do sistema, permitindo
a criação de usuários inválidos.

## 2 --- Cadastro com email duplicado

O email normalmente funciona como identificador único do usuário.
Permitir duplicidade pode causar:

-   problemas de login
-   falhas na recuperação de senha
-   inconsistência no banco de dados

------------------------------------------------------------------------

# Sugestões de Melhoria

### Validação de formulário

Implementar validação obrigatória para:

-   Nome completo
-   Email
-   Senha

### Validação de formato de email

Garantir que o email siga o padrão correto:

usuario@email.com

### Regras de senha

Implementar critérios mínimos de segurança:

-   mínimo de 8 caracteres
-   letras e números
-   caracteres especiais

### Feedback visual para erros

Exibir mensagens claras quando o usuário cometer erros no formulário.

Exemplo:

Email inválido\
Senha deve ter no mínimo 8 caracteres

### Máscara para telefone

Aplicar formatação automática para facilitar o preenchimento.

Exemplo:

(0) 00000-0000

### Verificação de email

Implementar confirmação de cadastro por email para evitar contas falsas.

------------------------------------------------------------------------

# Conclusão

A análise exploratória identificou diversos problemas relacionados
principalmente à **validação de dados e controle de cadastro de
usuários**.

A implementação de validações adequadas e melhorias de experiência do
usuário contribuiria significativamente para aumentar a **segurança,
integridade dos dados e usabilidade do sistema**.

Este relatório foi elaborado a partir de testes exploratórios com foco
na identificação de falhas funcionais, problemas de validação de dados e
melhorias de experiência do usuário.
