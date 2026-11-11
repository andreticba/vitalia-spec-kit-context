<!-- LEARNINGS.md | Vitalia SPEC Kit v0.0.1 | 11-11-2026 11:04:06(GMT-04:00) -->
> **LEARNINGS.md | Vitalia SPEC Kit v0.0.1 | 11-11-2026 11:04:06(GMT-04:00)**

# 💡 Aprendizados Técnicos e Lições Aprendidas Consolidadas

**Data/Hora de Geração:** `11-11-2026 11:04:06(GMT-04:00)` | **Fuso Horário:** America/Cuiaba `(GMT-04:00)`

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
- **Aprendizado:** [KIT] Sub-Agent Dispatch Engine no Architect via Catálogo: O Arquiteto não deve acoplar tipos de especialistas estaticamente em seu prompt; deve resolver dinamicamente via agents_catalog.yaml em runtime (padrão vitalia-route), permitindo adicionar novos especialistas sem alterar o contrato do workflow.
  - **Racional:** Garante extensibilidade zero-touch e preserva o Princípio do Contexto Delimitado (Bounded Context) sem inflar a sessão principal com ferramentas desnecessárias.
  - **Origem:** `srv_master` | **Data:** 09-11-2026 23:28:42(GMT-04:00)
- **Aprendizado:** [KIT] Separação de Responsabilidade Única (SRP) em Perfis de Governança: Matrizes de cálculo matemático, escalas e limiares de ambiguidade não devem sobrecarregar grounding_domains.yaml; exigem perfil (ambiguity_scoring.yaml) e schema próprios.
  - **Racional:** Mantém grounding_domains.yaml focado estritamente em grounding temporal e autoridades externas, enquanto os parâmetros de pontuação matemática ganham governança e schema dedicados.
  - **Origem:** `srv_master` | **Data:** 09-11-2026 23:28:42(GMT-04:00)
- **Aprendizado:** [KIT] Princípio Constitucional de Engenharia Didática: 100% dos scripts utilitários do kit devem implementar --help didático com exemplos práticos de uso; código sem help ou com help críptico é considerado violação constitucional bloqueante.
  - **Racional:** Torna o kit acessível a pesquisadores e desenvolvedores de diferentes níveis e viabiliza validação automatizada de conformidade antes de qualquer release.
  - **Origem:** `srv_master` | **Data:** 09-11-2026 23:28:42(GMT-04:00)
- **Aprendizado:** [KIT] Suíte de Sensores de Runtime e Pipeline Anti-Ruído: O terminal bruto nunca deve vazar para a janela de contexto; sensores devem fatiar e destilar falhas em Structured Error Envelopes (JSON minimalista), usando Context Lifting para persistir dumps no disco e ativando o Inverted CoT para auto-correção.
  - **Racional:** Previne diluição de atenção e o fenômeno lost-in-the-middle em prompts longos, forçando o modelo a raciocinar sobre evidências estruturadas.
  - **Origem:** `srv_master` | **Data:** 09-11-2026 23:28:42(GMT-04:00)
- **Aprendizado:** Em scripts bash com 'set -eo pipefail', pipelines contendo grep (ex: grep ... | awk ...) falham imediatamente quando grep não encontra linhas. Devem ser protegidos com '(grep ... || true) | awk ...'.
  - **Racional:** Garante robustez em pipelines shell defensivos sob modo estrito sem interromper a execução prematuramente.
  - **Origem:** `srv_master` | **Data:** 10-11-2026 15:46:20(GMT-04:00)
- **Aprendizado:** Frontmatter YAML em SKILL.md de agentes de IDE deve iniciar obrigatoriamente na linha 1 exata com '---'.
  - **Racional:** Cabeçalhos ou comentários colocados antes do delimitador invalidam o parser de YAML e quebram a descoberta de skills.
  - **Origem:** `srv_master` | **Data:** 10-11-2026 15:46:20(GMT-04:00)
- **Aprendizado:** Arquivos em .vitalia/memory/session/ (como SESSION_HISTORY.md) são artefatos compilados da Camada 3 e jamais devem ser editados manualmente.
  - **Racional:** A mutação da memória de sessão pertence exclusivamente ao motor de contexto (vitalia_context_engine.py), respeitando a Regra da Cerca Elétrica.
  - **Origem:** `srv_master` | **Data:** 10-11-2026 15:46:20(GMT-04:00)
