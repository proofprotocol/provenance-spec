> **DRAFT. NOT A VALID LICENSE.** Values marked UNFILLED must be completed and the file must pass `ggl.py check`.

<!-- GGL-PARAMS:BEGIN -->
```bash
# Greater Good Commercial License 1.0 PARAMETERS. Every value is REQUIRED for this license to be valid.
# LOCKED values never change once set for a Covered Work (Section I).
# Check: python3 ggl.py check <this file>
GGL_VARIANT="GGL-C-1.0"
GGL_BODY_SHA256="20c1a7422fdcc07e699e96c9f01e385644ed416944ec1bcc9e37328d235f656a"

# Licensor
LICENSOR_NAME="Nebulonium, Inc. (dba HACKERverse)"  # Legal name of the licensor (company or person)
LICENSOR_LOCATION="Castle Rock, Colorado"         # City and state or country of the licensor
COPYRIGHT_YEAR="2026"                             # Year of first publication
LICENSING_CONTACT="1proofprotocol@gmail.com"      # Email or https URL for licensing requests

# Inventor
INVENTOR_NAME="Craig Thomas Ellrod"               # LOCKED. Original inventor's full legal name (Section I)
INVENTOR_ORCID="0009-0004-1058-7666"              # LOCKED. Inventor's ORCID iD, form 0000-0000-0000-000X
INVENTOR_RECORD_DOI=""                            # LOCKED. DOI of the Zenodo Inventor Record

# Program
PROGRAM_NAME="Proof Protocol"                     # Name of the specification program
SPEC_NUMBER_PREFIX="PP-SPEC"                      # Prefix of specification numbers
ATTRIBUTION_NAMES="Nebulonium, Inc. and Proof Protocol"  # Names that attribution must carry besides the inventor (S.3)
MARKS="Proof Protocol, ProofSwarm, ProofFlock, ProofStamp, ProofRegister, HACKERverse"  # Names and marks reserved under G.4, comma separated

# Covered Work
COVERED_WORK="Proof Provenance Specification"     # Name and number of the work this copy covers
COVERED_WORK_VERSION="1.0.0"                      # Version of the covered work, x.y.z
SPEC_LICENSE="CC BY-ND 4.0"                       # Part S license for the text
OFFERED_LICENSES="GGL-C-1.0"                      # Family licenses this work is offered under, comma separated: GGL-OS-1.0, GGL-EGR-1.0, GGL-C-1.0
PATENT_SCHEDULE="PATENT-SCHEDULE.md"              # Path or URL of the Patent Schedule (P.1)
PATENT_SCHEDULE_VERSION="1"                       # Patent Schedule version number

# Commercial: Startup Tier
SMALL_BIZ_MAX_WORKERS="25"                        # Small business worker ceiling (C.4)
SMALL_BIZ_MAX_REVENUE_USD="1,000,000"             # Small business revenue ceiling in US dollars (C.4)
INFLATION_BASE_YEAR="2026"                        # Base year for CPI-U adjustment (C.4)
EVAL_DAYS="90"                                    # Free evaluation period in days (C.4)

# Commercial: Fees
REVENUE_SHARE_PCT="1"                             # Give-back share of Gross Revenue, percent (C.5)
FEE_PER_UOP_USD=""                                # Fee per Unit of Proof in US dollars (C.5)
MIN_ANNUAL_FEE_USD=""                             # Minimum annual fee in US dollars (C.5)
ANNUAL_CAP_USD=""                                 # Annual fee cap in US dollars (C.5); must be at least the minimum fee
RATES_URL=""                                      # https URL where commercial rates are published (C.8)

# Lineage
POOL_CAP_PCT="30"                                 # Most of the fee all pool shares in one ancestry may take (E.7)
LINEAGE_URL="LINEAGE.json in the provenance-spec repository"  # Where the canonical lineage file lives (E.9)

# Commercial: Terms
REPORT_DAYS="60"                                  # Days after fiscal year end to report and pay (C.7)
AUDIT_UNDERPAY_PCT="5"                            # Underpayment that shifts audit cost to the licensee (C.7)
FAIRNESS_DAYS="30"                                # Days the Licensor has to offer published terms (C.8)

# Terms
CURE_DAYS="30"                                    # Days to cure a violation (G.2)
LATE_INTEREST_PCT_MONTH="1.5"                     # Late interest, percent per month (G.3)

# Law
GOVERNING_LAW="Colorado"                          # Governing law, e.g. Colorado (G.10)
VENUE="the state or federal courts located in Colorado"  # Exclusive venue for disputes (G.10)
```
<!-- GGL-PARAMS:END -->

