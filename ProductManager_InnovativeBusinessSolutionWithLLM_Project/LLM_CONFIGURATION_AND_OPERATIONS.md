# LLM Configuration and Operations

## 1. Deployment Option
Recommended: Hybrid deployment (edge safety runtime + cloud private LLM endpoint).

Why:
- Preserves resilience under network interruptions.
- Enables low-latency safety gating close to the vehicle.
- Maintains centralized governance for model behavior.

Alternative options:
- Pure cloud: simpler architecture, weaker offline resilience.
- Pure edge: stronger privacy posture, weaker model quality and update velocity.

## 2. Runtime Configuration
### Generation Settings by Task
- Driving-mode assistant response:
  - Temperature: 0.1
  - Max tokens: 120
  - Top-p: 0.8
- Parked-mode assistant response:
  - Temperature: 0.3
  - Max tokens: 300
  - Top-p: 0.9
- Message summarization:
  - Temperature: 0.1
  - Max tokens: 80

### Retrieval Settings
- Embedding model: domain-optimized text embedding model.
- Chunk size: 300-500 tokens.
- Overlap: 10%.
- Top-k retrieval: 3-5 sources.
- Confidence threshold: minimum relevance and policy score required to answer.

## 3. Privacy and Security Settings
- PII masking pre-prompt (contacts, location traces, account identifiers).
- Consent-gated personalization features.
- Prompt/output logs with sensitive field redaction.
- Region-aware retention and deletion policies.

## 4. Fine-Tuning and Data Strategy
Phase 1:
- No fine-tuning; prompt engineering + policy templates + RAG.

Phase 2:
- Build supervised dataset from anonymized in-car interactions and correction events.
- Evaluate lightweight fine-tuning for assistant style and intent robustness.

Phase 3:
- Continuous evaluation and selective retraining based on safety/quality drift.

## 5. Evaluation Framework
Offline metrics:
- Groundedness score.
- Policy compliance rate.
- Hallucination rate.
- Brevity compliance in driving mode.

Online metrics:
- Task completion rate.
- Interaction satisfaction score.
- Safety intervention rate.
- Offline fallback success rate.

## 6. Risk Controls
- Confidence-based fallback to offline-safe templates.
- Block/redirect for high-risk prompts while driving.
- Prompt injection and unsafe-content detection.
- Session token quotas and anomaly cost alerts.

## 7. Operating Model
- Product owner: In-Car Digital Product Manager.
- Prompt/policy owner: Conversation Design + Safety team.
- Model owner: ML Platform team.
- Data owner: Connected Services Data Governance team.
- Incident response owner: Vehicle Digital Operations.
