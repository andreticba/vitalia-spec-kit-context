<!-- LEARNINGS.md | Atualizado em: 06-11-2026 13:15:31(GMT-04:00) -->
# 💡 Aprendizados Técnicos e Lições Aprendidas Consolidadas

**Data/Hora de Geração:** `06-11-2026 13:15:31(GMT-04:00)` | **Fuso Horário:** America/Cuiaba `(GMT-04:00)`

## KIT
- **Aprendizado:** [KIT] Contratos OpenAPI 3.0 para Google Gemini REST: Schemas JSON validados por compiladores de modelos de fronteira rejeitam meta-campos Draft-07 como $schema, title no nó raiz e additionalProperties: false (gerando HTTP 400). Padrão estrito OpenAPI 3.0 limpo.
  - **Racional:** Previne falhas de compilação de schema via chamadas de API em tempo de execução.
  - **Origem:** `ai-control` | **Data:** 03-11-2026 05:47:37(GMT-04:00)
- **Aprendizado:** [KIT] Sub-Agente Nativo vs CLI Externo: A orquestração do SDD-Judge nativamente na IDE Antigravity elimina a necessidade de fatiamento de 400 tokens de VRAM e previne diluição de regras constitucionais.
  - **Racional:** Janelas de contexto amplas com Sanduíche Constitucional mantêm atenção aos princípios e reduzem alucinações na auditoria.
  - **Origem:** `ai-control` | **Data:** 03-11-2026 05:47:37(GMT-04:00)
- **Aprendizado:** [KIT] Validação E2E Obrigatória em Scripts de Bootstrap: Validar apenas a criação do virtualenv ou diretórios do kit global gera falso positivo nos testes. A suíte de testes do bootstrap deve obrigatoriamente rodar um teste de fumaça de ponta a ponta acionando install-project em um projeto hospedeiro limpo, assegurando que templates, shims e skills cheguem ao destino.
  - **Racional:** Previne que omissões de espelhamento (como integrations/ e AGENTS.md) passem despercebidas nos testes unitários.
  - **Origem:** `ai-control` | **Data:** 06-11-2026 13:16:00(GMT-04:00)

## PROJETO
- **Aprendizado:** [PROJETO] Governança Scaffold Puro e Convenção Sequencial: Estrutura specs/<NNN>-<slug>/ com 3 dígitos zero-padded e scaffold direto de source/ para ~/.vitalia/ garante reprodutibilidade e modularidade.
  - **Racional:** Evita sobreposições e mantém a integridade de repositórios locais do kit.
  - **Origem:** `ai-control` | **Data:** 03-11-2026 05:47:37(GMT-04:00)

## GOVERNANCA
- **Aprendizado:** [GOVERNANCA] Specs Corretivas vs Imutabilidade de Entregas: Specs concluídas e comitadas são artefatos imutáveis. Erros e lacunas pós-entrega não devem ser maquiados como 'hardening' nem anexados à spec antiga; exigem abertura de spec corretiva sequencial formal (fix-*) com Root Cause Analysis transparente.
  - **Racional:** Garante rastreabilidade histórica íntegra e maturidade de engenharia sem falsear o escopo do que foi entregue.
  - **Origem:** `ai-control` | **Data:** 06-11-2026 13:16:00(GMT-04:00)
