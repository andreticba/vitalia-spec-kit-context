<!-- README.md | Atualizado em: 03-11-2026 05:50:35(GMT-04:00) -->

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
| 03-11-2026 05:47:37(GMT-04:00) | `ai-control (17a6f667)` | specs/001-sdd-judge-subagent | `Executar /vitalia-session-consolidate para consolidar os shards e renderizar o Dashboard` |
</details>

<details>
<summary><strong>⚖️ Clique para expandir as Decisões Arquiteturais Consolidadas</strong></summary>

<br/>

| Máquina (ID) | Decisão Arquitetural | Impacto / Racional |
| :--- | :--- | :--- |
| `17a6f667` | **[246ef7bd]** `ARQUITETURA` Utilizar estritamente contratos JSON OpenAPI 3.0 puros (sem $schema, sem title e sem additionalProperties: false) | Evita erros de compilação HTTP 400 no compilador REST do Google Gemini. |
| `17a6f667` | **[ad0a2d82]** `ARQUITETURA` Adotar Sanduíche Constitucional (Primacy Bias P00-P20 e Recency Checklist) e Inverted CoT | Neutraliza attention loss em prompts longos e mitiga confirmação prematura via veredito emitido apenas ao final da crítica. |
| `17a6f667` | **[a439a5bb]** `ARQUITETURA` Executar o SDD-Judge como Sub-Agente nativo na IDE Antigravity com HITL soberano | Permite auditoria em janela de 1M-2M tokens com Sanduíche Constitucional sem perda de regras e sem travar a IDE. |
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
