---
name: bootstrap-project
description: >-
  Inicializa e padroniza 100% da arquitetura do agente através de uma Entrevista
  Guiada em 5 Passos (1 pergunta por vez com exemplos ricos de resposta),
  preenchendo todos os arquivos da estrutura epic-tesla, criando as primeiras
  Skills do projeto e removendo o arquivo temporário COMECE_AQUI.md ao concluir.
---

# Skill: Onboarding Guiado e Padronização Total (`bootstrap-project`)

Esta skill é o ponto de partida (`COMECE AQUI`) de qualquer novo projeto estruturado com o template `epic-tesla`. Sua missão é conduzir o usuário por **5 perguntas estratégicas (1 de cada vez)**, fornecendo exemplos ricos de como responder a cada uma, e usar as respostas para preencher **100% dos arquivos da arquitetura** sem deixar nenhum campo pendente.

---

## Regras de Ouro da Condução da Entrevista

1. **Estritamente 1 Pergunta por Vez:** Nunca envie todas as 5 perguntas juntas. Envie o **Passo 1**, aguarde a resposta do usuário, processe o contexto e só então envie o **Passo 2**, até completar o **Passo 5**.
2. **Adaptação Dinâmica dos Exemplos (A partir do Passo 2):**
   - No **Passo 1**, apresente dois exemplos ricos (um de *Engenharia de Software/Código* e outro de *Operações/Negócios/Automação*).
   - Nos **Passos 2 a 5**, adapte os exemplos ricos usando o **próprio nome e nicho do projeto** que o usuário acabou de informar no Passo 1!
3. **Destravamento Cognitivo em Toda Pergunta:** Sempre encerre cada pergunta com o lembrete:
   > *"💡 **Dica:** Você pode responder com suas próprias palavras ou copiar a estrutura do exemplo acima. Se ainda não tiver definido algum ponto, basta dizer **'sugira o padrão recomendado'** que eu preencho com as melhores práticas de mercado para o seu projeto."*
4. **Caso Especial (Briefing Já Enviado):** Se o usuário já colou um briefing extenso na primeira mensagem, extraia tudo o que já foi respondido, mostre o que entendeu e faça **apenas as perguntas dos passos que ficaram faltando**, mantendo os exemplos ricos.

---

## Fase 1: As 5 Perguntas da Entrevista Guiada

### Passo 1 de 5: Identidade, Missão e Visão Geral do Projeto
*(Alimenta: `AGENTS.md` Seção 2 e `business_context.md` Seção 1)*

Apresente ao usuário a pergunta cobrindo os 5 subitens abaixo, acompanhada dos exemplos ricos:
1. **Nome do Projeto e Natureza:** (É um projeto de Software/Código, Automação/Operações, Comercial ou Híbrido?)
2. **Papel do Agente (Role):** Qual cargo/especialidade de elite eu devo assumir?
3. **Problema Central e Proposta de Valor:** Qual dor este projeto resolve e qual é o diferencial da solução?
4. **Modelo de Operação/Receita:** (Ex: SaaS B2B, Produto Interno, Agência, E-commerce, Backoffice).
5. **Objetivo Final Mensurável (Estado Desejado):** O que define que nosso trabalho neste projeto é um sucesso?

> **📌 Exemplo Rico A (Projeto de Software — "Genesis"):**
> - **Nome e Natureza:** Projeto *Genesis* (Software / API Backend e Dashboard).
> - **Papel do Agente:** Arquiteto de Software e Engenheiro Fullstack Sênior (Node.js/TypeScript).
> - **Problema e Proposta de Valor:** Escritórios contábeis perdem 15h/semana conciliando extratos bancários manualmente. O Genesis automatiza a conciliação cruzando OFX/PIX com notas fiscais em segundos.
> - **Modelo de Operação:** Micro-SaaS B2B por assinatura mensal.
> - **Objetivo Final:** Construir e manter o MVP em produção capaz de processar 10.000 transações/minuto com precisão de 99,9% e zero divergências de centavos.
>
> **📌 Exemplo Rico B (Projeto de Operações/Comercial — "Atlas Growth"):**
> - **Nome e Natureza:** Projeto *Atlas Growth* (Operação Comercial e Automação de Vendas).
> - **Papel do Agente:** Especialista Sênior em Sales Ops, Copywriting B2B e Inteligência Comercial.
> - **Problema e Proposta de Valor:** Consultorias de TI têm dificuldade em qualificar leads enterprise e demoram 4 dias para enviar propostas. O Atlas qualifica leads em 5 minutos e gera propostas personalizadas de alta conversão.
> - **Modelo de Operação:** Operação interna de Growth e Vendas High-Ticket.
> - **Objetivo Final:** Reduzir o tempo de geração de propostas para menos de 15 minutos e elevar a taxa de conversão de reuniões de 18% para 35%.

