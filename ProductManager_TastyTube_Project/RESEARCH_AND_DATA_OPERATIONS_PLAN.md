# Research and Data Operations Plan

## 1. Dataset Specification and Validation

## Objective
Retrieve top 1,000 videos from TastyTube matching:
- Single recipe
- Single camera
- Shot on phone
- Portrait orientation
- Narration in US English
- Captions in US English

## Retrieval Steps
1. Query top-performing cooking videos with required metadata filters.
2. Rank by engagement quality (completion rate, saves, shares) to avoid clickbait bias.
3. Pull 1,000 records with source metadata and rights checks.

## Validation Protocol
- Randomly sample 100 videos.
- Manually inspect against criteria and quality rubric.
- Target pass threshold: >= 92/100 valid.
- If below threshold, refine filters and repeat.

## 2. Exploratory User Research (8-12 users)

## Participant Profile
- Home chefs not experienced with TastyTube creator workflows.
- Mix of kitchen skill levels and content confidence.

## Observation Scope
- Cooking process
- Recording process
- Editing and posting behavior
- Social engagement workflow

## Outputs
- Workflow map
- Top pain points and frequency
- MVP opportunity ranking

## 3. Usability Testing (Pre-launch)

## Test Method
- Scenario-based tests in realistic conditions (home kitchen setup).
- 10 target users, 60-90 minutes each.

## Critical Tasks
- Upload raw cooking video.
- Accept/adjust clip splits.
- Edit captions and recipe text.
- Publish to TastyTube.

## Success Gates
- >= 80% task completion without moderator rescue.
- Median time-to-publish <= target threshold.
- No unresolved critical blockers before launch.

## 4. Labeling Team Plan

## Volume Estimate (Conservative)
- Dataset: 1,000 videos
- Avg source duration: 8 minutes
- Avg recipe clips per video: 8

## Human Effort Assumptions
- Clip splitting: 18 minutes/video (watch + segment + QA)
- Labeling: 24 minutes/video (equipment, ingredients, quantities, techniques + QA)
- Total annotation time/video: 42 minutes
- Total effort: 42,000 minutes = 700 hours

## Staffing Plan
- 10 annotators at 20 productive hours/week = 200 hours/week
- 1 QA lead at 25 hours/week
- 1 annotation manager at 20 hours/week
- Expected duration: ~4 weeks including calibration and rework buffer

## 5. Annotation Instructions (Summary)
- Segment video where an intentional step transition occurs.
- Label each clip with:
  - Equipment
  - Ingredients
  - Quantities (if observable or stated)
  - Techniques
- Use taxonomy sheet only; do not invent labels.
- Flag low-confidence clips for QA review.

## Quality Controls
- Gold set of 50 pre-labeled clips for onboarding calibration.
- Inter-annotator agreement check twice weekly.
- Random 10% QA sampling per annotator.
- Retraining trigger if QA score < 90%.

## 6. Dependency and Schedule Risk Buffers
- 20% schedule buffer for data ops rework.
- Parallelize model prototyping with early labeled subset.
- Freeze taxonomy by end of Week 4 to avoid relabeling churn.