<!-- GGL-1.0 BODY: canonical text, do not edit below this line -->
# The Greater Good Commercial License, Version 1.0 (GGL-C-1.0)

*Fair terms for those who profit, so the public-good work stays funded.*

SPDX identifier: `LicenseRef-GGL-C-1.0`

Licensor: Nebulonium, Inc. (dba HACKERverse), Castle Rock, Colorado.

Original Inventor: Craig Thomas Ellrod, ORCID 0009-0004-1058-7666. Inventor Record: DOI [[UNFILLED: INVENTOR_RECORD_DOI]]. See Section I. This line is permanent.

Required Notice: Copyright 2026 Nebulonium, Inc. (dba HACKERverse). Licensed under the The Greater Good Commercial License 1.0. Original inventor: Craig Thomas Ellrod (ORCID 0009-0004-1058-7666), Inventor Record DOI [[UNFILLED: INVENTOR_RECORD_DOI]]. Licensing contact: 1proofprotocol@gmail.com.

---

## 0. The Greater Good License Family

| License | For | Cost |
|---|---|---|
| **GGL-OS-1.0**, Open Source | Anyone, for Software the Licensor releases as open source | Free. Share-alike. |
| **GGL-EGR-1.0**, Education, Government, and Research | Schools, governments, and research and nonprofit bodies | Free. Non-commercial. |
| **GGL-C-1.0**, Commercial | Anyone using Covered Works commercially outside the other two | Fee. Waived for small businesses. |

All three licenses share the same Section I (Original Inventor), Part S (Specification Text), Part P (Patents), Section E (Enrichment and Lineage), Section M (Contribution Markers), and Section G (General Terms), word for word. They differ only in their own Part: Part O, Part R, or Part C. This copy is **GGL-C-1.0**, and its own Part is Part C.

**Offered licenses.** Each Covered Work's declaration lists the family licenses it is offered under. You may use it under any of those whose conditions you meet. If you meet none of them, you have no license to the Covered Work beyond Part S and P.2.

**Acceptance.** By using, copying, modifying, implementing, or distributing a Covered Work, or by claiming conformance with one, you accept the terms of the license you use it under. If you do not accept them, do not do those things.

**Declaration.** Every Covered Work carries a declaration in its header or LICENSE file in this form:

```
License family: Greater Good License 1.0
Covered Work: Proof Provenance Specification, version 1.0.0
Offered under: GGL-C-1.0
Original Inventor: Craig Thomas Ellrod, ORCID 0009-0004-1058-7666
Inventor Record: DOI [[UNFILLED: INVENTOR_RECORD_DOI]]
Specification text: CC BY-ND 4.0
Patent Schedule: PATENT-SCHEDULE.md, version 1
```

---

## I. Original Inventor

**I.1 Identification.** The original inventor and author of the Covered Works is **Craig Thomas Ellrod**, identified by ORCID **0009-0004-1058-7666**. The **Inventor Record** is the Zenodo deposit at DOI [[UNFILLED: INVENTOR_RECORD_DOI]], which lists the Covered Works, their versions, and the SHA-256 hash of each published text, and is bound to the same ORCID.

