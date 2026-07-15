# Proof Provenance Specification

**Document ID:** PP-SPEC-011  
**Version:** 1.0  
**Status:** Published  
**License:** CC BY 4.0  
**Maintained by:** Proof Economy™ Standards Alliance (PESA)  
**Repository:** https://github.com/proofprotocol  
**Published:** 2026-07-14  

---

## Abstract

This specification defines provenance requirements for proof artifacts produced under the Proof Protocol™. Provenance is independently verifiable evidence of the origin, lineage, and custody chain of a proof artifact - who produced it, under what conditions, from what inputs, and whether it has been altered since production.

Provenance is the property that answers: "Where did this proof come from, and can I verify that independently?"

Without provenance, a proof artifact is a document. With provenance, it is evidence.

---

## Status of This Document

This document is a published specification of the Proof Protocol™. It is released under the Creative Commons Attribution 4.0 International License (CC BY 4.0). You may copy, distribute, and adapt this specification for any purpose provided attribution is given to Craig Ellrod / Nebulonium, Inc..

---

## 1. Introduction

### 1.1 The Provenance Problem

A proof artifact without provenance can be fabricated after the fact. An attacker, a vendor, or a malicious auditor can construct a document that looks like a proof, assign it a plausible timestamp, and present it as evidence. Without an independent provenance mechanism, there is no way for a third party to distinguish a genuine proof from a fabricated one.

This is not a theoretical risk. In cybersecurity, the entity being evaluated controls the environment in which evaluation occurs. Without external provenance anchoring, every benchmark result, penetration test report, and efficacy score is self-reported evidence - the entity being watched writes its own report card.

### 1.2 The Proof Protocol™ Approach

