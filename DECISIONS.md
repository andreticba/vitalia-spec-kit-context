<!-- DECISIONS.md | Atualizado em: 03-11-2026 05:50:35(GMT-04:00) -->
# 🏛️ Decisões de Arquitetura e Governança Consolidadas (ADRs)

**Data/Hora de Geração:** `03-11-2026 05:50:35(GMT-04:00)` | **Fuso Horário:** America/Cuiaba `(GMT-04:00)`

| ID | Categoria | Decisão | Racional | Máquina | Data |
|---|---|---|---|---|---|
| `a439a5bb` | `ARQUITETURA` | Executar o SDD-Judge como Sub-Agente nativo na IDE Antigravity com HITL soberano | Permite auditoria em janela de 1M-2M tokens com Sanduíche Constitucional sem perda de regras e sem travar a IDE. | `17a6f667` | 03-11-2026 05:47:37(GMT-04:00) |
| `ad0a2d82` | `ARQUITETURA` | Adotar Sanduíche Constitucional (Primacy Bias P00-P20 e Recency Checklist) e Inverted CoT | Neutraliza attention loss em prompts longos e mitiga confirmação prematura via veredito emitido apenas ao final da crítica. | `17a6f667` | 03-11-2026 05:47:37(GMT-04:00) |
| `246ef7bd` | `ARQUITETURA` | Utilizar estritamente contratos JSON OpenAPI 3.0 puros (sem $schema, sem title e sem additionalProperties: false) | Evita erros de compilação HTTP 400 no compilador REST do Google Gemini. | `17a6f667` | 03-11-2026 05:47:37(GMT-04:00) |
