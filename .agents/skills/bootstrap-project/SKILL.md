---
name: bootstrap-project
description: >-
  Inicializa e padroniza 100% da arquitetura do agente em Modo Fast-Track (1
  turno quando o usuário cola o Gabarito do ESTRUTURADOR_DE_AGENTE.md) ou via
  Entrevista Guiada Otimizada na IDE, gravando todos os arquivos em lote
  paralelo, criando as primeiras Skills e removendo o kit temporário de
  instalação ao concluir.
---

# Skill: Onboarding e Materialização de Alta Performance (`bootstrap-project`)

Esta skill é o motor de inicialização do template `epic-tesla`. Ela opera em **2 Modos de Execução** para eliminar redundâncias, economizar tokens e materializar o agente em segundos.

---

## ⚡ Seleção Automática do Modo de Execução (Verifique Antes de Agir!)

Analise a mensagem do usuário e escolha **imediatamente** a rota correta:

### 🔥 MODO 1: Fast-Track (Gabarito Completo ou Briefing Estruturado Recebido)
- **Quando ativar:** Sempre que o usuário colar o **Gabarito Completo dos 5 Passos** (gerado pelo [`ESTRUTURADOR_DE_AGENTE.md`](../../../ESTRUTURADOR_DE_AGENTE.md)) ou um briefing que já contenha as definições de Identidade, Regras/Domínio, Stack, Segurança e Skills.
- **Regra de Performance (Zero-Confirmation / 1 Turno):**
  - ❌ **PROIBIDO fazer novas perguntas** se os 5 passos já estiverem presentes.
  - ❌ **PROIBIDO gerar um resumo pedindo confirmação novamente** (o usuário já revisou no `ESTRUTURADOR_DE_AGENTE.md`).
  - ✅ **AÇÃO IMEDIATA:** Se houver alguma micro-lacuna secundária, infira silenciosamente com o padrão sênior de mercado e **execute diretamente a Fase 2 (Gravação Total em Lote Paralelo) neste mesmo turno!**

### 💬 MODO 2: Concepção Guiada na IDE (Quando o usuário digita apenas *"Iniciar"* ou traz uma ideia inicial)
- **Quando ativar:** Quando o usuário iniciar do zero diretamente na IDE sem ter usado o `ESTRUTURADOR_DE_AGENTE.md` previamente.
- **Como conduzir (Sem Burocracia):**
  - Se o usuário digitou apenas *"Iniciar"*, faça a pergunta de abertura direta: pergunte **qual é a ideia do agente e qual problema ele quer resolver**, e se ele **(1) já sabe tudo o que quer** ou **(2) precisa de ajuda para lapidar a ideia**.
  - Conduza a coleta das **Etapas 1 a 5** (descritas na Fase 1 abaixo) fornecendo exemplos ricos adaptados ao projeto dele e **estabelecendo proativamente o Padrão Ideal da Etapa 4 (Segurança, Fallbacks e DoD)**.
  - Apresente o Gabarito Consolidado de 1 a 5 para revisão rápida e, após o *"De acordo"*, execute a **Fase 2 (Gravação Total em Lote Paralelo)**.

---

## Fase 1: Especificação das 5 Etapas (Para Coleta no Modo 2 ou Auditoria no Modo 1)

### Passo 1 de 5: Identidade, Missão e Visão Geral do Projeto
*(Alimenta: `AGENTS.md` Seção 2 e `business_context.md` Seção 1)*
1. **Nome do Projeto e Natureza:** (Software/API, Automação Comercial, Operações/Rotina ou Híbrido)
2. **Papel do Agente (Role):** Cargo e especialidade sênior.
3. **Problema Central e Proposta de Valor:** Dor que resolve e diferencial.
4. **Modelo de Operação/Receita:** (SaaS B2B, Produto Interno, Agência, Backoffice Familiar).
5. **Objetivo Final Mensurável (Estado Desejado):** Meta quantificável de latência, precisão e resultado.

### Passo 2 de 5: Público-Alvo (ICP), Regras de Negócio, Glossário e KPIs
*(Alimenta: `business_context.md` Seções 2, 3, 4 e 5)*
1. **Perfil de Público/Personas (ICP):** Quem usa/compra, Dor Principal, Ganho Esperado e Objeções/Restrições.
2. **Regras de Negócio e Matriz de Decisão:** Políticas operacionais e regras de roteamento (`Condição -> Ação/Destino`).
3. **Glossário e Siglas do Domínio:** Entidades de contexto, pessoas-chave, listas, siglas e jargões internos.
4. **Métricas de Sucesso (KPIs do Agente):** Indicadores objetivos de qualidade das entregas.

### Passo 3 de 5: Stack Tecnológica, Ferramentas (`MCP`), Estrutura e Comandos
*(Alimenta: `architecture_and_stack.md` Completo e `.agents/mcp_config.json`)*
1. **Stack Core / Softwares:** Linguagens, frameworks, validadores de schema e persistência local (ex: SQLite para auditoria/retry).
2. **Integrações Externas (`MCP` / APIs):** Serviços externos e conectores MCP.
3. **Estrutura de Diretórios Planejada:** Organização das pastas do projeto + `.agents/`.
4. **Comandos Canônicos:** `Setup`, `Dev Server`, `CLI Local` e `Testes`.

