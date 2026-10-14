# Sources and attribution

## Foundational Model of Anatomy (FMA)

- **What is used:** anatomical relationships (branch of, part of, attaches to, tributary of, and others) and preferred labels for structures with an FMA identifier.
- **Release:** the FMA OBO release in Ontobee's merged FMA graph (`http://purl.obolibrary.org/obo/merged/FMA`), retrieved 2026-08-16 and 2026-09-05. Labels were read from the same graph on 2026-10-14.
- **Licence:** Creative Commons Attribution. Bioregistry lists FMA as CC BY 4.0; Katalyser's rights record lists the OBO copy as CC BY 3.0. Either licence permits redistribution with credit.
- **Credit:** Foundational Model of Anatomy, Structural Informatics Group, University of Washington. Rosse C, Mejino JLV Jr. *A reference ontology for biomedical informatics: the Foundational Model of Anatomy.* J Biomed Inform. 2003;36(6):478–500.
- **Changes:** relationships were selected and mapped to Katalyser's predicate names. FMA's wording was not changed.

## Uberon multi-species anatomy ontology (UBERON)

- **What is used:** anatomical relationships, and preferred labels for structures that have a UBERON identifier but no FMA identifier.
- **Releases:** 2026-06-19 (`http://purl.obolibrary.org/obo/uberon/releases/2026-06-23/uberon.obo`) and 2026-10-01 (`https://purl.obolibrary.org/obo/uberon/releases/2026-10-01/uberon.obo`).
- **Licence:** [CC BY 3.0](https://creativecommons.org/licenses/by/3.0/).
- **Credit:** Uberon, an integrative multi-species anatomy ontology. Mungall CJ, Torniai C, Gkoutos GV, Lewis SE, Haendel MA. Genome Biol. 2012;13(1):R5. Haendel MA et al. *Unification of multi-species vertebrate anatomy ontologies for comparative biology in Uberon.* J Biomed Semantics. 2014;5:21.
- **Changes:** relationships were selected and mapped to Katalyser's predicate names.

## Identifiers in `xrefs`

`xrefs` lists other identifiers that Katalyser holds for the same structure from openly licensed sources: FMA, UBERON, NCI Thesaurus (CC BY 4.0), MONDO (CC BY 4.0), Disease Ontology (CC0) and Cell Ontology (CC BY 4.0). Only the identifiers are included, never those sources' text.

## Katalyser

The relationships marked "Katalyser expert curation" and "Katalyser, derived from segmented image geometry", and the predicate definitions in `data/predicates.tsv`, are Katalyser's own work, licensed under CC BY 4.0 (see LICENSE).
