# MVP Roadmap (6 Months)

## Strategic Launch Theme
"Create publish-ready cooking videos in minutes, not hours."

## Phase 0 - Week 1-2: Alignment and Baselines
- Finalize MVP scope and launch narrative.
- Define baseline metrics for time-to-publish and completion rate.
- Approve legal/privacy constraints for data and annotation.

## Phase 1 - Week 3-6: Data and Research Foundation
- Build top-1,000 candidate dataset query and validate sample of 100.
- Run exploratory research with 8-12 non-expert home chefs.
- Lock labeling taxonomy and annotation instructions.
- Staff annotation team.

Exit Criteria:
- Validated dataset accepted.
- User workflow findings documented.
- Annotation operations ready.

## Phase 2 - Week 7-12: Labeling and Model Baselines
- Manual split videos into recipe-step clips.
- Apply labels: equipment, ingredients, quantities, techniques.
- Train baseline clip segmentation model.
- Train baseline recipe-step classification model.

Exit Criteria:
- Target annotation volume complete.
- Baseline model metrics reach minimum threshold.

## Phase 3 - Week 13-18: Product Build and AI Integration
- Build mobile editor for clip review/reorder and text editing.
- Integrate STT + LLM caption generation.
- Integrate title/description/recipe generation.
- Implement one-tap publish to TastyTube.

Exit Criteria:
- End-to-end draft-to-publish path works in staging.

## Phase 4 - Week 19-22: Usability Testing and Hardening
- Run realistic usability tests with target creators.
- Prioritize and fix critical blockers.
- Improve model quality where failure rates exceed guardrails.
- Produce 5-8 Recipe Library showcase videos.

Exit Criteria:
- No P0/P1 usability blockers.
- Quality metrics meet launch thresholds.

## Phase 5 - Week 23-24: Launch Readiness
- Final launch checklist, monitoring, rollback plans.
- Team training and support scripts.
- Product announcement assets and demo narrative.

## MVP vs Post-MVP Split

### MVP (Now)
- Dataset + annotation operations
- Clip segmentation model
- Step classification model
- Captions and metadata generation
- Mobile editing app (at least one platform)
- Publish to TastyTube
- Usability testing
- Recipe Library

### Post-MVP (Next)
- Publish to YouVideo, TikTak, Fastgram
- Multilingual translation
- Extensions API
