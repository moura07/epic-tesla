---
name: bootstrap-project
description: >-
  Inicializa e padroniza toda a arquitetura do agente quando um novo projeto é
  iniciado ou quando o usuário fornece o contexto inicial do projeto. Use esta
  skill sempre que AGENTS.md contiver marcadores [PENDENTE DE CONTEXTO] ou quando
  o usuário pedir para configurar/inicializar o agente para o projeto.
---

# Skill: Inicialização e Padronização do Projeto (`bootstrap-project`)

Esta skill transforma um contexto bruto fornecido pelo usuário (ou extraído de uma entrevista rápida) em uma arquitetura de agente 100% padronizada, populando os arquivos base sem violar os limites de janela de contexto.

---

## Etapa 1: Coleta e Diagnóstico de Contexto

Verifique o que o usuário já forneceu na mensagem atual e inspecione os arquivos existentes no repositório.

### Caso A: O usuário já enviou o contexto do projeto (texto, briefing, documentação ou código)
1. Extraia diretamente os 4 pilares fundamentais:
   - **Identidade e Objetivo Final:** Qual é o projeto e qual resultado o agente deve entregar?
   - **Negócio e Público:** Regras de negócio, público-alvo, produto e métricas.
   - **Stack e Ferramentas:** Tecnologias, integrações externas (`MCP`) e ambiente.
   - **Restrições e Guardrails:** O que o agente jamais deve fazer neste domínio?
2. Se algum pilar crítico estiver ausente, faça **no máximo 2 a 3 perguntas diretas e agrupadas** antes de preencher os arquivos.

### Caso B: O usuário pediu para iniciar do zero sem fornecer contexto
Conduza uma **Entrevista Estruturada Sequencial** (fazendo 1 pergunta por vez para não sobrecarregar o operador):
1. **Pergunta 1 (Objetivo e Papel):** *"Qual é o nome deste projeto, seu objetivo final principal e qual papel específico você quer que eu assuma?"*
2. **Pergunta 2 (Público e Regras de Negócio):** *"Quem é o público-alvo/cliente final e quais são as principais regras de negócio ou critérios de qualidade das entregas?"*
3. **Pergunta 3 (Stack e Ferramentas):** *"Quais tecnologias, softwares externos (ex: Gmail, Notion, banco SQL, GitHub) ou ferramentas farão parte da rotina?"*
4. **Pergunta 4 (Restrições Críticas):** *"O que eu JAMAIS devo fazer neste projeto e qual tom de voz devo adotar?"*

---

## Etapa 2: Padronização dos Arquivos da Arquitetura

Com os dados em mãos, edite e padronize os arquivos na seguinte ordem:

1. **Atualizar [`AGENTS.md`](../../../AGENTS.md):**
   - Preencha a seção **2. Identidade e Missão do Projeto** substituindo todos os `[PENDENTE DE CONTEXTO]`.
   - Ajuste a seção **3. Diretrizes de Tom, Postura e Comunicação** caso o projeto exija um tom específico.
   - Remova o bloco de aviso inicial de `Modo de Onboarding` se o arquivo já estiver 100% configurado.
   - **Regra de Ouro:** Mantenha o `AGENTS.md` com **menos de 150 linhas**.

2. **Atualizar [`.agents/context/business_context.md`](../../context/business_context.md):**
   - Preencha Visão Geral, ICP/Personas (em tabela), Regras de Negócio, Glossário e KPIs.

3. **Atualizar [`.agents/context/architecture_and_stack.md`](../../context/architecture_and_stack.md):**
   - Preencha a tabela de Stack/Ferramentas, a árvore de diretórios atual do projeto e os comandos canônicos.

4. **Atualizar [`.agents/rules/security_and_guardrails.md`](../../rules/security_and_guardrails.md):**
   - Adicione na seção 4 as restrições específicas do domínio informadas pelo usuário.

---

## Etapa 3: Recomendação de `Skills` e `MCP` Iniciais

Ao concluir a padronização dos arquivos, apresente ao usuário um resumo executivo contendo:
1. Confirmação dos arquivos configurados.
2. Sugestão de **2 a 3 Skills específicas** que podem ser criadas para automatizar as rotinas mais frequentes daquele projeto (usando a skill `create-skill`).
3. Sugestão de servidores **MCP** (em `.agents/mcp_config.json`) caso o projeto envolva ferramentas externas.

---

## Critérios de Validação (Checklist Final)
- [ ] Nenhum placeholder `[PENDENTE DE CONTEXTO]` restou no `AGENTS.md`.
- [ ] `AGENTS.md` possui menos de 150 linhas.
- [ ] `business_context.md` e `architecture_and_stack.md` estão estruturados com listas e tabelas claras.
