<!-- LEARNINGS.md | Atualizado em: 08-11-2026 21:50:21(GMT-04:00) -->
# 💡 Aprendizados Técnicos e Lições Aprendidas Consolidadas

**Data/Hora de Geração:** `08-11-2026 21:50:21(GMT-04:00)` | **Fuso Horário:** America/Cuiaba `(GMT-04:00)`

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
- **Aprendizado:** [KIT] Regra da Cerca Elétrica (3-Tier Isolation): Agentes nunca devem editar ou commitar diretamente no repositório de sessão (.vitalia/memory/session/); toda mutação e push de shards/dashboard deve ocorrer exclusivamente via vitalia_context_engine.py acionado nos fluxos de session-end e session-consolidate.
  - **Racional:** Evita corrupção de shards entre múltiplas máquinas (ex: wsl2 vs andrenote) e garante que a consolidação respeite o schema determinístico de aprendizados e decisões.
  - **Origem:** `srv_master` | **Data:** 07-11-2026 21:38:04(GMT-04:00)
- **Aprendizado:** [KIT] Separação estrita entre código-fonte (source/ no repositório raiz) e kit instalado na máquina hospedeira (~/.vitalia-spec-kit por padrão via VITALIA_KIT_DIR).
  - **Racional:** Evita divergência entre o artefato versionado no Git e o runtime global invocado pelas skills da IDE.
  - **Origem:** `srv_master` | **Data:** 07-11-2026 21:38:04(GMT-04:00)
- **Aprendizado:** [KIT] Lentes de Fase Sem Poda (no_prune: true em gp_*.yaml): Em modelos de fronteira (1M+ tokens), podar a constituição por fase enfraquece a governança; o perfil gp_*.yaml deve injetar 100% da constituição e adicionar phase_guardrails específicos da etapa.
  - **Racional:** Elimina perda de princípios transversais (como P03, P05 e P11) durante fases intermediárias do ciclo SDD.
  - **Origem:** `srv_master` | **Data:** 07-11-2026 21:38:04(GMT-04:00)
- **Aprendizado:** [KIT] Proibição de Asserções Sintáticas Rasas (P05): Testes baseados apenas em assert path.is_file() ou regex em arquivos estáticos mascaram bugs de runtime (ex: colisão de stderr em subshell e deadlock de prompt interativo em WSL2/zsh).
  - **Racional:** Força a execução comportamental real via subprocess.run em tmp_path e exige Cenário de Falsificação explícito em tasks.md.
  - **Origem:** `srv_master` | **Data:** 07-11-2026 21:38:04(GMT-04:00)
- **Aprendizado:** Testes de bootstrap em ambientes sem venv devem capturar ausência de python3-venv via subshell e ejetar com código de saída 1 e instrução clara de remediação (sudo apt install python3-venv).
  - **Racional:** Evita rastros de erro crípticos do interpretador e orienta o usuário no primeiro contato.
  - **Origem:** `srv_master` | **Data:** 08-11-2026 21:48:52(GMT-04:00)
- **Aprendizado:** O gerador de skills (skill_generator.sh) deve isolar manifestos e backups em .vitalia/backups/skills/ e .vitalia/.vitalia-manifest, mantendo o diretório .agents/skills/ estritamente puro.
  - **Racional:** IDEs agênticas analisam .agents/skills/ e quebram ou falham na descoberta caso existam pastas como .trash/ ou arquivos .vitalia-manifest.
  - **Origem:** `srv_master` | **Data:** 08-11-2026 21:48:52(GMT-04:00)
- **Aprendizado:** Em arquiteturas 3-Tier de contexto distribuído, a ordenação de shards deve priorizar o campo last_sync em ordem decrescente (com fallback para created_at).
  - **Racional:** Assegura que a versão mais recentemente sincronizada seja utilizada como âncora principal no dashboard.
  - **Origem:** `srv_master` | **Data:** 08-11-2026 21:48:52(GMT-04:00)
- **Aprendizado:** Envelopes de context lifting e schemas OpenAPI 3.0 devem sincronizar propriedades aninhadas mandatárias (como prompt replicado no topo e dentro de guardian).
  - **Racional:** Atende compiladores rígidos de schema JSON e consumidores REST simultaneamente.
  - **Origem:** `srv_master` | **Data:** 08-11-2026 21:48:52(GMT-04:00)

## PROJETO
- **Aprendizado:** [PROJETO] Governança Scaffold Puro e Convenção Sequencial: Estrutura specs/<NNN>-<slug>/ com 3 dígitos zero-padded e scaffold direto de source/ para ~/.vitalia/ garante reprodutibilidade e modularidade.
  - **Racional:** Evita sobreposições e mantém a integridade de repositórios locais do kit.
  - **Origem:** `ai-control` | **Data:** 03-11-2026 05:47:37(GMT-04:00)
- **Aprendizado:** [PROJETO] Calibração de Grounding (grounding_domains.yaml) com a stack real dos projetos assistidos (ex: ai-control com Django 6.1 ASGI/Daphne, Next.js 16.4, React 19.2, pgvector HNSW, django-crypto-fields e Gemini 3.x + Ollama).
  - **Racional:** Garante que o detector de domínios (domain_detector.py) acione P03 e o sub-agente vitalia-research com triggers condizentes com a maturidade tecnológica dos sistemas reais.
  - **Origem:** `srv_master` | **Data:** 07-11-2026 21:38:04(GMT-04:00)
- **Aprendizado:** Isolamento de ambiente de desenvolvimento preservando ~/.vitalia congelado e simulando testes de máquina limpa via tmp_path e diretórios parametrizados.
  - **Racional:** Garante reprodutibilidade e blindagem contra poluição de ambientes globais.
  - **Origem:** `srv_master` | **Data:** 08-11-2026 21:48:52(GMT-04:00)

## GOVERNANCA
- **Aprendizado:** [GOVERNANCA] Specs Corretivas vs Imutabilidade de Entregas: Specs concluídas e comitadas são artefatos imutáveis. Erros e lacunas pós-entrega não devem ser maquiados como 'hardening' nem anexados à spec antiga; exigem abertura de spec corretiva sequencial formal (fix-*) com Root Cause Analysis transparente.
  - **Racional:** Garante rastreabilidade histórica íntegra e maturidade de engenharia sem falsear o escopo do que foi entregue.
  - **Origem:** `ai-control` | **Data:** 06-11-2026 13:16:00(GMT-04:00)
