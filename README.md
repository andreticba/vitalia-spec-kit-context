<!-- README.md | Atualizado em: 08-11-2026 21:50:21(GMT-04:00) -->

# 🧠 Painel de Contexto — vitalia-spec-kit

<img src="https://img.shields.io/badge/Status-Ativo-success?style=flat-square" alt="Status" />
<img src="https://img.shields.io/badge/Semáforo-LIVRE-success?style=flat-square" alt="Semáforo" />
<img src="https://img.shields.io/badge/Ambiente-Standalone-blue?style=flat-square" alt="Ambiente" />
<img src="https://img.shields.io/badge/Sync-GMT--04%3A00-informational?style=flat-square" alt="Sync" />
<img src="https://img.shields.io/badge/Grounding-Ativo-blueviolet?style=flat-square" alt="Grounding" />

> **Vitalia Kit v0.5.0 — Ledger de Memória Persistente e Orquestração Multi-Máquina.**  
> Este repositório armazena o histórico distribuído, aprendizados consolidados e o controle de concorrência das sessões de trabalho do framework Vitalia.

---

## 📡 Topologia de Shards & Sincronização

<div align="center">

```mermaid
flowchart TD
  Cloud(("☁️ Git Remoto / Hub"))
  M_17a6f667["💻 ai-control<br/><i>specs/001-sdd-judge-subagent</i><br/><code>Standalone</code>"]
  M_17a6f667 <-->|"03-11-2026 05:47:37(GMT-04:00)"| Cloud
  style M_17a6f667 stroke:#0969da,stroke-width:2px,fill:#ddf4ff,color:#0969da
  M_eb10269b["💻 srv_master<br/><i>Spec 002: Universal Bootstrap Runtime</i><br/><code>Standalone</code>"]
  M_eb10269b <-->|"08-11-2026 21:48:52(GMT-04:00)"| Cloud
  style M_eb10269b stroke:#0969da,stroke-width:2px,fill:#ddf4ff,color:#0969da
  style Cloud stroke:#1a7f37,stroke-width:2px,fill:#dafbe1,color:#1a7f37
```

</div>

---

## 🖥️ Máquinas e Status Atual

<table>
  <thead>
    <tr>
      <th align="left">Máquina / ID</th>
      <th align="left">Tarefa Atual</th>
      <th align="center">Ambiente</th>
      <th align="center">Status</th>
      <th align="left">Último Sync</th>
      <th align="left">Próximo Passo (P0)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>ai-control</strong> (<code>17a6f667</code>)</td>
      <td>specs/001-sdd-judge-subagent</td>
      <td align="center"><img src="https://img.shields.io/badge/-Standalone-blue?style=flat-square" alt="Standalone" /></td>
      <td align="center"><span style="color:green;">●</span> Concluído</td>
      <td>03-11-2026 05:47:37(GMT-04:00)</td>
      <td><strong>Executar /vitalia-session-consolidate para consolidar os shards e renderizar o Dashboard</strong></td>
    </tr>
    <tr>
      <td><strong>srv_master</strong> (<code>eb10269b</code>)</td>
      <td>Spec 002: Universal Bootstrap Runtime</td>
      <td align="center"><img src="https://img.shields.io/badge/-Standalone-blue?style=flat-square" alt="Standalone" /></td>
      <td align="center"><span style="color:green;">●</span> Concluído</td>
      <td>08-11-2026 21:48:52(GMT-04:00)</td>
      <td><strong>Realizar teste de ponta a ponta da instalação do kit (kit-bootstrap.sh) em máquina limpa (WSL2/zsh) e avançar para a Spec 003.</strong></td>
    </tr>
  </tbody>
</table>

---

## 🎯 Sessão Ativa em Destaque

- **Estação Ativa:** `ai-control` (`17a6f667`)
- **Tarefa em Execução:** specs/001-sdd-judge-subagent
- **🎯 Próximo Passo Prioritário (P0):** `Executar /vitalia-session-consolidate para consolidar os shards e renderizar o Dashboard`
- **Última Sincronização:** `03-11-2026 05:47:37(GMT-04:00)`

---

## 📚 Histórico, Decisões & Guard Rails

<details>
<summary><strong>🔍 Clique para expandir o Histórico Completo de Sessões</strong></summary>

<br/>

| Data / Hora | Estação (ID) | Tarefa Executada | Próximo Passo (P0) |
| :--- | :--- | :--- | :--- |
| 08-11-2026 21:48:52(GMT-04:00) | `srv_master (eb10269b)` | Spec 002: Universal Bootstrap Runtime | `Realizar teste de ponta a ponta da instalação do kit (kit-bootstrap.sh) em máquina limpa (WSL2/zsh) e avançar para a Spec 003.` |
| 07-11-2026 21:38:04(GMT-04:00) | `srv_master (eb10269b)` | Specs 002 + 003 + Ciclo Corretivo SDD (Âncora Unificada e Blindagem de Workflows) | `Regredir o repositório raiz para o estado íntegro da Spec 001 (git reset --hard 23bb91b) e conduzir o ciclo SDD unificado (Specs 002 + 003) via dogfooding dos novos workflows a partir da âncora .vitalia/memory/data_storage/research/anchor-research-brainstorming-002-003.md` |
| 2026-11-07T06:51:57.914397-04:00 | `servido ()` | 003-fix-universal-bootstrap-omissions | `Preparar release/tag ou iniciar a próxima spec sequencial do roadmap` |
| 2026-11-04T21:08:55.792475-04:00 | `servido ()` | Spec 002: Universal Bootstrap & Runtime (v0.0.1) | `Iniciar ciclo SDD da Spec 003: Especialistas Verticais & Capacidades Especializadas` |
| 03-11-2026 05:47:37(GMT-04:00) | `ai-control (17a6f667)` | specs/001-sdd-judge-subagent | `Executar /vitalia-session-consolidate para consolidar os shards e renderizar o Dashboard` |
</details>

