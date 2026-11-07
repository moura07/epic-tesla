# 🚀 COMECE AQUI — Inicialização Rápida do Seu Agente (`epic-tesla`)

> **[INSTRUÇÃO AUTOMÁTICA PARA A IA]:**
> Este arquivo faz parte do kit temporário de onboarding do template `epic-tesla`. Assim que a skill `bootstrap-project` concluir o preenchimento de todos os arquivos da estrutura e criar as Skills iniciais do projeto, **você deve excluir automaticamente `COMECE_AQUI.md`, `ESTRUTURADOR_DE_AGENTE.md` e a pasta `.agents/skills/bootstrap-project/`** para deixar o repositório 100% limpo para produção.

---

Bem-vindo! Este repositório já possui toda a engenharia de contexto, memória em 2 camadas e governança pronta. Você **não precisa editar nenhum arquivo manualmente**. Escolha abaixo o seu modo preferido de partida:

---

## 🔥 Modo 1: Fast-Track via Chat Externo (Recomendado — Mais Rápido e Zero Tokens na IDE)

Ideal para quando você quer **lapidar a ideia do agente, descobrir novas automações do dia a dia e revisar todas as 5 etapas com calma** antes de gravar no repositório:

1. **Anexe o arquivo [`ESTRUTURADOR_DE_AGENTE.md`](ESTRUTURADOR_DE_AGENTE.md)** em qualquer chat tradicional (**Gemini Web, ChatGPT, Claude**, etc.).
2. **Responda à pergunta inicial sem enrolação:** Diga qual problema quer resolver — seja você alguém que **(1) já sabe tudo o que quer** ou **(2) precisa de ajuda para lapidar a ideia**.
3. **Revise o Gabarito Completo dos 5 Passos:** A IA do chat vai conectar sua ideia à arquitetura `epic-tesla`, estabelecer o **padrão ideal de segurança (Etapa 4)** automaticamente e entregar o bloco final pronto.
4. **Cole o Bloco Final aqui na IDE (Antigravity, Claude Code, Cursor):** O agente da IDE reconhecerá o Gabarito completo e **gravará todos os arquivos + Skills em 1 único turno (~8 segundos)**, sem refazer perguntas!

---

## ⚡ Modo 2: Entrevista Guiada Direto na IDE (100% no Antigravity / Cursor / Claude Code)

Se preferir fazer tudo diretamente dentro da sua IDE sem abrir um chat externo, basta digitar no chat do agente:

> **"Iniciar"** *(ou "Quero criar um agente para [descreva sua ideia]")*

O agente ativará a skill [`bootstrap-project`](.agents/skills/bootstrap-project/SKILL.md), ajudará você a estruturar as 5 etapas com exemplos ricos adaptados ao seu projeto e estabelecerá o padrão ideal de segurança:

1. **Passo 1 — Identidade, Missão e Visão Geral:** Nome, papel sênior do agente, proposta de valor e meta mensurável.
2. **Passo 2 — Público (ICP), Regras de Negócio, Glossário e KPIs:** Personas, matriz de decisão/roteamento, entidades do domínio e métricas.
3. **Passo 3 — Stack, Ferramentas (`MCP`), Estrutura e Comandos:** Tecnologias, banco de auditoria, integrações e comandos canônicos.
4. **Passo 4 — Segurança, Guardrails e Qualidade (`DoD`):** Padrão ideal estabelecido proativamente pela IA para o seu projeto.
5. **Passo 5 — Seu Estilo de Trabalho e Primeiras `Skills`:** Preferências de interação e as 2 a 3 rotinas que já nascem prontas em `.agents/skills/`.

---

## 🎁 Entrega Final Automática (Em Ambos os Modos)

Assim que os 5 Passos estiverem definidos, o agente executará em **lote paralelo (`Batch Parallel Write`)**:
- ✅ Preenchimento de 100% do [`AGENTS.md`](AGENTS.md) mantendo-o enxuto ($< 150$ linhas).
- ✅ Preenchimento completo de [`business_context.md`](.agents/context/business_context.md) e [`architecture_and_stack.md`](.agents/context/architecture_and_stack.md).
- ✅ Configuração de segurança e DoD em [`security_and_guardrails.md`](.agents/rules/security_and_guardrails.md) e [`git_and_quality_standards.md`](.agents/rules/git_and_quality_standards.md).
- ✅ Registro de suas preferências em [`current_learnings.md`](.agents/memory/current_learnings.md) e conectores em [`mcp_config.json`](.agents/mcp_config.json).
- ✅ **Criação automática das primeiras pastas e arquivos `SKILL.md`** em `.agents/skills/`.
- ✅ **Autolimpeza do kit de instalação:** Remoção automática de `COMECE_AQUI.md`, `ESTRUTURADOR_DE_AGENTE.md` e `.agents/skills/bootstrap-project/`, deixando o repositório limpo e em produção!
