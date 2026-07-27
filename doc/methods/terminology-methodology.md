# SEKO Terminology Assessment and Recommendation Methodology (TASM)

**Version:** 1.0  
**Project:** SEKO – Multilingual Ontology of Musical Instruments  
**Status:** Working methodology

---

# Purpose

This methodology is used whenever two or more Finnish terms compete as the preferred translation or label for a Hornbostel–Sachs class, musical instrument concept, structural feature or organological term.

Its purpose is **not** to produce a literal translation from English, but to select the Finnish term that best serves the intended use of the SEKO ontology.

SEKO prefers established Finnish instrument names and instrument group names. General organological terms are used only when they are necessary for understanding the classification structure or when there is no established Finnish name.

The methodology produces a documented recommendation that can be attached to:

- GitHub issues
- editorial decisions
- ontology documentation
- release notes
- terminology reports

---

# Primary Design Goals

SEKO is intended primarily for

1. **Description of music collections in libraries**
   - books
   - scores
   - sound recordings
   - audiovisual material

2. **Description of musical instruments in museums and archives**

3. **Information retrieval**
   - multilingual searching
   - linked data
   - mappings to external vocabularies
   - exploration of instruments, cultures, regions and history

4. **Musicological and organological research**

The preferred Finnish term should therefore optimize **findability, usability and conceptual precision**, not merely linguistic similarity with the English original.

---

# Principles

## 1. Use existing Finnish terminology whenever possible

Existing Finnish terminology is preferred over newly invented words.

Do not create new terms unless no established Finnish equivalent can be found.

---

## 2. Prefer actual usage over literal translation

If established Finnish usage differs from the wording of the English Hornbostel–Sachs text, the established Finnish usage is normally preferred.

Literal translations should only be used when no accepted Finnish terminology exists.

---

## 3. Preserve organological meaning

The selected term must describe the same structural or functional concept as the original Hornbostel–Sachs definition.

A familiar but technically incorrect term should not be preferred.

---

## 4. Produce user-oriented ontology-friendly labels

Preferred labels should be the terms that Finnish users naturally employ when describing, cataloguing or searching for musical instruments. 

Scientific umbrella terms should be used only where no established Finnish instrument-class term exists.

The preferred labels should

- be understandable without hierarchy context
- work as standalone labels in web interfaces
- be suitable for indexing and searching
- be linguistically natural Finnish

---

# Evaluation Criteria

Each candidate term is evaluated according to the following criteria.

## A. Library description (highest priority)

Questions

- Is the term understandable for cataloguers?
- Has it been used in Finnish bibliographic description?
- Does it correspond to current library terminology?

Sources

- Finto
- Finna
- Melinda
- ARTO
- Finnish library vocabularies

Weight

★★★★★

---

## B. Museum and archive documentation

Questions

- Is the term used in museum collections?
- Does it occur in instrument catalogues?
- Is it understandable for museum professionals?

Sources

- Finna
- Museovirasto
- Museum catalogues
- Instrument museum databases

Weight

★★★★★

---

## C. Finnish musicological literature

Questions

- Does the term occur in scholarly publications?
- Is it used consistently?
- Is it preferred over competing alternatives?

Sources

- JYX
- Helda
- Doria
- Theseus
- dissertations
- scholarly articles

Weight

★★★★☆

---

## D. Teaching literature

Questions

- Is the term used in textbooks?
- Is it used in instrument guides?
- Is it understandable for students?

Weight

★★★★☆

---

## E. Linguistic quality

Evaluate

- readability
- morphology
- consistency
- ease of inflection
- clarity

Weight

★★★☆☆

---

## F. Consistency within Hornbostel–Sachs

The preferred term should fit the surrounding hierarchy.

Example

- lieriöporauksiset
- kartioporauksiset

should form a consistent pair.

Weight

★★★★☆

---

## G. International interoperability

Questions

Can the concept be mapped unambiguously to

- Hornbostel–Sachs
- MIMO
- Wikidata
- other linked-data vocabularies

Weight

★★★☆☆

## H. User-oriented terms (very high weight)

Questins

Which terms a library user uses for searching an instrument?
Which terms a museum cataloger uses for desribing it?
Which term is used for it in the Finnish music literature?
Is the more comon scientific term unfamiliar for th user?

Weight

★★★★★

---

# Source Priority

The following order should normally be used.

1. Finnish scholarly literature
2. Finnish dissertations
3. Finnish textbooks
4. Library vocabularies
5. Museum catalogues
6. Finnish dictionaries
7. General Finnish usage

International sources are used primarily for conceptual clarification, not for selecting Finnish terminology.

---

# Research Procedure

For every candidate term:

1. Search all relevant Finnish sources.

2. Record every significant occurrence.

3. Compare competing terms.

4. Evaluate each term using the criteria above.

5. Recommend one preferred term.

---

# Documentation Format

Each evaluation should contain the following sections.

## 1. Problem

Describe the competing terms.

Example

- kartioporainen
- kartioporauksinen

---

## 2. Sources

List all consulted sources.

---

## 3. Usage Examples

| Term | Source | Publication | Year | Page | Context |
|------|--------|-------------|------|------|---------|

---

## 4. Usage Analysis

Discuss

- frequency
- consistency
- context
- variations

---

## 5. Linguistic Assessment

Evaluate

- naturalness
- terminology
- morphology

---

## 6. Organological Assessment

Does the term correctly describe the Hornbostel–Sachs concept?

---

## 7. Ontology Assessment

Evaluate

- standalone usability
- indexing
- searchability
- multilingual interoperability

---

## 8. Recommendation

State the preferred term.

---

## 9. Justification

Explain why this term is preferred.

Support the recommendation with references.

---

## 10. Alternative Labels

If appropriate, recommend

- skos:altLabel
- skos:hiddenLabel

for search purposes.

---
## Type instrument test

For each H-S class look for 3 or 5 instruments in in the class and as
- does the class label fit naturally to all these instruments?
- Does the class label lead to a wrong conclusion with an imporant member of the group?
- If the class label does not fit well to these instrments, it is a strong case to consider aonther solution.

# Deliverables

Each terminology study should produce

- a recommended preferred label
- documented evidence
- bibliographic references
- rationale
- alternative labels (if needed)

The report should be suitable for direct inclusion in

- GitHub issues
- editorial documentation
- ontology release documentation

without further editing.

---

# General Rule

**Never invent Finnish terminology if reliable Finnish usage can be demonstrated.**

When no established Finnish term exists, propose the most natural Finnish equivalent and clearly state that it is a new editorial recommendation rather than an established term.
