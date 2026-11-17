# BV-BRC 3.60: Changes to Segmented Viral Genome Data

**Documentation status:** Draft for release review  
**Release context:** 3.60.21 (supersedes 3.59.14); release notes prepared November 16, 2026  
**Audience:** Researchers working with segmented viral genomes; BV-BRC support and training teams

> **Review note:** This document combines the supplied 3.60 release notes with the segmented-genome transition meeting notes. Features listed as shipped are described as reported in the release notes, **not independently verified in the deployed production environment**. Migration and deprecation details are still unresolved.

## Overview

BV-BRC is updating how segmented viral genome data are organized and accessed. Historically, individual segments could be represented as separate genome records. The new organization associates segments with genome records while preserving access to individual sequences. This is relevant to influenza viruses and other segmented viruses, including groups with incomplete sequence collections.

The 3.60 release also updates influenza searching, downloads, saved searches, and analysis services. These changes affect how users locate, select, export, and analyze genome- and sequence-level data.

## 1. Genome records and associated sequences

A genome record may have multiple associated sequences corresponding to viral segments. Users should inspect the **Genomes** and **Sequences** views to understand the parent record and its individual segment accessions. A genome may have fewer than the expected number of segments represented in the available data.

**Important distinction:** A genome with the expected number of segment labels is not necessarily a genome whose individual sequences are complete or whose quality has been verified. Genome-level completeness, sequence-level Complete/Partial status, and quality flags must be interpreted separately.

**Screenshot placeholder:** Verified genome Overview and Sequences tabs showing genome ID, segment labels, accessions, and sequence status. Do not use records with reported duplicate segment labels as the canonical example.

## 2. Finding segmented viral data

The 3.60 release notes report improvements to influenza searching, including selecting multiple segments and requiring that a genome contain **all selected segments**. Users can also restrict the returned sequences to selected segments. Sequence Complete/Partial status can be filtered independently of parent-genome completeness, alongside sequence-length criteria.

Search result tables can display parent-genome metadata on sequence and protein results. Attributes used in a search are automatically added as result columns. For Orthomyxoviridae and descendants, **Segment** is displayed rather than CDS; influenza B displays **Lineage**.

See [Flu Corner: Searching and Working with Influenza Genomes and Segments](BV_BRC_Flu_Corner_Influenza_Search_and_Segments_3.60_DRAFT.md) for a workflow-oriented guide.

## 3. Genome groups and sequence groups

Genome groups and sequence selections serve different analytical purposes. The 3.60 release notes confirm that **Genome Tree and MSA accept segmented genome groups**, with segment selection for each added genome group. The shared segment controls apply to every added group.

**Not yet confirmed by the release notes:**

- Whether existing single-segment genome groups are preserved unchanged, automatically migrated, or require user action
- Whether old and new genome identifiers can coexist in the same group
- Whether users can convert old genome groups into sequence groups
- Whether legacy groups can be updated by replacing old genome IDs with mapped new IDs
- Whether prior analysis results and bookmarks remain reproducible after deprecated records are removed

Do not promise group migration or backward compatibility until the release team confirms behavior and a tested procedure.

## 4. Downloads and exports

BV-BRC 3.60 introduces a **unified three-step download wizard** from the main data tables:

1. Choose the data type.
2. Choose which records to include.
3. Configure format options.

The download button above the table and **DOWNLOAD** in the green action bar open the same wizard. With no rows selected, the download covers the whole result set. **Copy curl** generates a command corresponding to the configured data type, records, and columns.

FASTA downloads allow users to select header fields, configure delimiters, or enter a custom format string. Header formats can be saved in the workspace and reused. The interface validates format strings and previews the resulting header. The available fields come from the relevant API collection.

**Release verification:** Retest header customization, record scope, filtered results, and cURL parity in the deployed release; earlier meeting notes reported problems in these areas.

## 5. Saved searches

The **SAVE** action is available from the green action bar on results tables, whether or not rows are selected. Saved searches are stored in the user's workspace and are accessible through **Workspaces** across browsers. They retain up to 1,000 selected rows and re-highlight matching rows when reopened; if rows no longer match, the interface reports the count. The saved criteria appear in the results header. Influenza saved searches offer **Edit Search**.

**Distinguish saved searches from genome groups:** A saved search stores query/results context; it should not be described as automatically migrating genome IDs in an existing group.

## 6. Analysis service compatibility

- **Genome Tree:** Accepts segmented genome groups and supports segment selection per group.
- **Multiple Sequence Alignment (MSA):** Accepts segmented genome groups; fixes include genome-ID parsing, large uploaded FASTA validation, and navigation for segmented reports.
- **Archaeopteryx:** Updated to **3.28**; tree labels and control icons were corrected, and trees rebuild when input changes.
- **Viral Genome Tree:** Column compression and label wrapping were fixed.
- **MetaCATS:** Feature accession display and rerun details were corrected; a loading indicator appears while feature groups are added.

**Still requires separate confirmation:** TreeSort 2.0, handling mixed legacy/new genome groups, automatic separation of unrelated segments, concatenation edge cases, and service-specific behavior for missing or duplicate segments. Do not describe these as completed features solely from the 3.60 release notes.

## 7. Changes to genome, feature, and taxon views

A filtered genome list now carries applicable filters into the Sequences, Features, and Proteins tabs instead of showing an empty table. When a destination tab cannot apply a criterion, the interface identifies the omitted criteria in a banner. The release also fixes view content persisting across unrelated taxa and restores a column picker to grids where it was absent.

## 8. Transition and deprecation: guidance pending

Before the migration guide can be finalized, the team must confirm:

1. How old single-segment genome IDs map to new genome records, including ambiguous or duplicated segments.
2. Whether existing user genome groups are automatically rewritten, preserved, or require manual recreation.
3. Whether mixed legacy/new groups are supported by each service.
4. Whether links, saved searches, exports, scripts, and previous job results remain usable.
5. Whether deprecated records are hidden from searches during a transition period.
6. The announced deprecation and deletion timeline (three versus six months was discussed, not decided).
7. The notification and recovery process for affected users.

**Do not publish a deprecation date or migration promise without a confirmed policy.**

## 9. Other 3.60 highlights (link to release notes rather than expanding here)

The 3.60 release notes also describe BV-BRC Copilot (dependent on deployment of the matching API), Protein-Protein Interface Prediction, expanded Synteny Graph, job submission fixes, and API busy-response handling. The 429 retry mechanism is controlled by `enableThrottleRetry`, which defaults to **off**; do not imply it is active on every deployment.

## Related documentation and links

- [BV-BRC documentation repository](https://github.com/BV-BRC/BV-BRC-Docs/tree/master/docroot)
- [Genome Search](https://www.bv-brc.org/searches/GenomeSearch)
- [Strain Search](https://www.bv-brc.org/searches/StrainSearch)
- [Sequences documentation](https://www.bv-brc.org/docs/quick_references/organisms_taxon/sequences.html)
- [Genome API documentation](https://www.bv-brc.org/api/doc/genome)

## Prepublication checklist

- [ ] Confirm new genome/segment terminology with data-model developers
- [ ] Select a verified, clean segmented-genome example
- [ ] Capture and caption actual release-candidate screenshots
- [ ] Confirm group migration and ID mapping policy
- [ ] Confirm deprecation timeline and user communication
- [ ] Validate mixed/legacy group compatibility for each service
- [ ] Verify download wizard, FASTA headers, cURL, and saved searches in production
- [ ] Link to finalized Flu Corner tutorial and release notes
