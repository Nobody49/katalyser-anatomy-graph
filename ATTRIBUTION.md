# Sources and attribution

## Foundational Model of Anatomy (FMA)

- **What is used:** anatomical relationships (branch of, part of, attaches to, tributary of, and others) and preferred labels for structures with an FMA identifier.
- **Release:** the FMA OBO release in Ontobee's merged FMA graph (`http://purl.obolibrary.org/obo/merged/FMA`, SPARQL endpoint `https://sparql.hegroup.org/sparql/`), retrieved 2026-08-16 (extract SHA-256 `5aad5b41ce400ca020d7ba608df0c3c198708a5c3695bedecf669330b41f0451`) and 2026-09-05 (extract SHA-256 `58c929a827198714d0502049c560137a1e7de864816f71b8f9426f9614bd7dab`). Labels were read from the same graph on 2026-10-14.
- **Licence:** Creative Commons Attribution. Bioregistry lists FMA as CC BY 4.0; Katalyser's rights record lists the OBO copy as CC BY 3.0. Either licence permits redistribution with credit.
- **Credit:** Foundational Model of Anatomy, Structural Informatics Group, University of Washington. Rosse C, Mejino JLV Jr. *A reference ontology for biomedical informatics: the Foundational Model of Anatomy.* J Biomed Inform. 2003;36(6):478–500.
- **Changes:** relationships were selected and mapped to Katalyser's predicate names. FMA's wording was not changed.

## Uberon multi-species anatomy ontology (UBERON)

- **What is used:** anatomical relationships, and preferred labels for structures that have a UBERON identifier but no FMA identifier.
- **Releases:**
  - `http://purl.obolibrary.org/obo/uberon/releases/2026-06-23/uberon.obo`, SHA-256 `7f06d8e8442008a67132a1599b652e86fe0c52d75c8d6bc5b0cc36a0031e6b3f`. Katalyser's record labels this release 2026-06-19; the file is the 2026-06-23 release, and edges.tsv carries the 2026-06-19 label.
  - `https://purl.obolibrary.org/obo/uberon/releases/2026-10-01/uberon.obo`, SHA-256 `d4751a15d7551a8414caee2628c62bf68301d567caf54ccfa3eef383ae7cbb61`.
- **Licence:** [CC BY 3.0](https://creativecommons.org/licenses/by/3.0/).
- **Credit:** Uberon, an integrative multi-species anatomy ontology. Mungall CJ, Torniai C, Gkoutos GV, Lewis SE, Haendel MA. Genome Biol. 2012;13(1):R5. Haendel MA et al. *Unification of multi-species vertebrate anatomy ontologies for comparative biology in Uberon.* J Biomed Semantics. 2014;5:21.
- **Changes:** relationships were selected and mapped to Katalyser's predicate names.

## Identifiers in `xrefs`

`xrefs` lists other identifiers that Katalyser holds for the same structure from openly licensed sources: FMA, UBERON, NCI Thesaurus (CC BY 4.0), MONDO (CC BY 4.0), Disease Ontology (CC0) and Cell Ontology (CC BY 4.0). Only the identifiers are included, never those sources' text.

## Katalyser

The relationships marked "Katalyser expert curation" and "Katalyser, derived from segmented image geometry", and the predicate definitions in `data/predicates.tsv`, are Katalyser's own work, licensed under CC BY 4.0 (see LICENSE).