**I.2 Permanent.** This identification is part of every grant in this license. No one may remove, alter, replace, or reassign it: not a licensee, a contributor, a standards body, an assignee or successor of the Licensor, or any later version of any license in the family. Assignment of rights under G.8 transfers rights, never the identification. A later version of this license that omits or changes Section I does not apply to any Covered Work.

**I.3 The Inventor Line.** Every copy, Derivative Work, translation, conformance claim, and public description of a conforming implementation must carry this line, in a reasonable place a reader will see:

```
Original inventor: Craig Thomas Ellrod (ORCID 0009-0004-1058-7666), Inventor Record DOI [[UNFILLED: INVENTOR_RECORD_DOI]]
```

For Part S, the Licensor designates the Inventor Line as the attribution required by CC BY 4.0, Section 3(a)(1)(A).

**I.4 Others get credit for what they add.** Contributors and adapters may credit their own additions next to the Inventor Line. No one else may be named, or present themselves, as the original inventor or originator of a Covered Work or of the methods it specifies.

**I.5 Evidence.** The Inventor Record, the ORCID record, the Zenodo deposit dates, and the Time Anchor and Registry bindings of each published version are the record of origin. In any dispute about origin, the earliest of these records controls.

**I.6 Patents.** Section I records authorship and origin for attribution. Inventorship and ownership of any patent are as stated in that patent and its assignment records.

---

## Part S. Specification License

**S.1 Default.** Unless its License Declaration says otherwise, the text of every Specification is licensed under the Creative Commons Attribution 4.0 International License (CC BY 4.0). Anyone may copy, share, translate, and adapt the text, including commercially, under CC BY 4.0.

**S.2 Doctrine texts.** A Specification whose License Declaration selects CC BY-ND 4.0 may be copied and shared verbatim but not adapted.

**S.3 Attribution.** Attribution under S.1 or S.2 must carry the Inventor Line (I.3), name Nebulonium, Inc. and Proof Protocol, give the specification number and version, and link to the source.

**S.4 Text only.** Part S licenses words, not inventions. As CC BY 4.0 itself states, it grants no patent or trademark rights. Implementing a Specification is governed by Part P. Use of names and marks is governed by Section G.4.

**S.5 Irrevocable.** A text released under CC BY 4.0 stays under CC BY 4.0. Nothing in this license narrows rights already granted in any earlier published version.

---

## Part C. Commercial Terms

**C.1 Who needs it.** Anyone using a Covered Work commercially who is not using it under GGL-OS-1.0 or GGL-EGR-1.0.

**C.2 Acceptance.** Commercial use outside the Startup Tier and the evaluation period requires accepting GGL-C-1.0 by a signed order form or an online acceptance that names it. Using a Covered Work commercially without doing so is still acceptance of these terms, and fees accrue from first use.

**C.3 Grant.** While you comply with Part C and your fees are paid, the Licensor grants you the right to use, copy, modify, and run the Covered Works offered under GGL-C-1.0 for any purpose; to embed the Software in your own products and distribute it inside them in object form; and to practice the Reserved Claims as embodied in the Software and in conforming implementations. Your own code stays yours and carries no share-alike obligation. Improvements to the Software itself that you distribute to others must be under GGL-C-1.0 or GGL-OS-1.0.

**C.4 Startup Tier and evaluation.** A small business that, together with all its Affiliates, had fewer than 25 workers and less than 1,000,000 USD in gross revenue last tax year, adjusted each year for US inflation (CPI-U) from 2026, pays no fee. Every other term of GGL-C-1.0 applies to it. Anyone else may evaluate the Covered Works free for 90 days.

**C.5 Fees: the give-back.** A commercial licensee outside the Startup Tier pays the Licensor each year the **greatest** of:

1. **1% of Gross Revenue** from any product or service that uses, includes, runs on, or is certified with the Software, including bundled and indirect revenue;
2. **[[UNFILLED: FEE_PER_UOP_USD]] USD per Unit of Proof** produced with the Software; or
3. **A minimum annual fee of [[UNFILLED: MIN_ANNUAL_FEE_USD]] USD.**

