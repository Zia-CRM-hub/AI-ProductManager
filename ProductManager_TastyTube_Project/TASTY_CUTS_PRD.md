# Product Requirements Document (PRD)

## Product
Tasty Cuts: AI-Powered Video Creation App for Home Chefs

## Date
2026-06-18

## 1. Context
TastyTube is a large short-form platform with millions of active users. Cooking videos are highly engaging, but content supply is constrained by difficult creation workflows: long editing cycles, manual captioning, and effort-heavy recipe writing.

Viewer engagement depends on new video volume. Increasing creator throughput is therefore a core growth lever.

## 2. Product Vision
Create a mobile-first assistant that turns raw cooking footage into publish-ready recipe videos with minimal effort.

## 3. MVP Objective
Increase creator throughput by at least 2x in pilot and establish the foundation to scale to 10x creator adoption over subsequent releases.

## 4. Target Users
- Primary: Home chefs who are new to TastyTube content creation.
- Secondary: Existing creators who want faster editing and publishing.

## 5. MVP Scope (In)
1. Specify and validate training dataset from top 1,000 qualifying videos.
2. Conduct exploratory user research (8-12 non-expert creators).
3. Select and train human labeling team.
4. Prepare training data:
- Split videos into step clips.
- Apply labels (equipment, ingredients, quantities, techniques).
5. Build ML model to clip video into recipe steps.
6. Build ML model to classify recipe steps.
7. Generate captions (third-party STT + LLM caption generation).
8. Generate title, description, and recipe summary (LLM).
9. Mobile app to review/reorder clips and edit text.
10. Publish to TastyTube with one-tap workflow.
11. Conduct realistic usability testing.
12. Create Recipe Library with 5-8 showcase videos.

## 6. Out of MVP (Post-MVP)
- Publish to YouVideo, TikTak, Fastgram.
- Translation into top 10 languages and localization into up to 5 additional languages.
- Extensions API and reference implementation.

## 7. Success Metrics
### North Star
- Weekly published cooking videos created via Tasty Cuts.

### Primary
- Creator completion rate (raw upload to publish): >= 55% in pilot.
- Median time to publish: 60% reduction from baseline.
- Captions accepted with no manual edits: >= 70% of clips.
- Auto-generated recipe accepted with minor/no edits: >= 60%.
- D7 creator retention after first publish: +20% vs control.

### Guardrails
- Crash-free sessions: >= 99.5%.
- P95 processing latency (10-min source video): <= 6 minutes.
- Caption critical error rate: <= 2%.

## 8. AI Model and Data Strategy
### Model A - Video Clip Segmentation
- Goal: Detect step boundaries and split raw footage into recipe clips.
- Model: Temporal sequence model (video transformer or TCN) with shot/action features.
- Inputs: Labeled clip boundaries, audio transitions, motion changes.
- Fallback: If confidence is low, propose coarse clips and ask user to confirm splits.

### Model B - Recipe Step Classification
- Goal: Label clips with cooking step attributes.
- Model: Multi-label classifier over visual/audio/text embeddings.
- Labels: equipment, ingredients, quantities, techniques.
- Fallback: If confidence is low, show top-3 suggestions for user selection.

### Model C - Captions and Metadata Generation
- STT: Third-party speech-to-text for narration transcript.
- LLM: Generate US English captions, title, description, recipe summary.
- Fallback: If transcript confidence is low, prompt manual caption edit mode.

## 9. Integration Requirements
- On-device editing UI with cloud-assisted ML processing.
- One-tap publish API integration with TastyTube upload and metadata services.
- Telemetry for clip edits, caption edits, generation acceptance, publish outcomes.

## 10. User Stories (MVP)
1. As a home chef, I want my raw video automatically split into recipe steps so I can avoid manual clipping.
2. As a home chef, I want each clip labeled with likely step details so I can assemble videos quickly.
3. As a home chef, I want automatic captions so I can publish faster.
4. As a home chef, I want title, description, and recipe draft text generated so I can avoid writing from scratch.
5. As a home chef, I want to review and reorder clips so my final flow matches my intent.
6. As a home chef, I want one-tap publish to TastyTube so I can post immediately.
7. As a PM, I want usability test insights before launch so we remove major blockers.
8. As a content lead, I want a recipe library to onboard first-time users quickly.

## 11. Risks and Mitigations
- Risk: Label inconsistency harms model quality.
- Mitigation: gold-standard QA set, calibration sessions, inter-annotator agreement checks.

- Risk: Processing latency too high for mobile experience.
- Mitigation: asynchronous cloud jobs, progress states, and model optimization.

- Risk: Generated metadata quality varies by speaking style.
- Mitigation: confidence scoring + inline editing with suggested alternatives.
