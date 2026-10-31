---
name: create-skill
description: >-
  Transforma um fluxo de trabalho bem-sucedido, procedimento operacional (SOP)
  ou rotina recorrente em uma nova Skill modularizada dentro de .agents/skills/.
  Use esta skill quando o usuário pedir para salvar um processo como Skill ou
  para padronizar uma rotina repetitiva.
---

# Skill: Criador de Skills Modulares (`create-skill`)

Esta skill encapsula qualquer processo validado em uma nova Skill reutilizável seguindo o padrão de **Divulgação Progressiva (*Progressive Disclosure*)**.

---

## Procedimento de Execução

1. **Definir o Identificador (`name`):**
   - Escolha um nome curto em `kebab-case` (letras minúsculas separadas por hífen, ex: `prospectar-leads`, `auditar-pr`, `gerar-relatorio-semanal`).

2. **Redigir a Descrição de Ativação (`description`):**
   - No YAML frontmatter, escreva em terceira pessoa **o que** a skill faz e **quando** o agente deve acioná-la.
   - *Importante:* Como o agente carrega apenas o `name` e `description` na janela inicial, a descrição deve conter as palavras-chave exatas que ativam o procedimento.

3. **Estruturar a Pasta da Nova Skill:**
   - Crie o diretório `.agents/skills/<nome-da-skill>/`.
   - Utilize o modelo base em [`resources/skill_template.md`](resources/skill_template.md) para criar o arquivo `.agents/skills/<nome-da-skill>/SKILL.md`.
   - Se a skill envolver templates longos, exemplos extensos ou scripts, coloque-os em subpastas (`resources/`, `examples/`, `scripts/`) e referencie-os por links relativos no `SKILL.md`.

4. **Validar a Nova Skill:**
   - [ ] O arquivo `SKILL.md` inicia exatamente com o bloco YAML `---` contendo `name` e `description`?
   - [ ] As etapas são determinísticas, numeradas e acionáveis sem depender do histórico do chat anterior?
   - [ ] Há uma seção clara de **Critérios de Validação (DoD)** no final?
