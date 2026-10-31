# Padrões de Qualidade, Versionamento e Higiene (`git_and_quality_standards.md`)

> **[INSTRUÇÃO DE PADRONIZAÇÃO PARA A IA]:**
> Aplique estes padrões em todas as entregas do projeto. Novas regras permanentes promovidas a partir de `.agents/memory/current_learnings.md` durante a compactação de memória devem ser adicionadas de forma enxuta na seção **4. Convenções Consolidadas do Projeto**.

---

## 1. Critério de Pronto (Definition of Done - DoD)
Nenhuma tarefa é considerada concluída até que:
1. O resultado tenha sido verificado na prática (testes executados, arquivo conferido, sintaxe validada).
2. Nenhum arquivo temporário ou rascunho de debug tenha sido deixado solto na raiz do projeto.
3. A documentação afetada (ou memória ativa, se houve correção) tenha sido atualizada.

---

## 2. Higiene da Arquitetura do Agente
- **Preservação do Teto de Contexto:**
  - `AGENTS.md`: Máximo de **150 a 200 linhas**.
  - `.agents/memory/current_learnings.md`: Máximo de **100 linhas**.
- **Divulgação Progressiva (*Progressive Disclosure*):** Todo fluxo operacional recorrente com mais de 15 linhas de instruções passo a passo deve ser extraído para uma Skill própria dentro de `.agents/skills/<nome-da-skill>/SKILL.md`.
- **Preservação de Comentários e Documentação:** Nunca remova comentários úteis, docstrings ou regras existentes em arquivos que você estiver editando, a menos que estejam comprovadamente obsoletos.

---

## 3. Padrões de Versionamento (Git)
- **Commits Atômicos e Semânticos:** Utilize o padrão *Conventional Commits*:
  - `feat:` nova funcionalidade ou nova Skill/integração.
  - `fix:` correção de bug ou ajuste de regra quebrada.
  - `docs:` atualização de contexto, README ou documentação.
  - `chore:` manutenção de estrutura, compactação de memória (`compact-memory`) ou configuração.
- **Verificação Pré-Commit:** Sempre execute `git status` e `git diff` antes de criar um commit para garantir que nenhum arquivo sensível (`.env`, credenciais) está sendo incluído.

---

## 4. Convenções Consolidadas do Projeto (Promovidas da Memória)
- `[Espaço reservado para regras permanentes promovidas automaticamente pela skill compact-memory]`