Total fees are capped at **[[UNFILLED: ANNUAL_CAP_USD]] USD per year** per company, Affiliates combined, except as C.6 provides. Revenue is measured before expenses, worldwide, across all Affiliates.

**C.6 Per user, not per host.** Every organization that benefits from the Software pays for its own use, once.

- **Hosting is not a loophole.** If you offer the Software, or a substantial part of its functionality, to others as a hosted service, managed service, API, marketplace listing, or platform feature, your license covers only your own internal use.
- **Your customers need their own license.** Each customer using the Software through your service must hold its own license, or you pay the C.5 fee on all revenue from that service.
- **No cap for resale.** The C.5 cap does not apply to revenue from offering the Software to others as a service.
- **Free status does not pass through.** A customer's free use does not make your service free, and your license does not make your customers' use free.
- **No double charge.** The same use is paid once. If a customer has paid the Licensor directly, you owe nothing further on that customer's use.

**C.7 Reporting.** Report and pay once a year, within 60 days of your fiscal year end. The Licensor may audit once a year at its own cost, or at yours if you underpaid by more than 5%.

**C.8 Same price for everyone.** The Licensor publishes its rates at [[UNFILLED: RATES_URL]]. Published rates paid by at least one unaffiliated customer are fair, reasonable, and nondiscriminatory by definition. If the Licensor fails to offer a commercial license on published terms within 30 days of your written request to the licensing contact, you may keep using the Software free until it does.

**C.9 Authorized use only.** You may run the Software only against systems, models, and data you own or have written permission to test.

**C.10 Where the fees go.** Fees fund the maintenance of the Covered Works, the Proof Protocol infrastructure, and the royalty pool in E.7. The Licensor publishes the pool calculation and payouts each year.

---

## Part P. Patent License

Part P lets the Licensor give specific inventions to the public good while keeping others to sustain the work that maintains the protocol.

**P.1 Patent Schedule.** The Licensor publishes a Patent Schedule with each Covered Work. It lists each patent and patent application the Licensor holds that bears on the Covered Work, and marks each claim, or group of claims, as either:

- **Contributed:** given to the public good under P.2; or
- **Reserved:** kept by the Licensor under P.3.

A claim not listed is Reserved.

**P.2 Contributed Claims.** The Licensor grants you a worldwide, royalty-free, non-exclusive license under the Contributed Claims to make, use, sell, offer for sale, import, and otherwise practice any implementation, to the extent it conforms to the Specification the claim is listed against. This license is free for everyone, including commercial users, under every license in the family.

**P.3 Reserved Claims.** No license is granted under Reserved Claims except as a family license grants it in its own Part: GGL-OS-1.0 in O.6, GGL-EGR-1.0 in R.2, and GGL-C-1.0 in C.3. The Licensor will not assert Reserved Claims against an individual for personal study, or against anyone for standards review or for citing and discussing a Specification.

**P.4 One-way ratchet.** The Licensor may move a claim from Reserved to Contributed at any time by publishing a new Patent Schedule version. A Contributed Claim is never moved back to Reserved, and the license in P.2 for it is irrevocable except under P.5.

**P.5 Defensive termination.** If you, or an Affiliate, start or join a lawsuit or proceeding claiming that a Covered Work, a conforming implementation, or the Licensor infringes a patent, every license you hold under the Greater Good License family ends on the date you file, for you and for the Affiliate that files.

**P.6 Grant-back.** If you obtain or hold a patent claim that covers a Derivative Work of the Software, or an improvement you made to a conforming implementation, you grant the Licensor and every other licensee under the Greater Good License family a worldwide, royalty-free, non-exclusive license under that claim to use it with the Covered Works. If the improvement is a Recognized Lineage Node whose terms are Reserved (E.5), the grant to the Licensor is unchanged, and other licensees receive it on that node's published price instead of royalty-free.

