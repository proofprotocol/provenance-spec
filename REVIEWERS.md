# Review Disclosure

Work: Proof Provenance Specification
Licensor: Nebulonium, Inc., dba HACKERverse (Proof Protocol)

## Declaration

[REVIEWED]
No
[/END OF REVIEWED]

[REVIEWED BY]
None
[/END OF REVIEWED BY]

## What this file is

REVIEWERS.md states whether anyone other than the author has reviewed this repository, who they are, whether each reviewer is a human or an AI, what they reviewed, and what interests they hold. It sits at the root of every Proof Protocol repository beside AI_DISCLOSURE.md (who wrote it), FUNDING.md (who paid for it), and LICENSE.md (who may use it).

## What it must accomplish

1. **Transparency.** Any reader, human or machine, can tell from this file alone whether the work was reviewed, by whom, and how far the review went.
2. **Traceability.** Every reviewer is named and identified by ORCID or URL, so a reader can find the person or system that reviewed the work.
3. **No borrowed authority.** A review covers only its stated scope. A reviewer's name never implies endorsement of anything outside that scope, and a review is never presented as proof, certification, or conformance (Proof Economy Code of Ethics, Sections 6.1 and 6.3).
4. **Human and AI kept apart.** Every review states whether a human or an AI performed it, and for an AI, which system. An AI review is not presented as a human review (Code of Ethics, Section 8.8).
5. **Ethics.** The Proof Economy Code of Ethics (https://proofeconomy.foundation, published at https://github.com/proofprotocol/CODE-OF-ETHICS) MUST be followed. Where this file and the Code differ, the stricter rule applies.

## Fields

| Marker | Accepted values | Rule |
|---|---|---|
| `[REVIEWED]` ... `[/END OF REVIEWED]` | `Yes` or `No`, exactly, on one line | Exactly one block per file. `Yes` if at least one review is recorded |
| `[REVIEWED BY]` ... `[/END OF REVIEWED BY]` | One line each: `Name:`, `Type:` (`human` or `ai`), `Model:` (required when Type is `ai`), `ID:` (ORCID `0000-0000-0000-000X`, an `https` URL, or `none`), `Affiliation:`, `Scope:`, `Date:` (`YYYY-MM-DD`), `Conflicts:` (`none` or a description) | One block per review. When `[REVIEWED]` is `No`, exactly one block containing the single word `None` |

Example of a reviewed repository:

```
[REVIEWED]
Yes
[/END OF REVIEWED]

[REVIEWED BY]
Name: Jane Example
Type: human
ID: 0000-0002-1825-0097
Affiliation: Example University
Scope: Sections 1 to 9, normative text
Date: 2026-11-01
Conflicts: none
[/END OF REVIEWED BY]

[REVIEWED BY]
Name: Example Review Agent
Type: ai
Model: Example Model 1.0
ID: https://example.com/agent
Affiliation: Example Labs
Scope: schemas and conformance vectors
Date: 2026-11-02
Conflicts: none
[/END OF REVIEWED BY]
```

## Rules

1. **What counts as a review.** A reading of the work by someone other than its author, with findings, whose scope is stated. Typo fixes, automated linting, and the author's own drafting assistance are not reviews; AI drafting assistance belongs in AI_DISCLOSURE.md.
2. **Scope is binding.** The `Scope:` line is the whole of what the reviewer looked at. Nothing outside it is reviewed.
3. **Conflicts.** A reviewer states every financial, employment, advisory, or competitive relationship with the Licensor, a funder, or a Provider measured under these specifications. Disclosure alone does not cure a conflict (Code of Ethics, Section 8.6).
4. **Consent.** A human reviewer is listed only with their consent, and may ask to be removed from future versions; a past version's record is not rewritten.
5. **History is the audit trail.** This file is versioned with the repository. A review, once recorded for a version, stays in that version's history.
6. **Markers.** The markers appear bare, each on its own line, exactly as written above. They are not wrapped in comments.
7. **Fail closed.** A repository with no REVIEWERS.md, more than one `[REVIEWED]` block, a value other than `Yes` or `No`, `Yes` with no review, `No` with a review, a review missing a required field, or an AI review without `Model:`, is treated as unreviewed.
8. **Humans and machines.** A person reading this file and a program parsing the markers reach the same result.
