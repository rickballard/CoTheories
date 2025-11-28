# CoTheories – Plan and Parking Lot (v1)

## 1. Current state

- CoTheories repo created and linked to GitHub.
- Wave 1 theory trove seeded at `docs/CoTheoryTrove_v1_raw.txt`.
- 80 auto-generated CoTheory records under `data/theories/GEN.*.json`.
- Basic `domain` auto-tagging applied by substring rules.
- JSON Schema and YAML example written to `schema/`.
- First commit pushed to `main` with message:
  `seed: CoTheoryTrove_v1, CoTheory records, and schema v1`.

## 2. Constraints and sequencing

- CoIndex is in the process of indexing CoSuite assets.
- CoTheories should not attempt full cross-linking into CoCore or other repos
  until CoIndex has a first usable wave of entries.
- This document acts as a parking lot for intent and future MegaWaves.

## 3. Candidate future MegaWaves

- **MW_CoTheories_T10_FromCoIndex_v1**  
  - Use CoIndex outputs to:
    - Attach `problem_ids` for theories that are directly referenced in open problems.
    - Add `cotwin_ids` between theories that often co-occur in assets.
    - Seed `tags` with CoIndex / GIBindex concept IDs.

- **MW_CoTheories_T11_CoCoreAlignment_v1**  
  - Scan CoCore domain models and:
    - Record which theories each model assumes.
    - Promote those theories to higher `tier` or `core` stance where appropriate.

- **MW_CoTheories_T12_TierAndStanceReview_v1**  
  - Manual / semi-automated review of:
    - `tier` values for central theories.
    - `status` and `stance` for disputed or adversarial theories.
  - Prepare a short guide for how advice engines should interpret these fields.

- **MW_CoTheories_T13_GIBindexIntegration_v1**  
  - For each high-priority theory:
    - Add GIBindex IDs to `tags`.
    - Align with any existing Co* concept labels (CoPortal, CoBeacon, CoScendence, etc.).

## 4. Parking-lot notes

- CoTheories should remain relatively minimal and machine-friendly.
- Deeper narrative and mythos work about these theories belongs in CoCivium and CoSteward.
- When CoIndex v1 is ready, revisit this plan and confirm the sequence and scope of the next waves.