**P.7 No implied licenses.** No patent rights pass except as Part P states, whether by implication, estoppel, or otherwise. Publishing a Specification under Part S grants no patent license.

---

## E. Enrichment and Lineage

A Covered Work can grow. Section E lets other inventors enrich it, be named for what they add, and choose how their own portion is used, without ever changing what sits above them.

**E.1 Enrichment.** Anyone may enrich a Covered Work by adding something separable that builds on it: a method, an improvement, a profile, a test suite, or text. Each enrichment is recorded as a Lineage Node.

**E.2 Lineage Node.** A Lineage Node is a record that states: its parent nodes, by hash; the contributor's name and ORCID; the Covered Work and version it builds on; the scope of the contribution, by section, claim, and description; the SHA-256 hash of the contributed material; the contributor's terms under E.5; whether it touches a root claim (E.8); and the DOI of the node's deposit on Zenodo under the contributor's ORCID. A node's hash is the SHA-256 of its record in canonical JSON (RFC 8785), excluding the hash itself. The root node is the Inventor Record (Section I). Because every node names its parents by hash, the nodes form a hash-linked tree in which any change to any node breaks every hash below it.

**E.3 Recognition.** A node is Recognized when the contributor of each of its parent nodes has countersigned a Recognition record naming the node's hash, deposited with a DOI. A node that is not Recognized is a Fork. A Fork may be used under the terms of the nodes above it, must be labeled as a fork wherever it is named, and receives no pool share under E.7.

**E.4 Scope, and no override.** A node's terms govern only the contributor's own portion, as its scope describes. Everything a node inherits stays under the terms of the nodes above it, up to the root. No node may relax, remove, replace, or add conditions to the terms of any node above it, including Section I and the Inventor Line.

**E.5 Node terms.** Each contributor chooses one term for their portion:

- **Contributed:** free for any use, including commercial use, and royalty-free under any patent claim the contributor holds on that portion;
- **Inherit:** the same terms as its parent node; or
- **Reserved:** available on the contributor's own published price, for that portion only.

A contributor may also require their Enrichment Line (E.6) in attribution.

**E.6 Obligations stack.** Anyone using a work at a node must meet the terms of the root and of every node above it, and must carry the Inventor Line and the Enrichment Line of each Recognized node above it:

```
Enriched by: <name> (ORCID <orcid>), lineage node <first 12 hex of node hash>, Record DOI <doi>
```

No one other than the root's inventor may be named original inventor (I.4). Contributors are named as enrichers of what they added.

**E.7 Royalty pool.** A licensee under GGL-C-1.0 pays its fee once, however deep the tree. The Licensor pays each Recognized node whose terms are Contributed or Inherit the pool share that node declared, out of GGL-C-1.0 fees collected on works whose ancestry includes that node. In the ancestry of any node, the pool shares together must not exceed 30% of the fee. A Reserved node charges its own price and takes no pool share; a node takes one or the other, never both. The Licensor publishes the pool calculation and payouts each year.

**E.8 Root claims and inventorship.** A Lineage Node must state whether its contribution touches any claim of the root's patents or patent applications. A node that does is Recognized only if its contributor has assigned to the Licensor their interest in each touched root claim, by a recorded assignment cited in the node. Inventorship is decided by patent law, not by this license. E.8 decides recognition and pool eligibility.

**E.9 The lineage file.** The Licensor keeps the canonical lineage of each Covered Work at LINEAGE.json in the provenance-spec repository. Anyone may check every hash, parent link, recognition, scope, term, assignment, and pool limit in it with the published verifier.

---

## M. Contribution Markers

This section says how a Licensor marks any part of a Covered Work as contributed to a named organization, and makes everything not so marked uncontributed.