The Proof Protocol™ solves provenance through pre-execution commitment to an unpredictable external randomness source. The NIST Randomness Beacon (https://beacon.nist.gov) produces a new 512-bit random value every 60 seconds. It cannot be predicted in advance. It cannot be retroactively altered.

By committing test parameters to a NIST Beacon pulse before execution begins, the Proof Protocol™ creates a cryptographic link between the proof artifact and a specific moment in time that no party controls. If the pulse value is in the provenance record, the artifact was produced after that pulse. If execution parameters hash to the committed value, they were not altered after commitment.

This makes retroactive fabrication structurally impossible, not merely detectable.

### 1.3 Scope

This specification defines:

- Required provenance fields for a Proof Protocol™ artifact
- The pre-execution commitment mechanism
- Lineage requirements for derived artifacts
- Chain of custody requirements for proof submission
- Provenance verification procedure

This specification does not define:
- The format of the ProofBundle™ (see PP-SPEC-003)
- The ProofRegister™ API (see PP-SPEC-004)
- The Witness Protocol (see PP-SPEC-005)
- Legal attestation packaging (see PP-SPEC-010)

---

## 2. Definitions

**Provenance Record** - The structured set of fields in a proof artifact that establish its origin, lineage, and custody chain.

**Pre-Execution Commitment** - A cryptographic commitment to test parameters made before execution begins, anchored to a NIST Beacon pulse that had not yet been published at the time of commitment initiation.

**Pulse Index** - The sequential identifier of a NIST Randomness Beacon pulse, used to identify a specific 60-second window in the Beacon's output chain.

**Commitment Hash** - A SHA-256 hash of the canonical serialization of committed test parameters, recorded alongside the pulse index at commitment time.

**Lineage** - The documented chain of transformations from raw execution data to final proof artifact.

**Custody Event** - Any transfer of a proof artifact from one party to another, or any transformation applied to it.

**Origin Timestamp** - The timestamp of the NIST Beacon pulse to which execution was committed. This is the earliest possible time at which the proof artifact could have been produced.

**Proof Record ID (PCID)** - The globally unique identifier assigned to a proof record by ProofRegister™ upon submission. See PP-SPEC-004.

---

## 3. Provenance Record Requirements

### 3.1 Required Fields

A conformant provenance record MUST contain the following fields:

| Field | Type | Description |
|-------|------|-------------|
| `schema_version` | string | Provenance schema version. Current: `"1.0"` |
| `document_id` | string | `"PP-SPEC-011"` |
| `commitment.pulse_index` | integer | NIST Beacon pulse index at time of pre-execution commitment |
| `commitment.pulse_timestamp` | ISO 8601 datetime | Timestamp of the committed pulse |
| `commitment.pulse_value` | hex string (128 chars) | 512-bit output value of the committed pulse |
| `commitment.commitment_hash` | hex string (64 chars) | SHA-256 of canonical serialization of committed parameters |
| `commitment.committed_at` | ISO 8601 datetime | Timestamp at which commitment was recorded by the committing party |
| `execution.start_time` | ISO 8601 datetime | Time at which execution began, must be after `commitment.pulse_timestamp` |
| `execution.end_time` | ISO 8601 datetime | Time at which execution concluded |
| `execution.operator` | string | Identity of the party conducting execution |
| `witness.identity` | string | Identity of the independent witness (see PP-SPEC-005) |
| `witness.attestation_hash` | hex string (64 chars) | SHA-256 of the witness attestation document |
| `artifact.bundle_hash` | hex string (64 chars) | SHA-256 of the ProofBundle™ (PP-SPEC-003) produced |
| `artifact.produced_at` | ISO 8601 datetime | Timestamp at which the ProofBundle™ was assembled |
| `custody` | array | Ordered list of custody events (see 3.2) |

### 3.2 Custody Event Fields

Each entry in the `custody` array MUST contain:

| Field | Type | Description |
|-------|------|-------------|
| `event_type` | string | One of: `PRODUCED`, `TRANSFERRED`, `SUBMITTED`, `CERTIFIED`, `DELIVERED` |
| `timestamp` | ISO 8601 datetime | Time of the custody event |
| `from_party` | string | Identity of transferring party (null for PRODUCED) |
| `to_party` | string | Identity of receiving party |
| `artifact_hash` | hex string (64 chars) | SHA-256 of the artifact at time of this event |
| `notes` | string | Optional. Human-readable description of the event |

### 3.3 Optional Fields

| Field | Type | Description |
|-------|------|-------------|
| `anchor.proofregister_id` | string | Proof Record ID (PCID) assigned by ProofRegister™ |
| `anchor.proofregister_pulse_index` | integer | NIST Beacon pulse index at time of ProofRegister™ submission |
| `anchor.blockchain_tx` | string | Optional blockchain transaction hash (supplemental, not authoritative) |
| `lineage` | array | Ordered list of transformation events applied to raw data |
| `related_artifacts` | array | PCIDs or hashes of related proof artifacts |

---

## 4. Pre-Execution Commitment Procedure

### 4.1 Purpose

The pre-execution commitment procedure creates an unforgeable link between the proof artifact and a specific moment in time. It is the mechanism that makes retroactive fabrication structurally impossible.

### 4.2 Steps

**Step 1: Retrieve current NIST Beacon pulse**

Query the NIST Randomness Beacon API:

```
GET https://beacon.nist.gov/beacon/2.0/pulse/last
```

Record the `pulseIndex`, `timeStamp`, and `outputValue` from the response.

**Step 2: Serialize committed parameters**

Construct the canonical serialization of the parameters to which execution is being committed. This MUST include at minimum:

- Test suite identifier
- Target system identifier
- Operator identity
- Witness identity
- Pulse index being committed to

Canonical serialization format: JSON with keys sorted alphabetically, no whitespace, UTF-8 encoding.

**Step 3: Compute commitment hash**

```
commitment_hash = SHA-256(canonical_serialization)
```

**Step 4: Record commitment**

Record the pulse index, pulse timestamp, pulse output value, commitment hash, and committed_at timestamp in the provenance record. This record must be created before execution begins.

**Step 5: Execute**

Begin execution. The `execution.start_time` must be after `commitment.pulse_timestamp`.

### 4.3 Verification

A verifier can confirm pre-execution commitment by:

1. Querying the NIST Beacon for the recorded pulse index: `GET https://beacon.nist.gov/beacon/2.0/pulse/{index}`
2. Confirming the returned `outputValue` matches `commitment.pulse_value`
3. Recomputing SHA-256 of the canonical parameter serialization and confirming it matches `commitment.commitment_hash`
4. Confirming `execution.start_time` is after `commitment.pulse_timestamp`

If all four checks pass, the proof was committed before execution and could not have been fabricated retroactively.

---

## 5. Lineage Requirements

### 5.1 Definition

Lineage documents the chain of transformations from raw execution output to the final ProofBundle™. Each transformation that materially affects the artifact content must be recorded.

### 5.2 Lineage Event Fields

| Field | Type | Description |
|-------|------|-------------|
| `step` | integer | Sequential step number |
| `transformation` | string | Human-readable description of the transformation |
| `input_hash` | hex string (64 chars) | SHA-256 of the input artifact |
| `output_hash` | hex string (64 chars) | SHA-256 of the output artifact |
| `performed_by` | string | Identity of the party performing the transformation |
| `timestamp` | ISO 8601 datetime | Time of transformation |

### 5.3 Required Lineage Steps

At minimum, the following lineage steps MUST be recorded:

1. Raw execution output → parsed proof records
2. Parsed proof records → ProofBundle™ assembly
3. ProofBundle™ → ProofRegister™ submission (if submitted)

---

## 6. Provenance Verification

A proof artifact's provenance is verified by a third party as follows:

1. **Locate the provenance record.** It is embedded in the ProofBundle™ or available via ProofRegister™ at the PCID.

2. **Verify the NIST Beacon commitment.** Query the Beacon for the recorded pulse index. Confirm the output value matches. Recompute the commitment hash. Confirm execution started after the pulse.

3. **Verify the artifact hash chain.** Recompute SHA-256 of the ProofBundle™ and confirm it matches `artifact.bundle_hash`. Trace custody events and confirm hashes are consistent.

4. **Verify witness attestation.** Recompute SHA-256 of the witness attestation document and confirm it matches `witness.attestation_hash`. Confirm witness identity is independent of operator (see PP-SPEC-005).

5. **Confirm ProofRegister™ anchor (if present).** Query ProofRegister™ at the PCID. Confirm the stored record matches.

If steps 1–4 pass, provenance is verified. Step 5 provides an additional independent anchor but is not required for provenance verification.

---

## 7. Conformance

A proof artifact is conformant with PP-SPEC-011 if:

- Its provenance record contains all required fields from Section 3.1
- The pre-execution commitment procedure in Section 4 was followed
- The NIST Beacon pulse recorded predates `execution.start_time`
- The commitment hash is verifiable by any third party following Section 4.3
- The custody array contains at minimum a `PRODUCED` event

---

## 8. Relationship to Other Specifications

| Specification | Relationship |
|---------------|-------------|
| PP-SPEC-001 | PP-SPEC-011 implements the provenance requirements of the core Proof Protocol™ |
| PP-SPEC-003 | The ProofBundle™ embeds or references the PP-SPEC-011 provenance record |
| PP-SPEC-004 | ProofRegister™ stores and serves provenance records alongside proof records |
| PP-SPEC-005 | Witness identity requirements referenced in Section 3.1 |
| PP-SPEC-008 | NIST Beacon anchoring mechanism used by the commitment procedure |
| PP-SPEC-010 | Legal attestation package includes the provenance record |

---

## 9. Reference Implementation

The reference implementation of the pre-execution commitment procedure is the Pipelock v3.0.0 ProofStamp™ certification run:

- **Proof Record ID:** PR-2026-00028  
- **NIST Beacon Pulse Index:** 1852788  
- **Block:** 29  
- **Execution date:** 2026-07  
- **Result:** 164 applicable cases, 99.2% containment, 100% detection, 4.5% FP rate  

This run predates any published standard defining provenance requirements for AI security verification. It is the first publicly documented proof artifact conformant with the requirements of this specification.

---

## 10. Authors

Craig Ellrod, Founder & CEO, Nebulonium, Inc. (d/b/a HACKERverse)  
Castle Rock, Colorado  
2026-07-14

---

*CC BY 4.0 - Attribution to Craig Ellrod / Nebulonium, Inc. required.*
