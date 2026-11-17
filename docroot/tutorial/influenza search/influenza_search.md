# Flu Corner: Searching and Working with Influenza Genomes and Segments

**Documentation status:** Draft for BV-BRC 3.60.21 review  
**Release context:** 3.60.21 (supersedes 3.59.14); release notes prepared November 16, 2026

> **Review note:** The behaviors below are reported in the supplied BV-BRC 3.60 release notes. Final screenshots and step-by-step controls should be verified against the deployed release. Older meeting notes describe bugs that may have been addressed by this release; they are listed for regression testing, not presented as current defects.

## Overview

The rebuilt Influenza Search helps researchers locate influenza genomes and individual segments, combine metadata filters, and download selected sequences. It also supports saved searches and preserves search selections when returning to the form.

Influenza A and B viruses have eight genome segments; influenza C and D have seven. Available records may contain all expected segments or only a subset. A genome with all expected segment labels does not necessarily have complete, high-quality sequences for each segment.

## 1. Open Influenza Search

Open the updated **Influenza Search** page in BV-BRC. Use the search form to choose the relevant influenza records and metadata criteria.

**Screenshot placeholder 1:** Full Influenza Search form, including primary fields and segment selection. Add the exact navigation path once verified in production.

## 2. Search by host, country, and subtype

The 3.60 release notes report multi-value selection for:

- **Host:** Choose up to five hosts.
- **Country:** Choose up to five countries.
- **Subtype:** Choose up to five values across H, N, full subtype, and influenza B subtype options.

Selections appear as removable chips. The available **Host** values respond to the selected **Host Group**, and **Country** values respond to the selected **Continent**, narrowing choices to values that can return results.

**Example to verify:** Choose a host group, then select more than one host; verify that the chips and results reflect all selected values.

**Screenshot placeholder 2:** Multiple host/country/subtype chips and dependent dropdowns.

## 3. Search using GenBank accessions

The rebuilt search accepts multiple GenBank accessions pasted together, separated by **commas, spaces, semicolons, or newlines**.

**Example workflow:** Paste a small set of known accessions into the accession-search field, run the search, and confirm the expected records appear. Use real, verified accessions in the published screenshot.

**Screenshot placeholder 3:** Multiple-accession search and matching results.

## 4. Find specific segments

Use the segment controls to focus on sequences of interest, such as HA or NA.

The updated search supports two distinct behaviors:

1. **Require all selected segments:** Return genome records that contain every segment chosen in the search.
2. **Restrict returned sequences:** Limit the sequence results to the chosen segments.

These controls should not be conflated: requiring a genome to contain HA and NA is different from returning only its HA and NA sequence records.

**Example workflow to verify:** Select HA and NA, require both to be present, then restrict sequence results to HA and NA. Compare the Genomes and Sequences tabs.

**Screenshot placeholder 4:** Segment selector and both options, followed by genome and sequence results.

## 5. Distinguish complete genomes from complete sequences

Influenza Search supports **sequence Complete/Partial status** independently of whether the **parent genome** is marked complete. Sequence-length filters can be combined with complete-genome filters.

For example, a genome may have the expected set of segment labels while one or more sequences are partial. Conversely, a single available HA sequence may be marked complete even though other segments are absent from the parent genome record.

**Quality caveat:** Meeting notes reported errors in completeness and quality assignments, including duplicate segments and missing quality flags. Confirm the finalized definitions and corrected pipeline behavior before publishing examples that rely on quality labels.

**Screenshot placeholder 5:** Side-by-side genome completeness and sequence status/length fields in actual results.

## 6. Understand the results tables

The search adds the attributes used in the query as result columns automatically. Sequence and protein results can display relevant parent-genome metadata, accession, and status columns.

- Orthomyxoviridae and descendants display **Segment** rather than CDS.
- Influenza B results display **Lineage**.
- Column visibility is independent between grids; changing columns in one tab does not change another.
- **Edit Search** in the green action bar returns to the search form with the original selections intact.
- Selections persist through browser Back, refresh, and bookmarking. For very large searches, restoration may be limited to the same tab.

**Screenshot placeholder 6:** Result columns, Select Columns, and Edit Search.

## 7. Download sequences and metadata

The main-table **DOWNLOAD** controls open a unified three-step wizard:

1. **Choose data type.** Select the data to export.
2. **Choose records.** Use selected records or, with nothing selected, the entire result set.
3. **Set format options.** Configure the available export format and fields.