**M.1 Default: nothing is contributed.** No part of a Covered Work is contributed to any organization, standards body, consortium, foundation, project, or working group, except text, code, schemas, or other material that lies between Contribution Markers under M.2 and is listed in the Contribution Schedule under M.4. This holds whatever any other document, submission, pull request, email, meeting, membership agreement, charter, intellectual property policy, or contributor license says, including any term under which material submitted to a project is deemed contributed unless the submitter states otherwise. This section is that statement.

**M.2 Markers.** A contribution is marked by a start marker and an end marker, each on its own line, in exactly this form:

```
[CONTRIBUTED TO <orgname>]
...
[/END OF CONTRIBUTED TO <orgname>]
```

`<orgname>` is the organization's legal or registered name, written identically in both markers, case and spacing included. In source code, configuration, or any format where a bare line would break the file, each marker is placed alone inside a line comment of that format (for example `# [CONTRIBUTED TO <orgname>]`, `// [CONTRIBUTED TO <orgname>]`, or `<!-- [CONTRIBUTED TO <orgname>] -->`). Only the bracketed text is the marker; the comment syntax around it is not. In prose and documentation (Markdown, plain text) the bare form is used, so that a reader sees the marker in the rendered text; markers MUST NOT be hidden in a comment where the format displays bare lines.

**M.2a Formats without markers.** Some formats cannot carry markers reliably. In JSON, which has no comments, a contribution is declared only in the Contribution Schedule, by file path and JSON Pointer (RFC 6901) to each contributed element; the element at the pointer, with everything beneath it, is the contributed material. In YAML, markers MAY be placed in `#` comments, but YAML parsers discard comments when files are loaded and rewritten, so the Contribution Schedule entry is the authority: a YAML contribution MUST also be listed in the Schedule by file path and, where only part of the file is contributed, by the path to each contributed node. Where markers and the Schedule disagree for any format, the narrower of the two applies.

**M.3 Scope.** Everything strictly between a start marker and its matching end marker is contributed to the named organization, and to no other, on the terms the Contribution Schedule records for it. Everything outside every matched pair remains licensed under this license alone.

**M.4 Contribution Schedule.** Every contribution MUST appear in the Covered Work's Contribution Schedule, published in two forms that agree: `CONTRIBUTIONS.md` for people and `contributions.json` for machines. Each entry states the organization; the Covered Work and version; the scope, as a list of files each marked `by: markers` or `by: pointer` with the pointer or node path (M.2a); the terms of the contribution (a license name, or the identifier of a signed agreement); any Patent Schedule claims Contributed with it (Part P), by identifier, or none; the date; and the Licensor's signature. Markers naming an organization with no Schedule entry, and material in a file the Schedule entry does not list, contribute nothing. The Contribution Schedule is the companion of the Patent Schedule (Part P): the Patent Schedule says which claims are contributed, the Contribution Schedule says which text, code, and data are contributed and to whom.

**M.5 Fail closed.** A start marker without a matching end marker, an end marker without a matching start marker, markers whose organization names differ, or markers for the same organization nested inside one another, contribute nothing anywhere in the file in which they occur. Blocks for different organizations MAY nest; the inner material is then contributed to each named organization on its own Schedule terms. Blocks MUST NOT cross: a block that ends inside another block it did not start in contributes nothing.

**M.6 Who may mark.** Only the Licensor may place Contribution Markers in a Covered Work. The owner of a Recognized Lineage Node (Section E) may place them only around material within that node's own scope. Markers placed by anyone else contribute nothing.

**M.7 What a contribution does not change.** A contribution never removes or alters Section I (Original Inventor), the Inventor Line, the attribution required by Part S, or the Enrichment Lines of Section E; the contributed material carries them into the organization's work. A contribution of text or code grants no patent license unless the Schedule entry lists the Contributed claims (Part P).

**M.8 Per version.** A contribution attaches to the version of the Covered Work in which the markers appear. Removing or moving markers in a later version does not withdraw a contribution already made for an earlier version, and adding markers in a later version does not contribute the same material in earlier versions.

