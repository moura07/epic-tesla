---
name: compact-memory
description: >-
  Executa a poda, síntese e compactação da memória ativa (.agents/memory/current_learnings.md)
  quando ela se aproxima de 80 a 100 linhas, promovendo aprendizados consolidados
  para regras permanentes (.agents/rules/) e arquivando o histórico em archive.md.
---

# Skill: Compactação e Curadoria de Memória (`compact-memory`)

Esta skill impede o fenômeno de degradação de atenção (*context rot* / *lost-in-the-middle*) mantendo o arquivo `current_learnings.md` enxuto e de alta densidade informacional.

---

## Procedimento de Execução

1. **Auditoria de `current_learnings.md`:**
   - Leia todos os itens registrados em [`.agents/memory/current_learnings.md`](../../memory/current_learnings.md).
   - Classifique cada item em uma das 3 categorias:
     - **A. Regra Permanente Consolidada:** Padrão definitivo de projeto, código ou negócio que nunca muda.
     - **B. Aprendizado Recente em Observação:** Correção recente que ainda precisa permanecer visível no boot diário.
     - **C. Item Obsoleto / Duplicado / Resolvido:** Bug temporário já corrigido na raiz ou instrução superada.

2. **Promoção de Regras (Categoria A):**
   - Transfira os itens da Categoria A de forma sintetizada para:
     - [`.agents/rules/git_and_quality_standards.md`](../../rules/git_and_quality_standards.md) (se for padrão técnico/qualidade)
     - [`.agents/rules/security_and_guardrails.md`](../../rules/security_and_guardrails.md) (se for restrição de segurança/operação)
     - [`.agents/context/business_context.md`](../../context/business_context.md) (se for regra de negócio do domínio)

3. **Arquivamento Histórico (Categorias A e C):**
   - Adicione uma linha na tabela de [`.agents/memory/archive.md`](../../memory/archive.md) registrando a data original, a data de compactação, o resumo da lição e para qual arquivo ela foi promovida.

4. **Limpeza da Memória Ativa:**
   - Reescreva [`.agents/memory/current_learnings.md`](../../memory/current_learnings.md) mantendo apenas os itens da **Categoria B** (aprendizados ativos recentes) e preferências essenciais do operador.
   - O arquivo final deve ficar com **menos de 40 linhas** após a compactação.

---

## Critérios de Validação
- [ ] Nenhum aprendizado valioso foi perdido (todos foram promovidos para `rules/`/`context/` ou registrados em `archive.md`).
- [ ] `current_learnings.md` está abaixo de 40 linhas.
