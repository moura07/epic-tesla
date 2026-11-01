# 🚀 COMECE AQUI — Inicialização Rápida do Seu Agente (`epic-tesla`)

> **[INSTRUÇÃO AUTOMÁTICA PARA A IA]:**
> Este arquivo é o guia temporário de onboarding do template `epic-tesla`. Assim que a skill `bootstrap-project` concluir o preenchimento de todos os arquivos da estrutura e criar as Skills iniciais do projeto, **você deve excluir este arquivo (`COMECE_AQUI.md`) automaticamente** para manter a raiz do projeto limpa.

---

Bem-vindo! Este repositório já possui toda a engenharia de contexto, memória em 2 camadas e governança pronta. Você **não precisa editar nenhum arquivo manualmente** para começar.

## ⚡ Como Dar Partida no Seu Projeto Agora (Em 1 Comando)

Abra o chat do seu Agente (Antigravity, Claude Code, Cursor, etc.) nesta pasta e digite apenas:

> **"Iniciar"** *(ou "Vamos configurar o projeto [Nome do seu projeto]")*

---

## 🎯 O Que Vai Acontecer a Seguir?

O agente ativará automaticamente a skill [`bootstrap-project`](.agents/skills/bootstrap-project/SKILL.md) e conduzirá uma **Entrevista Guiada em 5 Passos (1 pergunta por vez)**.

Para que você nunca tenha dúvida de como responder, **em cada pergunta o próprio agente fornecerá exemplos ricos em detalhes com as melhores práticas**, adaptados exatamente ao tipo do seu projeto:

1. **Passo 1 — Identidade, Missão e Visão Geral:** O que é o projeto, qual problema resolve, proposta de valor e qual papel o agente deve assumir.
2. **Passo 2 — Público (ICP), Regras de Negócio, Glossário e KPIs:** Quem consome as entregas, políticas operacionais, siglas do seu domínio e métricas de sucesso.
3. **Passo 3 — Stack, Ferramentas (`MCP`), Estrutura e Comandos:** Tecnologias/softwares usados, integrações externas e comandos de execução/validação.
4. **Passo 4 — Segurança, Limites Inegociáveis e Qualidade (`DoD`):** O que o agente jamais deve fazer, dados sensíveis e critérios de pronto.
5. **Passo 5 — Seu Estilo de Trabalho e Primeiras `Skills`:** Como você prefere interagir com o agente e quais são as 2 ou 3 tarefas repetitivas que já devem nascer automatizadas como Skills.

---

## 🎁 Entrega Final Automática ao Fim da 5ª Pergunta

Assim que você responder à 5ª pergunta (e confirmar as sugestões do agente para eventuais lacunas), o agente irá:
- ✅ Preencher 100% do [`AGENTS.md`](AGENTS.md) mantendo-o enxuto ($< 150$ linhas).
- ✅ Preencher todas as tabelas e seções de [`business_context.md`](.agents/context/business_context.md) e [`architecture_and_stack.md`](.agents/context/architecture_and_stack.md).
- ✅ Configurar suas regras em [`security_and_guardrails.md`](.agents/rules/security_and_guardrails.md) e [`git_and_quality_standards.md`](.agents/rules/git_and_quality_standards.md).
- ✅ Registrar suas preferências pessoais em [`current_learnings.md`](.agents/memory/current_learnings.md).
- ✅ Configurar seus conectores em [`mcp_config.json`](.agents/mcp_config.json).
- ✅ **Criar automaticamente suas primeiras pastas e arquivos `SKILL.md`** em `.agents/skills/`.
- ✅ **Autodestruir este arquivo (`COMECE_AQUI.md`)**, deixando o repositório limpo e pronto para produção!