**M.9 Humans and machines.** Markers are plain text so that a person can see them and a machine can find them. The Licensor publishes a tool that, for any file and organization, lists the marked blocks, rejects any file in which M.5 makes the markers void, and produces a Contribution Extract containing only the contributed blocks or elements with the source file's SHA-256, the version, and the Schedule entry, so that anyone can verify that an extract matches the published source. A person reading the file and the tool reading the file MUST reach the same answer about what is contributed.

---

## G. General Terms

**G.1 Contributions.** Two kinds:

- **G.1a Repository contributions.** If you submit code, text, test cases, or other material into the Licensor's own repositories or releases, you grant the Licensor a perpetual, worldwide, royalty-free, irrevocable license to use, modify, sublicense, and relicense it under any terms, and you confirm you have the right to grant it.
- **G.1b Enrichments.** If you record a Lineage Node under Section E instead, you keep ownership of your portion and your terms under E.5 govern it, subject to E.4, E.8, and P.6.

**G.2 Fix it and you keep it.** If you are notified of a violation, your license continues if you fix it and pay any amount owed within 30 days. Otherwise it ends.

**G.3 Termination.** If your license ends, you must stop the use that needed it, and any amounts owed remain due. Late payments accrue interest at 1.5% per month or the highest rate the law allows, whichever is lower, plus reasonable costs of collection. Rights already granted under CC BY 4.0 for specification text are not affected.

**G.4 Names and marks.** This license grants no rights to the Licensor's names, logos, or trademarks, including Proof Protocol, ProofSwarm, ProofFlock, ProofStamp, ProofRegister, HACKERverse, and PP-SPEC numbers, except:

- you may state accurately that a work implements or cites a named specification; and
- you may say a product is "[Mark] Conformant" only while you hold a license under the applicable parts and the product meets that specification's conformance section.

A modified Specification text must not carry a PP-SPEC number or present itself as the Specification.

**G.5 Definitions.** **Software** means the code, compiled code, schemas, test suites, test vectors, tools, and documentation the Licensor releases as part of a Covered Work, and later versions of them. **Derivative Work** means a work based on or derived from the Software: modifications, forks, translations, ports, rewrites in another language, and models trained or tuned on it. Using the Software's outputs, results, and reports is not a Derivative Work, and a component that connects at a declared Integration Point without copying, modifying, or linking in Software code is not one. An independent implementation written from a Specification alone is not a Derivative Work of the Software; Part P governs it. **Affiliates** means any entity that controls, is controlled by, or is under common control with you; **Control** means owning most of an entity's equity or the power to direct its management. **Covered Work** means anything the Licensor releases under this license. **Gross Revenue** means all amounts invoiced or received, before any deduction; revenue from a bundle is allocated to each component at its list price. **Integration Point** means an interface a Specification declares for connecting third-party components. **Specification** means a document the Licensor publishes as part of Proof Protocol. **Unit of Proof** means the measured outcome of one adversarial technique run against a target, as defined in the applicable Specification.

**G.6 Versions.** Each release is governed by the version of this license it shipped under. The Licensor may publish new versions, and you may choose to use a release under a later version, except that Section I carries forward unchanged into every version (I.2).

**G.7 Notices.** Anyone who receives a Covered Work from you must also receive this license, the Required Notice, and the Inventor Line.

**G.8 Assignment.** The Licensor may assign this license, its rights, and fees owed under it to any affiliate or successor. You may not sublicense or transfer your license.

**G.9 No warranty.** As far as the law allows, every Covered Work is provided as is, and the Licensor is not liable for any damages arising from it.

**G.10 Governing law.** Colorado law governs this license, without regard to conflict-of-law rules. Disputes belong exclusively in the state or federal courts located in Colorado, and you consent to their jurisdiction.

**G.11 Severability.** If any part of this license is unenforceable, it is enforced to the maximum extent allowed and the rest remains in effect.

---

*GGL-C-1.0. Licensor: Nebulonium, Inc. (dba HACKERverse), Castle Rock, Colorado.*
