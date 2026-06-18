# Reference Data Strategy

## 1. Data Types Needed
- Vehicle product data: model capabilities, feature availability, safety constraints.
- Navigation and POI data: maps, traffic, destination metadata.
- Policy data: privacy rules, consent settings, blocked topics, compliance requirements.
- User preference data (consented): media preferences, recent destinations, communication habits.
- Knowledge content: owner manuals, support FAQs, service bulletins.

## 2. Data Volume and Coverage Targets
- Vehicle docs: 100% of active model-year trims in rollout markets.
- Policy corpus: all active privacy/safety policy versions by region.
- Retrieval corpus freshness target: <= 24-hour lag for dynamic data and <= 7-day lag for documentation updates.

## 3. Data Sources
- Internal systems: connected services platform, product documentation repository, consent management service.
- External partners: map/traffic providers, media catalogs.

## 4. Bias and Quality Assessment
- Evaluate intent success and error rates by user segment, region, and device ecosystem (iOS/Android).
- Run fairness checks for differential failure rates across demographic slices.
- Maintain red-team prompt suite for safety and harmful-output tests.
- Require policy-compliance checks in offline and online evaluation pipelines.

## 5. Data Governance and Privacy
- Data minimization in prompts.
- Purpose limitation and explicit consent gating for personalization fields.
- Pseudonymization for training and analytics datasets.
- Access controls and audit logs for sensitive data paths.

## 6. Update Cadence
- Dynamic navigation context: near-real-time.
- Policy and safety rules: immediate on release.
- Documentation corpus: nightly sync plus emergency patch path.
- Embedding index refresh: daily incremental, weekly full rebuild.

## 7. Operational Ownership
- Data source owners: Connected Services Data Governance team.
- Quality owner: AI Quality and Safety team.
- Retrieval/index owner: ML Platform Engineering.