- **Aprendizado:** Proibição estrita de auto-invocação sem caminho absoluto em scripts de mock de shell
  - **Racional:** Mocks executáveis injetados no PATH temporário nunca devem chamar o mesmo nome de binário sem caminho absoluto, sob risco de recursão infinita (fork bomb) que satura processos e memória no WSL2. Preferir sempre mocks estáticos sem subprocessos.
  - **Origem:** `andrenote` | **Data:** 10-11-2026 20:17:46(GMT-04:00)
- **Aprendizado:** Validação de permissão de escrita em caminhos inexistentes
  - **Racional:** O teste defensivo prévio deve inspecionar recursivamente o primeiro ancestral existente no disco com probe temporário via mktemp, impedindo a criação precoce de diretórios órfãos.
  - **Origem:** `andrenote` | **Data:** 10-11-2026 20:17:46(GMT-04:00)
- **Aprendizado:** Resolução de symlinks em virtualenvs (PEP 405): Path.resolve() em symlinks de python segue até o binário do sistema, perdendo o sys.prefix do ambiente virtual. O kit deve sempre utilizar o caminho absoluto sem seguir symlinks (Path(os.path.abspath(c))).
  - **Racional:** Garante que subprocessos executados com o binário resolvam o pyvenv.cfg do virtualenv e seus pacotes instalados.
  - **Origem:** `andrenote` | **Data:** 11-11-2026 10:58:54(GMT-04:00)
- **Aprendizado:** Fronteira de Sandbox em IDEs de Agentes: Erros com código 127 ao acessar binários fora do workspace decorrem exclusivamente do isolamento de sandbox do terminal. A governança do AGENTS.md deve instruir BypassSandbox: true e vetar a auto-reinstalação reflexa via kit-bootstrap.sh.
  - **Racional:** Evita loops de reinstalação e confusão cognitiva dos modelos diante de permissões de terminal.
  - **Origem:** `andrenote` | **Data:** 11-11-2026 10:58:54(GMT-04:00)

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
- **Aprendizado:** [PROJETO] Isolamento Rigoroso em Fases de Concepção: Manter source/ e ~/.vitalia/ 100% intocados durante a revisão contratual e concentrar relatórios e matrizes decisórias na pasta TEMP/ garante rastreabilidade e impede corrupção prematura do repositório antes da execução formal da spec.
  - **Racional:** Assegura que qualquer implementação de código no repositório ocorra estritamente sob uma spec formal aprovada.
  - **Origem:** `srv_master` | **Data:** 09-11-2026 23:28:42(GMT-04:00)
- **Aprendizado:** A suíte de sensores VRSS atua como guarda ativa durante todo o ciclo de desenvolvimento, capturando caminhos hardcoded, anomalias e segredos em tempo real.
  - **Racional:** Executar a suíte de 5 sensores previne regressões contratuais e violações de Progressive Disclosure.
  - **Origem:** `srv_master` | **Data:** 10-11-2026 15:46:20(GMT-04:00)
- **Aprendizado:** Preservação de exit codes em redirecionamentos Bash
  - **Racional:** O padrão 'command >> file 2>&1 || true; STATUS=$?' mascara o código de retorno tornando-o 0. A abordagem canônica é usar 'set +e ... set -e' capturando $? diretamente sem '|| true'.
  - **Origem:** `andrenote` | **Data:** 10-11-2026 20:17:46(GMT-04:00)
- **Aprendizado:** Preservação de atributos raiz em contratos de ambiente: Manter atributos de alto nível (project_root, kit_dir) no retorno do health check garante retrocompatibilidade estrita para ferramentas existentes enquanto novos consumidores consomem os nós segregados kit_runtime e project_runtime.
  - **Racional:** Permite evolução contínua de contratos sem quebrar consumidores legados ou suítes de testes anteriores.
  - **Origem:** `andrenote` | **Data:** 11-11-2026 10:58:54(GMT-04:00)

## GOVERNANCA
- **Aprendizado:** [GOVERNANCA] Specs Corretivas vs Imutabilidade de Entregas: Specs concluídas e comitadas são artefatos imutáveis. Erros e lacunas pós-entrega não devem ser maquiados como 'hardening' nem anexados à spec antiga; exigem abertura de spec corretiva sequencial formal (fix-*) com Root Cause Analysis transparente.
  - **Racional:** Garante rastreabilidade histórica íntegra e maturidade de engenharia sem falsear o escopo do que foi entregue.
  - **Origem:** `ai-control` | **Data:** 06-11-2026 13:16:00(GMT-04:00)
