# Katalyser Anatomy Graph

A one-time, read-only snapshot of the openly licensed part of the anatomy graph behind [Katalyser](https://katalyser.com), a medical-education platform. It is published to show the graph, not for editing: there are no updates, issues or pull requests.

**Browse it:** <https://nobody49.github.io/katalyser-anatomy-graph/>. Search a structure and follow its connections.

| | |
|---|---|
| Snapshot | 14 October 2026 |
| Structures | 3,151 |
| Relationships | 4,221 |
| Domain | Human gross anatomy: arterial, venous and nervous trees, partonomy, body systems, attachments, blood supply, and spatial relations |

## What is in it

Every relationship is a statement made by a named source:

| Source | Relationships |
|---|---|
| FMA, OBO release (retrieved via Ontobee, 2026-08-16 and 2026-09-05) | 3,832 |
| UBERON, releases 2026-06-23 (recorded by Katalyser as 2026-06-19) and 2026-10-01 | 412 |
| Katalyser expert curation (parent vessels for branches the sources leave under a grouping concept) | 65 |
| Katalyser, derived from segmented image geometry (spatial relations measured on segmented volumes) | 34 |

A relationship backed by more than one source counts once per source, so the column adds up to more than 4,221.

| Predicate | Reads as | Relationships |
|---|---|---|
| BRANCH_OF | branches from / gives rise to | 1,748 |
| REGIONAL_PART_OF | is a region of / is divided into | 800 |
| SYSTEMIC_PART_OF | belongs to / includes the organ | 683 |
| CONSTITUTIONAL_PART_OF | makes up / is made of | 471 |
| ATTACHES_TO | attaches to / attachment of | 171 |
| SUPPLIES | supplies / supplied by | 105 |
| TRIBUTARY_OF | drains into / is drained by | 89 |
| IS_A | is a kind of / kinds of it include | 75 |
| DRAINS_INTO | drains into / drained by | 29 |
| SUPERIOR_TO, ANTERIOR_TO, MEDIAL_TO, ADJACENT_TO | spatial | 34 |
| CONTINUOUS_WITH | continuous with (symmetric) | 12 |
| INDIRECTLY_SUPPLIES | indirectly supplies | 4 |

Full definitions are in `data/predicates.tsv`.

## What is not in it

This is a subset. Katalyser's working graph also draws on sources whose licences do not allow redistribution, such as content obtained through the UMLS Metathesaurus. Every relationship supported only by such a source has been left out, and so has every structure without an openly licensed identifier and name. There is no learner data of any kind.

## Known limitations

This snapshot reproduces what the sources state, mapped to Katalyser's predicate names. It has not been reviewed edge by edge. An external audit on 14 October 2026 found the following, and Katalyser is correcting them in its working graph. The snapshot itself is frozen.

- **`BRANCH_OF` mixes direct origin with ancestry.** 178 of the 1,560 structures with a `BRANCH_OF` edge have more than one parent. Some parents are the direct origin and some are further upstream: the radial artery is recorded as branching from both the brachial artery and the subclavian artery. 82 `BRANCH_OF` edges point at a whole ("Systemic arterial tree") rather than a vessel. Do not read a `BRANCH_OF` edge as "arises directly from" without checking for a shorter path.
- **Confluences and nerve roots are recorded as branching.** The basilar artery is recorded as a branch of both vertebral arteries, which actually join to form it. The long thoracic nerve is recorded as a branch of its own C5, C6 and C7 roots (3 edges).
- **Some `IS_A` edges point at grouping classes.** 8 of the 75 `IS_A` edges have FMA classes named "Branch of …" or "Tributary of …" as their object, e.g. popliteal vein IS_A "Tributary of deep femoral vein". These are groupings, not kinds.
- **`CONSTITUTIONAL_PART_OF` follows FMA's broader usage.** FMA also uses it for structures contained in a region (e.g. median nerve in the wrist). That is broader than "what the whole is made of".
- **`CONTINUOUS_WITH` is symmetric.** One pair (sigmoid colon and rectum) is stored in both directions.
- **`TRIBUTARY_OF`** has the same multi-parent pattern as `BRANCH_OF` (10 of 76 structures).
- **Coverage.** Relationships available only under non-redistributable licences are excluded, including all innervation. The result is 115 disconnected components (the largest has 2,728 structures), and 1,885 structures have only one relationship. Pathways such as the brachial plexus are therefore incomplete here.
- **Types.** Every structure has the coarse type `ANATOMICAL_STRUCTURE`.
- **Provenance granularity.** `sources` lists the releases that state an edge, not the individual source assertion.

## Files

| File | Contents |
|---|---|
| `data/nodes.tsv` | `id` (FMA or UBERON CURIE), `label`, `label_source`, `type`, `xrefs` (other open identifiers for the same structure) |
| `data/edges.tsv` | `subject`, `subject_label`, `predicate`, `object`, `object_label`, `sources` |
| `data/predicates.tsv` | Each predicate's reading in both directions, whether it is directional and transitive, its count and its definition |
| `data/graph.json` | The same graph in one file, as used by `index.html` |
| `index.html` | A small browser for the graph (uses Cytoscape.js from cdnjs) |

An edge reads **subject — predicate → object**. For example, `FMA:50040 Left coronary artery — BRANCH_OF → FMA:3736 Ascending aorta` reads "the left coronary artery branches from the ascending aorta".

Names are the sources' own preferred labels: FMA's for structures with an FMA identifier, otherwise UBERON's.

## Licence and credit

- The upstream statements and labels remain under their sources' licences: FMA (CC BY) and UBERON (CC BY 3.0). See [ATTRIBUTION.md](ATTRIBUTION.md).
- Katalyser's own contributions (the curated and geometry-derived relationships, the predicate definitions, and the selection and arrangement of this compilation) are licensed under [CC BY 4.0](LICENSE).

Please cite as: *Katalyser Anatomy Graph, snapshot of 14 October 2026*, with the source credits in ATTRIBUTION.md.
