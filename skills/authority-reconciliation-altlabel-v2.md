# SEKO Skill: Authority Reconciliation for Alternative Labels

Version: 1.1

---

# Purpose

Determine whether each `skos:altLabel` of a SEKO concept genuinely denotes the same musical instrument by comparing authoritative external sources and documented usage.

The workflow produces evidence supporting editorial decisions to:

- retain an alternative label,
- move it to another concept,
- remove it,
- or postpone the decision pending further research.

This workflow is intended for multilingual musical instrument concepts, especially inherited vocabularies and historical terminology.

---

# Principle

Two different questions must always be answered separately.

## A. Usage evidence

Has this label actually been used for the instrument?

## B. Concept identity

Does the label denote the same musical instrument as the SEKO concept?

A label may occur in Finnish collections while actually referring to another instrument.

Therefore usage alone is never sufficient evidence for concept identity.

---

# When to use

Use this workflow whenever

- a concept contains numerous `skos:altLabel`s;
- labels originate from several languages;
- inherited labels have uncertain provenance;
- concepts are mapped to external authority files;
- editorial decisions require documented evidence.

Typical cases include

- Indian instruments
- African instruments
- Indigenous instruments
- Historical instruments
- Folk instruments with numerous regional names

---

# Search order

## A. Finnish documentary evidence

### 1. Finna

Search the exact label.

If necessary also search

- transliteration variants
- diacritic-free variants
- historical spellings

Record

- number of hits (approximate if necessary)
- one representative Finna record
- original publication or collection
- observations about how the label is used

The representative record should allow another editor to verify the original source.

---

### 2. Melinda (optional)

Use when additional Finnish bibliographic evidence is needed.

---

# B. International authority sources

Search in the following order.

1. Wikidata
2. MIMO Instrument Thesaurus
3. Getty AAT
4. Library of Congress (LCMPT/LCSH)
5. Grove Music Online

Record persistent identifiers whenever available.

---

# C. Scholarly sources

If authority files are insufficient, consult

- ethnomusicological literature
- museum databases
- scholarly books
- peer-reviewed articles

General web pages should only be used when no better source exists.

---

# Reconciliation procedure

For every alternative label

1. Verify language.
2. Search Finna.
3. Search authority sources.
4. Record all identifiers.
5. Compare concepts.
6. Decide whether the authority concept matches the SEKO concept.
7. Record the editorial recommendation.
8. Document the evidence.

Never assume two labels denote the same concept because they resemble one another.

---

# Reconciliation table

| Label | Language | Finna | Representative record | Original source | Wikidata | MIMO | Getty AAT | LCMPT/LCSH | Grove | Same instrument? | Recommended SEKO action | Confidence | Notes |
|-------|----------|-------|-----------------------|-----------------|----------|------|------------|-----------|-------|------------------|-------------------------|------------|-------|

---

# Recording identifiers

Whenever possible record persistent identifiers rather than labels.

Examples

- Wikidata QID
- Getty AAT ID
- MIMO identifier
- Library of Congress URI

These identifiers provide reproducible evidence.

---

# Decision values

## Same instrument?

Use only one value.

- Yes
- No
- Ambiguous
- Unverified

### Yes

Authority sources identify the same instrument.

### No

Authority sources identify another instrument.

### Ambiguous

Different sources or language communities use the label for different instruments.

### Unverified

Insufficient reliable evidence.

---

# Recommended SEKO action

Choose one.

- Keep as `skos:altLabel`
- Move to another concept
- Remove
- Needs further research

---

# Confidence

Assess the evidence.

- High
- Medium
- Low

Confidence depends on

- number of independent authority sources
- agreement between sources
- quality of evidence

---

# Editorial principles

## Evidence first

Never retain or remove a label without evidence.

---

## Usage is not identity

Finding a label in Finna demonstrates documented use.

It does **not** prove that the label denotes the same instrument.

---

## Verify independently

Treat every label as an independent research task.

---

## Prefer persistent identifiers

Whenever possible record

- QIDs
- URIs
- AAT IDs
- MIMO IDs

instead of only textual labels.

---

## Record disagreements

If sources disagree, record the disagreement.

Do not force a conclusion.

---

## Record provenance

Always identify the authority or publication supporting each conclusion.

---

# Output

The workflow produces

1. a reconciliation table;
2. evidence supporting every editorial decision;
3. labels to retain;
4. labels to move;
5. labels to remove;
6. labels requiring additional research.

---

# Expected benefits

The workflow

- improves semantic precision;
- documents Finnish usage;
- improves interoperability with Wikidata;
- improves interoperability with MIMO;
- improves interoperability with Getty AAT;
- improves interoperability with Library of Congress vocabularies;
- creates transparent editorial documentation;
- provides reproducible evidence for GitHub issues.

---

# Typical workflow

For a concept with many alternative labels

1. Identify language.
2. Search Finna.
3. Record a representative Finnish source.
4. Search international authority files.
5. Record identifiers.
6. Compare concepts.
7. Produce editorial recommendations.
8. Update SEKO.
9. Document the evidence in the related GitHub issue.

---

# Relationship to other SEKO editorial skills

This workflow complements the

**SEKO Terminology Comparison and Recommendation**

workflow.

Terminology Comparison answers

> Which term should become the preferred label?

Authority Reconciliation answers

> Do these labels actually denote the same instrument?

The two workflows are intended to be used together during ontology maintenance.
