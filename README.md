# CTS Demonstration Corpus

A CTS corpus containing a variety of texts, editions, translations, and exemplars.

## Contents

- A TextInventory
- A Configuration File
- An XML Directory
- A Tabulated-Files Directory
- A TTL-Directory

## Texts

This demonstration corpus includes a selection of Greek and Latin texts, and some English translations:

- Herodotus, *Histories* (Greek and English)
- Homer, *Iliad* (Greek)
- Plutarch, *Life of Pericles* (Greek)
- Vergil, *Aeneid* (Latin)
- Ptolemy, *Geography* (Greek)

This corpus also includes to *aligned translations* one of the *Iliad* and one of the *Aeneid*. Poetic texts, canonically cited by poetic line, are difficult to work with in translation. These aligned translations demonstrate one method for implementing translations of poetic texts that remain citable according to the citation scheme of the original poem.

## Inventories

- The `inventory.xml` file is the CTS TextInventory cataloging the texts of this corpus. It valdates to `schemas/cts/TextInventory.rng`.
- The `citationconfig.xml` file provides information that the [CITE Manager](https://github.com/cite-architecture/citemgr) utility uses to process the XML files into tabular files and RDF statements. It validates to `schemas/cts/CitationConfiguration.rng`.

All texts in the corpus are catalogued in `inventory.xml`. The aligned translations are *not* included in `citationconfig.xml`, because they were not processed with CITE Manager.

## XML Files

The `XML` directory contains editions of the texts, valid according to the TEI P5 schema.

## Tabulated Files

Because CTS is based on a model of "text" as an "ordered hierarchy of citation objects", it is possible to instantiate a text differently for different purposes. The `Tabulated` directory contains transformations of the XML texts. These files contain one line for each citation-unit of the text. Each line contains records capturing citation-hierarchy, sequence, and text-content, delimited by the '#' character.

## TTL-RDF

The `TTL-RDF` directory contains another expression of the texts in this archive, this time as a sequence of RDF statements describing every text in the corpus.

- `cts-basic.ttl`. This is an RDF expression built from the tabular files in the `Tabulated` directory.
- `phi0690-phi003-alignedEng-RDF.ttl`. This is an RDF expression of Williams' translation of Vergil's *Aeneid*, processed to allow chunks of the translation to align with canonical citations in the Latin text.
- `tlg0012-tlg001-fuEng-RDF.ttl`. This is an RDF expression of Butler's English translation of the *Iliad*, processed to allow chunks of the translation to align with canonical citations in the Greek text.
- `cts.ttl`. This is a concatenation of the three files, above.


