# CoTheories

CoTheories is the seed-stage home for CoCivium-aligned theories and theory records.

It provides:
- A raw CoTheoryTrove text file for mining and regeneration.
- Per-theory machine-readable records in JSON under `data/theories`.
- A JSON schema and YAML example under `schema/` for validation and future tooling.
- A landing point for linking generic human theories to CoCivium-specific domain models and CoIndex entries.

## Layout

- `docs/CoTheoryTrove_v1_raw.txt`  
  Initial Wave 1 theory trove, generated from generic science / society / philosophy prompts.  
  Each line has the form:  
  `Theory Name: term1, term2, ...`.

- `data/theories/*.json`  
  Auto-generated CoTheory records; one file per theory.  
  Each record follows the schema in `schema/CoTheory_Record_Schema_v1.json`.

- `schema/CoTheory_Record_Schema_v1.json`  
  JSON Schema for a CoTheory record.

- `schema/CoTheory_Record_Example_v1.yaml`  
  Human-friendly example of a CoTheory record.

## CoTheory record fields (v1)

Key fields:

- `theory_id`  
  Stable ID for the theory. Wave 1 is auto-generated (`GEN.*`) and treated as archival seeds.

- `name`  
  Human name of the theory.

- `domain`  
  Coarse domain bucket (for example: `Physics`, `Biology`, `Economics`, `Philosophy`, `Governance`, `ComputerScience`, `CognitiveScience`, `ComplexSystems`).  
  Wave 1 domain labels are simple substring-based auto-tags and should be treated as provisional.

- `tier`  
  Rough importance / centrality ranking for CoCivium (1 = core; 2 = important; 3 = background / archival).  
  Wave 1 seeds default to `3`.

- `status`  
  Lifecycle / posture of this theory within CoCivium.  
  Currently one of:
  - `active`
  - `deprecated`
  - `speculative`
  - `adversarial`
  - `archival` (Wave 1 default)

- `stance`  
  How CoCivium intends to use this theory:
  - `core`       : central to CoCivium worldview.
  - `useful`     : generally useful background.
  - `disputed`   : contested but important to track.
  - `caution`    : potentially misleading if used naively.
  - `contrary`   : intentionally tracked as a contrast case or anti-example.

- `summary_coSpeak`  
  Short CoCivium-facing summary in CoSpeak style.

- `core_terms`  
  Ordered list of the most important terms for this theory, from the original trove.

- `problem_ids`  
  Links to problem statements or open questions that this theory helps address.

- `cotwin_ids`  
  Links to sibling or competing theories that should be considered together.

- `sources`  
  Optional list of canonical references (books, papers, articles).

- `tags`  
  Freeform tags to connect with CoIndex / GIBindex and other repos.

- `origin_note`  
  Provenance note for the record.

- `notes_coMeta`  
  Meta-notes about how this theory is used or interpreted in CoCivium.

## Current status (Wave 1)

- 80 theory records auto-generated from `CoTheoryTrove_v1_raw.txt`.
- Coarse `domain` auto-tagging and default `tier = 3`, `status = archival`, `stance = useful`.
- Schema and example file written to `schema/`.

This wave is intentionally generic and conservative: the goal is to provide a substrate for later waves, not to lock in any final CoCivium worldview.

## Relationship to CoIndex, CoCore, and CoCivium

- **CoIndex** is expected to become the primary index of all CoSuite assets, including problems, domain models, and concept nodes.
- **CoTheories** will link into CoIndex by:
  - Adding `problem_ids`, `cotwin_ids`, and `tags` that point at CoIndex entries.
  - Maintaining per-theory status and stance for governance and advice engines.
- **CoCore** will store domain models and civic patterns that sit downstream from these theories.  
  CoTheories provides the upstream conceptual layer that those models can declare as assumptions or influences.

Until CoIndex has a stable first wave of entries, the heavy cross-linking work is intentionally parked.

## Next waves (sketch)

Planned future waves could include:

- **T10_FromCoIndex_v1**  
  Use CoIndex outputs to populate `problem_ids`, `cotwin_ids`, and tags on a subset of theories that are most relevant to CoCivium governance.

- **T11_CoCoreAlignment_v1**  
  Attach CoCore domain models to the theories they assume, extend, or dispute.

- **T12_TierAndStanceReview_v1**  
  Promote some theories from `tier = 3` archival seeds to `tier = 1` or `tier = 2` based on actual use in CoCivium.

- **T13_GIBindexIntegration_v1**  
  Add GIBindex / CoIndex IDs and any future Co* concept IDs as tags on these records.

This repo is seed-stage and may change structure as CoIndex and CoCore evolve.