<details>
<summary><strong>⚖️ Clique para expandir as Decisões Arquiteturais Consolidadas</strong></summary>

<br/>

| Máquina (ID) | Decisão Arquitetural | Impacto / Racional |
| :--- | :--- | :--- |
| `eb10269b` | **[5c455455]** `ARQUITETURA` Padronização de esquemas em OpenAPI 3.0 puro sem propriedades de meta-schema ($schema, title de raiz, additionalProperties: false). | Compatibilidade universal com ferramentas de IA, SDKs e IDEs que rejeitam dialetos incompatíveis de JSON Schema. |
| `eb10269b` | **[23ce3811]** `ARQUITETURA` Política incondicional de Zero Poda (total_budget: 0, no_prune: true) para modelos de fronteira em todos os 16 workflows SDD e 14 perfis gp_*.yaml. | Modelos de fronteira suportam janelas amplas de contexto, garantindo que nenhuma regra constitucional ou diretiva seja perdida. |
| `eb10269b` | **[98aae91b]** `ARQUITETURA` Desacoplamento total de Redis local no Kit v0.0.1, utilizando envelopes de contexto direto em disco (.vitalia/memory/data_storage/context/<machine_id>/). | Elimina dependências de serviços e containers externos para desenvolvedores e pesquisadores sem infraestrutura pesada. |
| `eb10269b` | **[9d78edb0]** `PROJETO` Consolidar todas as especificações e contratos das Specs 002, 003 e do Ciclo Corretivo na âncora unificada .vitalia/memory/data_storage/research/anchor-research-brainstorming-002-003.md para reexecução limpa (dogfooding) a partir do commit íntegro da Spec 001 (23bb91b). | Evita alucinações por artefatos intermediários divergentes e permite validar o kit recém-blindado reconstruindo as Specs 002 e 003 do zero com governança completa. |
| `eb10269b` | **[a6e3da62]** `ARQUITETURA` Criar o Sub-Agente /vitalia-research (research.toml + gp_research.yaml) e calibrar grounding_domains.yaml em 10 domínios alinhados à stack de produção do ecossistema (incluindo ai-control). | Separa a responsabilidade de pesquisa profunda, Grounding Temporal (P03), validação HTTP 200 e Engenharia Reversa Funcional em 3 Camadas antes da especificação e planejamento. |
| `eb10269b` | **[f3067b6c]** `ARQUITETURA` Instituir a Matriz Bidimensional de Testes P05 com 4 Modalidades ([TEST:NEW], [TEST:BUGFIX], [TEST:REFACTOR], [TEST:MIGRATION]), Cenário de Falsificação obrigatório e bloqueio de testes sintáticos rasos. | Impede que features de infraestrutura/CLI e migrações passem na validação apenas verificando existência de arquivos sem testar execução real e regressão. |
| `eb10269b` | **[c020e5ca]** `ARQUITETURA` Converter perfis do Guardian (gp_*.yaml) em Lentes de Fase Sem Poda (no_prune: true, total_budget: 0) combinadas com phase_guardrails e phase_profiles. | Preserva 100% da constituição em todas as fases SDD em modelos de fronteira enquanto injeta restrições especializadas por comando. |
| `eb10269b` | **[a7a8ad47]** `ARQUITETURA` Adotar Topologia de 4 Camadas Isoladas: (1) Código-fonte exclusivo em source/ no repositório raiz; (2) Kit instalado na pasta escolhida pelo usuário (padrão ~/.vitalia-spec-kit); (3) Repositório Git dedicado de sessão em .vitalia/memory/session/; (4) Repositório Git dedicado de dados em .vitalia/memory/data_storage/. | Garante isolamento entre o código versionado do kit, o runtime local da máquina hospedeira e os repositórios de memória/contexto em nuvem. |
| `17a6f667` | **[246ef7bd]** `ARQUITETURA` Utilizar estritamente contratos JSON OpenAPI 3.0 puros (sem $schema, sem title e sem additionalProperties: false) | Evita erros de compilação HTTP 400 no compilador REST do Google Gemini. |
| `17a6f667` | **[ad0a2d82]** `ARQUITETURA` Adotar Sanduíche Constitucional (Primacy Bias P00-P20 e Recency Checklist) e Inverted CoT | Neutraliza attention loss em prompts longos e mitiga confirmação prematura via veredito emitido apenas ao final da crítica. |
</details>

<details>
<summary><strong>🛡️ Clique para expandir os Guard Rails de Grounding e Domínios</strong></summary>

<br/>

| Arquivo de Regras | Status | Domínios Monitorados | Pendentes de Curadoria HITL |
| :--- | :---: | :--- | :---: |
| `grounding-domains.yaml` (Global) | ✅ Ativo | `llm_models`, `python_packages`, `external_apis`, `security_practices`, `regulations`, `cloud_services`, `scientific_claims` | — |
| `grounding-domains-local.yaml` (Projeto) | ✅ Sincronizado | Domínios locais específicos do workspace | `0 pendências` |

</details>

---

<sub>Painel gerado automaticamente pelo motor de contexto do Vitalia Kit (<code>vitalia_context_engine.py --action consolidate</code>).</sub>