### Passo 4 de 5: Segurança, Guardrails de Domínio e Padrão de Qualidade (`DoD`)
*(Alimenta: `security_and_guardrails.md` e `git_and_quality_standards.md` — **Sempre estabelecido proativamente pela IA conforme o projeto**)*
1. **Segurança e Privacidade:** Proteção de `.env`/tokens OAuth, sanitização de dados sensíveis (LGPD/PII/saúde/finanças) em logs, defesa contra *Prompt Injection* e travas *Human-in-the-Loop* contra deleções ou disparos externos sem confirmação.
2. **Convenções Técnicas e de Domínio:** Fuso horário rígido (ex: `America/Fortaleza` / `America/Sao_Paulo` `UTC-3`), horários/parâmetros de *fallback* determinísticos, tipagem estrita e padrão de idioma.
3. **Critério de Pronto (`Definition of Done - DoD`):** Testes com cenários compostos reais, suíte de testes passando, tratamento de timeout/retry e zero segredos hardcoded.

### Passo 5 de 5: Estilo Pessoal do Operador e Primeiras `Skills` do Projeto
*(Alimenta: `AGENTS.md` Seção 3, `current_learnings.md` Seção 1 e cria as pastas em `.agents/skills/`)*
1. **Preferências do Operador:** Estilo de resposta executivo, regra do mini-plano de 5 linhas (para mudanças em $> 3$ arquivos) e formato de recibo visual diário.
2. **Primeiras `Skills` (2 a 3 rotinas em `.agents/skills/<nome>/SKILL.md`):** Nome em `kebab-case`, gatilho YAML, insumos, passo a passo (SOP) e DoD.

---

## Fase 2: Gravação Total em Lote Paralelo (`Batch Parallel Write`) e Autolimpeza

Para máxima performance, **NÃO edite arquivos um por um sequencialmente**. Execute chamadas `write_file` (`Overwrite=true`) **em paralelo na mesma resposta** para gravar todos os arquivos abaixo:

1. **Gravar [`AGENTS.md`](../../../AGENTS.md):**
   - Remova o bloco superior `> **[DIRETRIZ DE AUTO-PADRONIZAÇÃO E GATILHO DE ONBOARDING PARA A IA]**`.
   - No passo 2 do Protocolo de Boot, substitua a verificação de onboarding por: `2. **Alinhamento de Missão:** Opere estritamente dentro do papel e objetivo final definidos na Seção 2.`
   - Preencha a seção **2. Identidade e Missão do Projeto** e refine a seção **3. Diretrizes de Tom, Postura e Comunicação**.
   - **Limite Rígido:** Garanta que o `AGENTS.md` final tenha **menos de 150 linhas**.

2. **Gravar [`.agents/context/business_context.md`](../../context/business_context.md):**
   - Remova o cabeçalho `> **[INSTRUÇÃO DE PADRONIZAÇÃO PARA A IA]**` e preencha 100% das seções: Visão Geral, Tabela de Personas (ICP), Regras de Negócio / Matriz de Roteamento, Tabela de Glossário/Entidades e KPIs do Agente.

3. **Gravar [`.agents/context/architecture_and_stack.md`](../../context/architecture_and_stack.md):**
   - Remova o cabeçalho `> **[INSTRUÇÃO DE PADRONIZAÇÃO PARA A IA]**` e preencha 100% das seções: Tabela de Stack/Ferramentas, Árvore de Diretórios planejada, Comandos Canônicos e Estratégia de Roteamento de Modelos.

4. **Gravar [`.agents/rules/security_and_guardrails.md`](../../rules/security_and_guardrails.md) e [`.agents/rules/git_and_quality_standards.md`](../../rules/git_and_quality_standards.md):**
   - Remova os cabeçalhos temporários de onboarding e preencha as restrições específicas do domínio (Seção 4 de `security_and_guardrails.md`), o DoD customizado (Seção 1 de `git_and_quality_standards.md`) e as convenções técnicas consolidadas (Seção 4 de `git_and_quality_standards.md` — fuso horário, fallbacks, tipagem).

5. **Gravar [`.agents/memory/current_learnings.md`](../../memory/current_learnings.md) e [`.agents/mcp_config.json`](../../mcp_config.json):**
   - Registre em `current_learnings.md` com a data atual (`[AAAA-MM-DD]`) as preferências do operador e regras críticas iniciais.
   - Configure em `mcp_config.json` os servidores MCP reais do projeto (removendo a chave `_comment_instrucao_ia` e exemplos inativos).

6. **Criar em Paralelo as Primeiras Skills do Projeto (`.agents/skills/<nome-da-skill>/SKILL.md`):**
   - Seguindo a estrutura de [`skill_template.md`](../create-skill/resources/skill_template.md), crie todos os arquivos `SKILL.md` mapeados no Passo 5 (com YAML frontmatter `name` e `description`, Objetivo, Insumos, Passo a Passo SOP, Exceções e DoD).

7. **Autodestruir o Kit Temporário de Instalação:**
   - Execute um comando de terminal para remover simultaneamente da raiz e de `.agents/skills/`:
     - `COMECE_AQUI.md`
     - `ESTRUTURADOR_DE_AGENTE.md`
     - `.agents/skills/bootstrap-project/` *(como o projeto já foi inicializado, esta skill de setup é removida para economizar contexto permanente; permanecem `create-skill`, `compact-memory` e as novas Skills do projeto)*.

---

## Checklist Obrigatório de Validação Final (DoD do Bootstrap)
Antes de entregar a mensagem final de conclusão ao usuário, verifique:
- [ ] **Zero Placeholders:** Nenhum arquivo do projeto contém o texto `[PENDENTE`.
- [ ] **Teto de Contexto:** `AGENTS.md` possui $< 150$ linhas e `current_learnings.md` possui $< 100$ linhas.
- [ ] **Novas Skills Criadas:** Todas as pastas e arquivos `SKILL.md` do projeto existem em `.agents/skills/`.
- [ ] **Limpeza Completa:** `COMECE_AQUI.md`, `ESTRUTURADOR_DE_AGENTE.md` e `.agents/skills/bootstrap-project/` foram removidos.