---

### Passo 2 de 5: Público-Alvo (ICP), Regras de Negócio, Glossário e KPIs
*(Alimenta: `business_context.md` Seções 2, 3, 4 e 5)*

Após receber a resposta do Passo 1, apresente o Passo 2 adaptando os exemplos ao projeto do usuário e solicitando:
1. **Perfil de Público/Personas (ICP):** Quem usa ou compra, qual a dor principal, o que considera ganho e quais suas objeções/restrições comuns?
2. **Regras de Negócio e Políticas Operacionais:** Condições comerciais/preços, critérios de priorização e políticas que nunca devem ser quebradas.
3. **Glossário e Siglas do Domínio:** Termos internos, siglas de negócio ou jargões específicos do projeto.
4. **Métricas de Sucesso (KPIs do Agente):** Quais indicadores mostram que minhas entregas estão excelentes?

> **📌 Exemplo Rico de Melhor Prática (Adapte ao projeto do usuário):**
> - **Personas (ICP):**
>   1. *Contador Sênior (Operador)*: Dor = medo de erro fiscal; Ganho = fechar o mês em 1 dia; Objeção = desconfiança em automação caixa-preta.
>   2. *Sócio do Escritório (Decisor)*: Dor = folha salarial alta; Ganho = atender o dobro de clientes com a mesma equipe; Objeção = custo de implantação.
> - **Regras de Negócio:** Qualquer divergência financeira acima de R$ 0,05 não pode ser aprovada automaticamente (deve ir para fila de revisão humana). Leads ou clientes do plano Enterprise têm SLA prioritário.
> - **Glossário Interno:** ` Conciliação D+1` = batimento do extrato do dia anterior; `Divergência Crítica` = lançamento sem CNPJ identificado; `NFSe` = Nota Fiscal de Serviço Eletrônica.
> - **KPIs do Agente:** Cobertura de testes > 85% nas regras fiscais, tempo de resposta de queries < 200ms e zero bugs de arredondamento monetário.

---

### Passo 3 de 5: Stack Tecnológica, Ferramentas (`MCP`), Estrutura e Comandos
*(Alimenta: `architecture_and_stack.md` Completo e `.agents/mcp_config.json`)*

Solicite ao usuário os detalhes do ecossistema técnico/operacional (ou inspecione os arquivos existentes na pasta caso já haja código):
1. **Stack Core / Softwares Utilizados:** Linguagens, frameworks, bancos de dados (ou ferramentas como Notion, Gmail, Google Sheets, CRM).
2. **Integrações Externas (`MCP` / APIs):** Quais serviços externos o agente deve consultar ou operar via MCP?
3. **Estrutura de Diretórios:** Como as pastas do projeto estão (ou devem ser) organizadas?
4. **Comandos Canônicos e Rotinas:** Comandos de instalação (`setup`), desenvolvimento (`dev`), testes (`test`) e entrega (`build/deploy`).

> **📌 Exemplo Rico de Melhor Prática (Adapte ao projeto do usuário):**
> - **Stack Core:** Node.js 22, TypeScript 5, Fastify (API), Prisma ORM, PostgreSQL 16 e Redis para filas.
> - **Integrações e MCP:** Servidor MCP do PostgreSQL (somente leitura para diagnóstico), MCP do GitHub para gestão de PRs e API da Asaas/Stripe.
> - **Estrutura de Pastas:** Monorepo ou `src/modules/` (arquitetura modular por domínio: `auth`, `reconciliation`, `billing`), `tests/` e `prisma/`.
> - **Comandos Canônicos:** Setup: `npm install && npx prisma generate` | Dev: `npm run dev` | Testes: `npm run test:unit` | Build: `npm run build`.

