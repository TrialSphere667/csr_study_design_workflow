# CSR Study Design Workflow Prompt Pack

This prompt pack defines a modular workflow for extracting, generating, verifying, and evaluating a CSR Study Design section.

The overall design goal is to support source-grounded, practical, and reviewable automation rather than single-step freeform drafting.

---

## Overview

The workflow is designed around the idea that high-quality Study Design generation should be treated as a modular process:

1. extract the key design facts from source
2. generate the Study Design paragraph from validated facts
3. verify the generated paragraph against source
4. score both the generated text and the verifier performance

This modular design is intended to improve:
- factual reliability
- completeness
- traceability
- diagnosability of failures
- human review usability

---

## Workflow Diagram

SOURCE_TEXT  
→ EXTRACTOR  
→ STRUCTURED_ELEMENTS  
→ GENERATOR  
→ GENERATED_TEXT  
→ VERIFIER  
→ VERIFIER_OUTPUT  
→ SCORERS

More specifically:

- Extractor: identifies source-supported study design elements
- Generator: drafts a CSR Study Design paragraph
- Verifier: reviews the generated paragraph
- Generator scorer: evaluates the generated paragraph
- Verifier scorer: evaluates the verifier itself

---

## Prompt Pack Structure

```text
csr_study_design_workflow/
│
├── shared/
│   └── workflow_rules.md
│
├── extractor/
│   └── csr_study_design_extractor.md
│
├── generator/
│   └── csr_study_design_generator_v2.md
│
├── verifier/
│   └── csr_study_design_verifier_v2.md
│
├── scoring/
│   ├── csr_study_design_generator_scorer_v2.md
│   └── study_design_verifier_scorer_v2.md
│
└── README.md
