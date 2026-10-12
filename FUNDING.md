# Funding Disclosure

Work: Proof Provenance Specification
Licensor: Nebulonium, Inc., dba HACKERverse (Proof Protocol)

## Declaration

[FUNDED]
No
[/END OF FUNDED]

[FUNDED BY]
None
[/END OF FUNDED BY]

## What this file is

FUNDING.md states, in one place, whether anyone outside the Licensor has put money or paid resources into this repository, and if so who. It sits at the root of every Proof Protocol repository, specification and code alike, beside AI_DISCLOSURE.md (who wrote it) and, where present, CONTRIBUTIONS.md (what is contributed and to whom). Together they answer the three questions a reader should be able to ask of any work that claims to produce proof: who made it, who paid for it, and who may use it.

## What it must accomplish

1. **Transparency.** Any reader, human or machine, can tell from this file alone whether the work was funded and by whom, without asking the author.
2. **Traceability.** Every funder is named and linked, so a reader can follow the money to an organization that can be looked up. A funder, once listed, stays listed in the history of this file; funding is never removed from the record after the fact.
3. **Independence.** A specification that measures security controls loses its value if a party it measures paid to shape it. Disclosure lets every reader judge that for themselves.
4. **Ethics.** The Proof Economy Code of Ethics (https://proofeconomy.foundation, published at https://github.com/proofprotocol/CODE-OF-ETHICS) MUST be followed by everyone who maintains, funds, or relies on this work. This file is how a repository meets the Code's funding duties: truthful representation of what was funded (Section 9), disclosure of significant funding sources and of sponsorship or grants connected to standards outcomes (Section 8.6), and the Ethical Capital Principle that capital may finance the production of proof but cannot purchase the truth of that proof (Section 7.4). Where this file and the Code differ, the stricter rule applies.

## Fields

| Marker | Accepted values | Rule |
|---|---|---|
| `[FUNDED]` ... `[/END OF FUNDED]` | `Yes` or `No`, exactly, on one line | Exactly one block per file. `Yes` if any funding has gone into any released or unreleased version of this repository |
| `[FUNDED BY]` ... `[/END OF FUNDED BY]` | `Name: <organization>` and `URL: <https URL>`, one per line | One block per funder. When `[FUNDED]` is `No`, exactly one block containing the single word `None` |

Example of a funded repository:

```
[FUNDED]
Yes
[/END OF FUNDED]

[FUNDED BY]
Name: Example Research Foundation
URL: https://example.org
[/END OF FUNDED BY]

[FUNDED BY]
Name: Example Insurance Company
URL: https://example.com
[/END OF FUNDED BY]
```

## Rules

1. **What counts as funding.** Money, grants, sponsorships, research contracts, paid commercial engagements, and paid resources given in kind (cloud credits, paid staff time, equipment, lab access) provided into this project by any organization other than the Licensor, whether commercial or for research. Capital invested in or lent to the Licensor that is not directed to this project is not listed here; its disclosure follows Code Section 8.6.
2. **Every funder, named and linked.** Each funder appears with its legal or trading name and an `https` URL for that organization. An individual funding in a personal capacity is listed by name with a URL of their choosing, or `URL: none` if they have none.
3. **Funding buys nothing in the work.** A funder gains no right to alter the specification text, conformance requirements, test vectors, records, outcomes, or the decisions of any Registry, Issuer, or Witness. A funder that is also a Provider of a control measured under these specifications is still listed here, and the relationship is stated in a Notes section below the declaration. Disclosure alone does not cure a conflict (Code Section 8.6); a material conflict is also managed, mitigated, or met with recusal.
4. **Kept current.** The file is updated before any release is tagged, and in any case within 30 days of funding being received. The values in a tagged release describe that release.
5. **History is the audit trail.** This file is versioned with the repository. Changes are made by commit, never by rewriting history, so any past state of the disclosure can be recovered.
6. **Markers.** The markers appear bare, each on its own line, exactly as written above. One value per line; surrounding whitespace is ignored. They are not wrapped in comments; this file is plain Markdown so a person and a parser read the same text.
7. **Fail closed.** A repository with no FUNDING.md, more than one `[FUNDED]` block, a value other than `Yes` or `No`, `Yes` with no funder, `No` with a funder, or a funder missing a name or URL, is treated as having undisclosed funding.
8. **Not GitHub's FUNDING.yml.** GitHub's `.github/FUNDING.yml` controls the Sponsor button and is not this disclosure. If a repository has both, they must not contradict each other.
9. **Humans and machines.** This file is checked the same way by a person reading it and by a program parsing the markers, and both reach the same result.