---

### Passo 4 de 5: Segurança, Guardrails de Domínio e Padrão de Qualidade (`DoD`)
*(Alimenta: `security_and_guardrails.md` Seção 4 e `git_and_quality_standards.md` Seções 1, 3 e 4)*

Solicite os limites inegociáveis e critérios de qualidade:
1. **Restrições Específicas de Segurança e Privacidade:** Dados regulados (LGPD, PII, dados bancários) e ações que exigem aprovação humana explícita.
2. **Convenções Técnicas / Padrões de Código ou Entrega:** Regras de estilo, arquitetura ou formatação obrigatórias (ex: proibido usar `any`, usar sempre valores em centavos `integer` para dinheiro, padrão de idioma de código).
3. **Critério de Pronto (`Definition of Done - DoD`):** O que é obrigatório validar antes de você considerar qualquer tarefa concluída?

> **📌 Exemplo Rico de Melhor Prática (Adapte ao projeto do usuário):**
> - **Segurança e Guardrails:** Nunca exibir CPF/CNPJ ou tokens bancários reais em logs. Jamais rodar migrations destrutivas (`prisma migrate reset`) sem confirmação.
> - **Convenções do Projeto:** Valores monetários devem ser armazenados estritamente em centavos (`Int` / `BigInt`), nunca em `Float`. Código e variáveis em inglês; documentação e respostas em Português (PT-BR). Proibido uso de `any` no TypeScript.
> - **Critério de Pronto (DoD):** Código compilando sem erros de lint/typecheck, teste unitário criado para a regra de negócio alterada e documentação atualizada.

---

### Passo 5 de 5: Estilo Pessoal do Operador e Primeiras `Skills` do Projeto
*(Alimenta: `AGENTS.md` Seção 3, `current_learnings.md` Seção 1 e cria as primeiras Skills em `.agents/skills/`)*

Solicite os ajustes finais de parceria humano-agente:
1. **Suas Preferências Pessoais de Interação e Comunicação:** Como você gosta que eu trabalhe com você? (Ex: mostrar plano antes de editar vários arquivos, respostas diretas em bullet points, nível de autonomia).
2. **Mapeamento das Primeiras `Skills` (2 a 3 rotinas repetitivas):** Quais são os fluxos de trabalho ou tarefas mais frequentes neste projeto que eu já devo deixar criados como **Skills prontas** agora mesmo?

> **📌 Exemplo Rico de Melhor Prática (Adapte ao projeto do usuário):**
> - **Preferências do Operador:** Sempre que uma mudança afetar mais de 3 arquivos ou o schema do banco, me mostre um mini-plano em 5 linhas antes de executar. Prefiro respostas diretas, sem textos longos de introdução, sempre com links clicáveis para os arquivos alterados.
> - **Primeiras Skills para Criar Agora:**
>   1. `criar-endpoint-api`: Padroniza a criação de novas rotas Fastify com validação Zod, service, controller e teste unitário.
>   2. `auditar-conciliacao`: Analisa um lote de transações divergentes e gera um relatório diagnóstico da causa raiz.

---

## Fase 2: Inferência de Lacunas e Validação Pré-Gravação

Assim que o usuário responder ao **Passo 5**:
1. **Audite as Informações Coletadas:** Verifique se há dados suficientes para preencher **todas as seções e tabelas** de:
   - [`AGENTS.md`](../../../AGENTS.md)
   - [`.agents/context/business_context.md`](../../context/business_context.md)
   - [`.agents/context/architecture_and_stack.md`](../../context/architecture_and_stack.md)
   - [`.agents/rules/security_and_guardrails.md`](../../rules/security_and_guardrails.md)
   - [`.agents/rules/git_and_quality_standards.md`](../../rules/git_and_quality_standards.md)
   - [`.agents/memory/current_learnings.md`](../../memory/current_learnings.md)
   - [`.agents/mcp_config.json`](../../mcp_config.json)
