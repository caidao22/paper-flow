# Flow Audit Protocol

Use this protocol when the user asks to identify or repair abrupt concept
introductions, broken transitions, duplicated claims, misplaced sentences, or
whole-manuscript logical flow. Apply it after the article-level check in ch01
and alongside the paragraph and IMRAD guidance in ch03--ch05.

## Select the operating mode

Infer the mode from the user's request and preserve any requested output
constraint.

- `diagnose-only`: identify defects without rewriting, explaining causes, or
  proposing repairs. Use for requests such as “only say what” or “list the
  problems.”
- `interactive`: present one issue at a time with its location, original text,
  proposed operation, and revised passage. Wait for the user's decision before
  editing or advancing to the next issue.
- `revise`: identify and repair the requested scope, then re-audit the affected
  context. Do not silently expand a local revision into a whole-manuscript
  rewrite.

An audit request does not authorize edits. A request to revise, fix, address, or
apply accepted wording does.

## Establish the audit frame

Read the complete requested scope and enough adjacent text to evaluate each
boundary. For a whole manuscript:

1. State the article's central purpose and ordered evidence story.
2. Record the intended job of each section and subsection.
3. Label each paragraph by its controlling idea.
4. Label each sentence by one primary function:
   `orient | define | background | purpose | method | result | evidence |
   interpret | qualify | limit | imply | bridge`.
5. Build a compact concept ledger and claim-location map before reporting
   local defects.

Inspect prose together with headings, captions, tables, and appendices when
they carry the setup, evidence, or qualification needed by the claim.

## Check 1: Abrupt concept entry

Track the first appearance of every material method, model, comparator,
dataset, metric, subgroup, mechanism, limitation, and implication.

Flag an entry when any of the following occurs:

- a new concept appears without definition or a backward anchor;
- the subject, scientific question, comparator, outcome, scale, population,
  time horizon, or evidence type changes without orientation;
- a result appears before the question or comparison it answers;
- a qualification or subgroup analysis appears after the headline claim with
  no advance signal;
- `this`, `these`, `such`, `the former`, or another reference has no unique
  antecedent;
- a heading names the topic but the first sentence still leaves its relation
  to the preceding argument unstated.

Do not flag a concept solely because it is new. First-use definitions,
explicitly announced enumerations, conventional section openings, and
independent analyses already named in a section roadmap are legitimate.

## Check 2: Broken or false transition

For each sentence and paragraph boundary, state the actual relationship in
plain language: `additive | adversative | causal | sequential | none`.

Flag the boundary when:

- the connector names a different relationship from the propositions;
- a causal connector joins association, chronology, or coexistence;
- an adversative connector joins compatible or independent statements;
- the next sentence lacks a shared concept or explicit bridge;
- a paragraph closes one topic and the next begins another without a
  two-anchor transition;
- a transition refers backward but does not establish the next question.

Do not add a connector when no defensible relationship exists. Reorder, split,
or relocate the material instead.

## Check 3: Duplicated claim

Represent each material claim as:

`subject + predicate + comparator/object + scope + evidence status`.

Map each occurrence across the title, abstract, Introduction, Results,
captions, Discussion, Conclusion, and Appendix. Assign one rhetorical function
to every occurrence:

`preview | define | demonstrate | qualify | interpret | synthesize | conclude`.

Flag duplication when:

- adjacent sentences state the same claim with the same function;
- prose restates values already visible in a table without selecting a pattern;
- Results repeats a full method already established in Methods;
- Discussion repeats a demonstrated result without interpretation or synthesis;
- a caption and its surrounding prose provide the same complete numerical report;
- repeated claims drift in comparator, scope, modality, or numerical precision.

Do not flag purposeful recurrence when each occurrence has a distinct function,
such as previewing in the Abstract, demonstrating in Results, interpreting in
Discussion, and closing with a bounded conclusion.

## Check 4: Misplaced sentence

Compare each sentence's primary function with its current location.

| Sentence function | Default location |
|---|---|
| Problem, prior knowledge, gap, study aim | Introduction |
| Reproducible procedure, parameter, data processing, analysis rule | Methods or Appendix |
| Observation, comparison, effect size, primary uncertainty | Results |
| Cross-result synthesis, literature relation, bounded interpretation | Discussion |
| Claim boundary and its consequence | Adjacent to the claim or in Limitations |
| Future test or extension | Discussion or explicit Future Work |
| Display-reading instructions | Figure or table caption |
| Access, repository, identifier, license | Data or Code Availability |

Flag a sentence when its function conflicts with its section, interrupts the
paragraph's controlling idea, separates a claim from its qualification, or
appears after material that depends on it. Treat Appendix placement by the same
rule: supporting material should remain with the method, result, or audit thread
it serves.

## Prioritize findings

- `blocking`: a missing or misplaced link changes the claim, comparison,
  evidence boundary, or interpretation.
- `major`: section or paragraph order obscures the active question, result, or
  qualification.
- `minor`: local abruptness, redundant restatement, weak referent, or inaccurate
  connector that does not alter the scientific claim.

Report findings in document order within severity. Do not inflate severity to
make the audit appear more consequential.

## Output contracts

### Diagnose-only

Use one line per issue:

`- [location] Category: precise defect.`

State what is wrong. Omit causal explanation, repair advice, praise, and a
general writing lecture when the user requests findings only.

### Interactive

Handle exactly one issue per turn:

1. `Issue and location`
2. `Original`
3. `Proposed operation` (`keep | delete | move | split | merge | bridge | narrow`)
4. `Proposed revision`
5. One concise approval question

Do not edit or advance to the next issue until the user accepts, modifies, or
rejects the proposal. After an accepted edit, re-read the preceding and
following paragraphs before presenting the next issue.

### Revise

Record the issue and operation, edit only the authorized scope, preserve facts,
citations, quantities, terminology, and evidence strength, then re-audit all
affected boundaries. Report the changed locations and verification performed.

## Guardrails

- Audit article logic before paragraph logic, and paragraph logic before
  sentence transitions.
- Do not use a transition to conceal a missing premise or unsupported claim.
- Do not invent causal, temporal, or evidential relationships.
- Do not confuse an unfamiliar technical term with an abrupt concept entry.
- Do not require a bridge when adjacency, a roadmap, or an established
  sequence already supplies one.
- Do not split tightly coupled claims into choppy fragments.
- Do not vary technical terminology merely to reduce repetition.
- Do not remove qualifications, negative results, reproducibility details, or
  required reporting information as a flow repair.
- Preserve intentional section-level recurrence when the rhetorical function
  changes.
- When evidence is unavailable, flag the gap instead of drafting support.

## Completion check

After diagnosis or revision:

1. Re-read every changed boundary with one paragraph of context on each side.
2. Re-run the concept-entry and transition checks at moved or split material.
3. Re-run the claim-location map for duplicated or narrowed claims.
4. Confirm that every aim has a method, result, interpretation, and bounded
   conclusion.
5. Confirm that no edit changed a citation, quantity, comparator, uncertainty,
   or claim strength unintentionally.