Both the table download button and **DOWNLOAD** in the green action bar open the same wizard.

### FASTA header options

For FASTA downloads, choose header fields and delimiters or supply a custom format string. The wizard validates the format and previews the header before download. Preset formats and formats saved to the workspace can be reused. Field choices come from the API and may be grouped by category.

**Copy curl** generates the equivalent command for the configured data type, records, and columns.

**Regression tests required:** Earlier meeting notes reported mismatches between selected FASTA header fields and downloaded headers, and between saved-search filters and generated cURL. Retest the 3.60 implementation before calling these fixes verified in production.

**Screenshot placeholder 7:** Wizard steps, header preview, saved format, and Copy curl.

## 8. Save and reopen searches

Use **SAVE** in the green action bar on a results table, whether or not rows are selected. Saved searches appear in the **Workspaces** menu and are available across browsers because they are stored in the workspace.

A saved search remembers up to **1,000 selected rows** and re-highlights matching rows when reopened. If some selected rows no longer match, the interface reports how many. The reopened view displays the criteria in its header; influenza searches include **Edit Search** to reopen the form.

**Note:** A saved search is not the same thing as a genome group. Do not assume saving a search migrates old genome IDs or converts legacy groups.

**Screenshot placeholder 8:** SAVE action, Workspaces menu, reopened search, and Edit Search.

## 9. Use influenza data in analysis services

The 3.60 release notes confirm that **Genome Tree** and **MSA** accept segmented genome groups, with segment selection per genome group. Shared segment controls apply to every group added to the analysis. MSA also includes fixes to genome-ID parsing and segmented-report navigation.

For an HA-specific analysis, ensure that the input represents the intended homologous segment rather than a mixture of unrelated segments. Check which segments are available in each selected genome.

**Not confirmed here:** Automatic legacy-group conversion, TreeSort 2.0 release behavior, reassortment-specific workflows, and how concatenated phylogeny handles duplicate or nonoverlapping segments. Link to validated service-specific tutorials when available.

**Screenshot placeholder 9:** Genome Tree or MSA submission form with segment controls for multiple genome groups.

## 10. Frequently asked questions

**Can I search for several GenBank accessions at once?**  
Yes, according to the 3.60 release notes. Separate accessions using commas, spaces, semicolons, or newlines.

**Can I require a genome to contain HA and NA?**  
Yes. Select both segments and use the option requiring all selected segments.

**Can I return only HA and NA sequences?**  
The rebuilt search includes a separate option to restrict returned sequences to selected segments.

**Does a complete genome mean every segment sequence is complete?**  
No. Genome completeness and sequence Complete/Partial status are separate filters.

**Can I download all matching results without selecting rows?**  
Yes. The unified download wizard uses the whole result set when no rows are selected.

**Will my saved search preserve selected rows?**  
The release notes state that up to 1,000 selected rows are remembered, with a notice when some no longer match.

**Will my old HA-only genome group still work?**  
The 3.60 release notes do not establish the migration policy for legacy groups. Compatibility and any required user action must be confirmed separately.

## Release validation checklist

- [ ] Verify navigation path and screenshots in the deployed 3.60 release
- [ ] Test five-value host, country, and subtype selections
- [ ] Verify dependent host-group and continent filters
- [ ] Test multiple-accession input delimiters
- [ ] Test require-all-segments and restrict-sequences separately
- [ ] Confirm genome completeness versus sequence status/length behavior
- [ ] Verify automatic columns, independent column visibility, and Edit Search
- [ ] Test Back, refresh, and bookmark restoration
- [ ] Test whole-result-set download with zero selected rows
- [ ] Confirm FASTA header preview matches downloaded file
- [ ] Confirm Copy curl matches configured records and columns
- [ ] Confirm saved-search selected-row restoration and criteria display
- [ ] Test Genome Tree and MSA segmented-group segment controls
- [ ] Obtain confirmed guidance for legacy genome groups

## Related documentation

- [Changes to Segmented Viral Genome Data](BV_BRC_Segmented_Viral_Genome_Data_Changes_3.60_DRAFT.md)
- [BV-BRC documentation repository](https://github.com/BV-BRC/BV-BRC-Docs/tree/master/docroot)
- [Genome Search](https://www.bv-brc.org/searches/GenomeSearch)
- [Strain Search](https://www.bv-brc.org/searches/StrainSearch)