2. **Preenchimento Inteligente de Lacunas:** Se o usuário deu respostas curtas ou deixou algum campo em aberto (ex: não citou siglas para o glossário, não definiu KPIs ou comandos), **infira e elabore sugestões de altíssimo nível** compatíveis com o mercado e a stack do projeto.
3. **Confirmação Rápida:** Apresente um resumo estruturado das definições (destacando o que você inferiu/completou para ele e listando as Skills iniciais que serão geradas) e pergunte:
   > *"Revise o resumo acima. Posso confirmar e gravar toda a estrutura do projeto e criar suas primeiras Skills?"*

---

## Fase 3: Gravação Total, Geração de Skills e Autodestruição do `COMECE_AQUI.md`

Após o *"De acordo"* do usuário, execute em sequência atômica:

1. **Padronizar [`AGENTS.md`](../../../AGENTS.md):**
   - Remova o bloco superior `> **[DIRETRIZ DE AUTO-PADRONIZAÇÃO E GATILHO DE ONBOARDING PARA A IA]**`.
   - Preencha a seção **2. Identidade e Missão do Projeto** e ajuste a seção **3. Diretrizes de Tom, Postura e Comunicação**.
   - **Limite Rígido:** Garanta que o `AGENTS.md` final tenha **menos de 150 linhas**.

2. **Padronizar [`.agents/context/business_context.md`](../../context/business_context.md):**
   - Remova o bloco de instrução de onboarding e preencha 100% das seções: Visão Geral, Tabela de Personas (ICP), Regras de Negócio, Tabela de Glossário/Siglas e KPIs do Agente.

3. **Padronizar [`.agents/context/architecture_and_stack.md`](../../context/architecture_and_stack.md):**
   - Remova o bloco de instrução de onboarding e preencha 100% das seções: Tabela de Stack/Ferramentas, Árvore de Diretórios real/planejada, Comandos Canônicos e Estratégia de Roteamento de Modelos.

4. **Padronizar [`.agents/rules/security_and_guardrails.md`](../../rules/security_and_guardrails.md) e [`.agents/rules/git_and_quality_standards.md`](../../rules/git_and_quality_standards.md):**
   - Preencha as restrições específicas do domínio, o DoD customizado e as convenções técnicas consolidadas na Seção 4.

5. **Inicializar [`.agents/memory/current_learnings.md`](../../memory/current_learnings.md):**
   - Registre com a data atual (`[AAAA-MM-DD]`) todas as preferências de interação do operador e regras críticas iniciais informadas durante a entrevista.

6. **Configurar [`.agents/mcp_config.json`](../../mcp_config.json):**
   - Configure os servidores MCP reais que o projeto utilizará (ou limpe os exemplos genéricos caso o projeto não utilize MCP inicialmente).

7. **Criar Automaticamente as Primeiras Skills do Projeto (`.agents/skills/<nome-da-skill>/SKILL.md`):**
   - Seguindo o padrão de [`create-skill`](../create-skill/SKILL.md) e [`skill_template.md`](../create-skill/resources/skill_template.md), crie as pastas e os arquivos `SKILL.md` completos (com YAML frontmatter `name` e `description`, insumos, passo a passo detalhado e DoD) para as rotinas mapeadas no Passo 5.

8. **Autodestruir o Arquivo [`COMECE_AQUI.md`](../../../COMECE_AQUI.md):**
   - Exclua o arquivo `COMECE_AQUI.md` da raiz do repositório para encerrar oficialmente o Modo de Onboarding.

---

## Checklist Obrigatório de Validação Final (DoD do Bootstrap)
Antes de entregar a mensagem final de conclusão ao usuário, verifique:
- [ ] **Zero Placeholders:** Nenhum arquivo em todo o projeto contém o texto `[PENDENTE`.
- [ ] **Teto de Contexto:** `AGENTS.md` possui menos de 150 linhas e `current_learnings.md` possui menos de 100 linhas.
- [ ] **Novas Skills Criadas:** As pastas e arquivos `SKILL.md` específicos do projeto existem em `.agents/skills/`.
- [ ] **Limpeza Concluída:** O arquivo `COMECE_AQUI.md` foi removido da raiz.
