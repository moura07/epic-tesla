# Agent Boilerplate — Arquitetura Padrão para Agentes Autônomos de IA

[![GitHub Repo](https://img.shields.io/badge/GitHub-moura07%2Fepic--tesla-blue?logo=github)](https://github.com/moura07/epic-tesla.git)
[![Architecture](https://img.shields.io/badge/Architecture-Autonomous_Agent_Loop-success)](#arquitetura-do-ecossistema-em-5-niveis)
[![Protocol](https://img.shields.io/badge/Protocol-MCP_%26_Progressive_Disclosure-orange)](#as-3-meta-skills-inclusas)
[![Open Source](https://img.shields.io/badge/Community-Open_Collaboration-blueviolet)](#colaboracao-e-evolucao-continua)

Estrutura base corporativa para governança e engenharia de contexto de **Agentes de IA Autônomos**. Projetada para eliminar a amnésia entre sessões, prevenir a sobrecarga da janela de contexto (*context rot* e *lost-in-the-middle*) e desacoplar o manual de conduta do agente da interface de execução.

Compatível com os principais ecossistemas e plataformas do mercado: **Google Antigravity**, **Claude Code**, **Hermes**, **Cursor**, terminais interativos e pipelines headless integrados via MCP.

---

## Fundamentos e Proposta de Valor

A maioria das implementações com modelos de linguagem falha ao tentar escalar tarefas do mundo real por quatro motivos principais:

1. **Tratamento Reativo (Chatbot vs. Agente):** Dependência de prompts pontuais e dispersos, nos quais o operador humano precisa validar e planejar cada passo, assumindo toda a carga cognitiva.
2. **Amnésia Intersessão:** LLMs operam em ambientes efêmeros. Correções realizadas ao longo do dia são descartadas ao fechar a janela, exigindo reensinar diretrizes a cada novo chat.
3. **Sobrecarga de Atenção:** Manuais com centenas de linhas na raiz do projeto saturam a janela de contexto com ruído informacional, degradando o raciocínio lógico e induzindo alucinações.
4. **Acoplamento à Ferramenta:** Regras de negócio aprisionadas dentro de configurações de uma plataforma específica, dificultando a portabilidade entre modelos e ambientes de desenvolvimento.

Este repositório soluciona essas deficiências ao transformar a IA em um **agente teleológico (orientado a objetivos)** através de:
- **Separação entre Chassi e Motor:** Arquitetura desacoplada baseada em Markdown, permitindo alternar livremente entre harnesses e modelos de inferência.
- **Memória em Duas Camadas:** Leitura mandatória de aprendizados ativos no boot e compactação periódica com histórico arquivado.
- **Divulgação Progressiva (*Progressive Disclosure*):** Procedimentos operacionais extensos (*Skills*) carregados sob demanda via metadados, mantendo a janela de contexto limpa e rápida.

---

## Arquitetura do Ecossistema em 5 Níveis

```mermaid
flowchart TD
    subgraph L1 ["1. Harness & Runtime"]
        Harness["Antigravity / Claude Code / Hermes / Cursor"]
    end

    subgraph L2 ["2. Constituicao & Contexto Estavel"]
        Agents["AGENTS.md (Boot & Limites: < 150 linhas)"]
        Context["Contexto Sob Demanda (.agents/context/)"]
        Rules["Regras Modulares (.agents/rules/)"]
    end

    subgraph L3 ["3. Memoria Persistente & Autoevolucao"]
        MemAtiva["Memoria Ativa: current_learnings.md (< 100 linhas)"]
        MemArchive["Memoria Historica: archive.md"]
        Compaction["Compactacao Periodica: compact-memory"]
    end

    subgraph L4 ["4. Acao no Mundo Real"]
        Skills["Skills sob Demanda (.agents/skills/*)"]
        MCP["Model Context Protocol (mcp_config.json)"]
    end

    subgraph L5 ["5. Roteamento Economico"]
        HighLLM["Sessao/Codigo: Modelos de Fronteira (Sonnet / GPT / Argon)"]
        LowLLM["Background/Cron 24/7: Modelos Abertos (DeepSeek / Qwen / NemoTron)"]
    end

    L1 --> L2
    L2 --> L3
    L3 --> L4
    L4 --> L5
```

---

## Estrutura de Diretórios

```text
.
├── COMECE_AQUI.md                             # Guia inicial interativo (autodestruido apos o onboarding)
├── AGENTS.md                                  # Constituicao mestra do Agente (< 150 linhas)
├── README.md                                  # Documentacao arquitetural e operacional
└── .agents/                                   # Governanca centralizada do Agente
    ├── mcp_config.json                        # Conectores com servicos externos via MCP
    ├── context/                               # Bases de conhecimento de apoio (consultadas sob demanda)
    │   ├── business_context.md                # Regras de negocio, ICP/Personas, glossario e KPIs
    │   └── architecture_and_stack.md          # Stack tecnica, arvore de arquivos e comandos canonicos
    ├── rules/                                 # Regras inegociaveis e padroes de conformidade
    │   ├── security_and_guardrails.md         # Prevencao de acoes destrutivas, dados sensiveis e guardrails
    │   └── git_and_quality_standards.md       # Definition of Done (DoD), limites e padrao de commits
    ├── memory/                                # Sistema de Persistencia em Duas Camadas
    │   ├── current_learnings.md               # Caderno ativo de licoes aprendidas (lido no boot)
    │   └── archive.md                         # Log consolidado de licoes promovidas para regras
    └── skills/                                # Procedimentos Operacionais Padronizados (SOPs)
        ├── bootstrap-project/                 # Onboarding guiado em 5 passos e auto-padronizacao
        │   └── SKILL.md
        ├── create-skill/                      # Fabrica de Skills: encapsula fluxos validados
        │   ├── SKILL.md
        │   └── resources/
        │       └── skill_template.md
        └── compact-memory/                    # Higienizador de memoria: poda sem perda de contexto
            └── SKILL.md
```

---

## Como Inicializar um Novo Projeto

### 1. Clonar o Repositório

```bash
git clone https://github.com/moura07/epic-tesla.git meu-novo-projeto
cd meu-novo-projeto

# Inicialize um historico limpo para o seu projeto
rm -rf .git
git init
```

### 2. Abrir no Harness ou Editor de Preferência

Abra a pasta no Antigravity, Claude Code, Cursor ou ambiente de terminal integrado.

### 3. Disparar o Onboarding Guiado

Com o gatilho automático configurado no `AGENTS.md`, envie no chat:

> **"Iniciar"** *(ou "Vamos configurar o projeto [Nome do Projeto]")*

#### Etapas da Configuração Automática:
1. **Entrevista Guiada em 5 Passos (1 pergunta por vez):** O agente conduz perguntas sequenciais cobrindo objetivo, negócio, ferramentas, segurança e primeiras rotinas. Em cada etapa, apresenta exemplos práticos detalhados, adaptados ao nicho do projeto.
2. **Preenchimento Inteligente de Lacunas:** Se houver respostas parciais, o agente infere os padrões recomendados de mercado e exibe um resumo para validação antes de salvar.
3. **Padronização Integral e Limpeza:** Após confirmação, todos os arquivos de contexto, regras e memória são preenchidos, as primeiras Skills são criadas em `.agents/skills/` e o arquivo temporário `COMECE_AQUI.md` é removido automaticamente.

---

## As 3 Meta-Skills Inclusas

| Meta-Skill | Finalidade | Mecanismo de Ação |
| :--- | :--- | :--- |
| **`bootstrap-project`** | Configuração inicial ao iniciar novos projetos. | Mapeia contexto estruturado e preenche os arquivos base sem ultrapassar os limites de linhas. |
| **`create-skill`** | Modularização de rotinas bem-sucedidas. | Converte fluxos consolidados em pacotes reutilizáveis em `.agents/skills/<nome>/` com frontmatter YAML e DoD. |
| **`compact-memory`** | Higienização da memória ativa. | Transfere aprendizados estáveis de `current_learnings.md` para as regras permanentes e move o histórico para `archive.md`. |

---

## Ciclo de Autoevolução e Acúmulo de Contexto

```text
       [Operador corrige a IA no chat]
                     │
                     ▼
  [IA registra a licao em .agents/memory/current_learnings.md]
                     │
                     ▼
  [A cada nova sessao, a IA relê current_learnings.md]
                     │
                     ▼
  [Ao atingir ~80 linhas, aciona a skill compact-memory]
         ┌───────────┴───────────┐
         ▼                       ▼
[Promove para .agents/rules/]   [Arquiva em archive.md]
```

Esse ciclo contínuo estabelece um **ativo cumulativo proprietário**: ao longo das semanas de uso, o agente refina suas decisões e alinhamento com a equipe sem sofrer lentidão ou dispersão no raciocínio.

---

## Integração com Ferramentas Externas (MCP)

O arquivo [`.agents/mcp_config.json`](./.agents/mcp_config.json) segue a especificação do Model Context Protocol:

```json
{
  "mcpServers": {
    "meu-banco-sqlite": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-sqlite", "./database.db"],
      "env": { "DB_READONLY": "true" }
    },
    "meu-servidor-remoto": {
      "url": "https://mcp.minhaempresa.com/mcp"
    }
  }
}
```

Permite conectar ferramentas locais (`Stdio`) ou serviços remotos (`Streamable HTTP`) para leitura de bancos, envio de e-mails, integração com repositórios e chamadas de APIs externas.

---

## Roteamento de Modelos e Otimização de Custo

Para manter a viabilidade econômica em projetos de alta demanda:

* **Sessão Interativa e Arquitetura:** Modelos de raciocínio avançado (`Claude 3.5 Sonnet`, `Gemini Pro / Argon`, `GPT-4o`) para estruturação, análise de código complexo e criação de novas Skills.
* **Tarefas Contínuas de Background (24/7):** Modelos abertos de alta eficiência (`DeepSeek-V3`, `Qwen 2.5`, `GLM-4`) ou execução local com custo zero de tokens (`NemoTron`, `Ollama`) para crons, triagens e rotinas automatizadas.

---

## Diretrizes de Uso e Boas Práticas

1. **Concisão no `AGENTS.md`:** Manter o arquivo sempre abaixo de 200 linhas (recomendado: até 150 linhas). Regras extensas pertencem a `.agents/rules/` e fluxos detalhados a `.agents/skills/`.
2. **Critério de Validação Obrigatório (DoD):** Toda tarefa deve ser inspecionada na prática antes de ser considerada concluída.
3. **Padrão de Versionamento:** Commits atômicos no formato Conventional Commits (`feat:`, `fix:`, `docs:`, `chore:`).

---

## Colaboração e Evolução Contínua

Este repositório foi concebido como um padrão vivo para a comunidade de engenharia de agentes de IA. Melhorias em regras de governança, novas meta-skills e aprimoramentos nos protocolos de contexto são amplamente bem-vindos.

Sinta-se livre para abrir *issues*, sugerir melhorias estruturais via *pull requests* ou adaptar este modelo para as particularidades do seu time ou empresa.
