# Downloading Data with the BV-BRC Download Wizard

> **Status:** Draft for BV-BRC 3.60.21 review. **Audience:** All BV-BRC users. **Placement:** `docroot/quick_references/` and linked from table documentation.

## Overview
The main data tables now use a **unified three-step download wizard**. Both the DOWNLOAD button above a table and **DOWNLOAD** in the green action bar open the same options.

## Download records
1. Open a BV-BRC results table.
2. Select rows if you want only those records. **If no rows are selected, the download covers the full result set.**
3. Click **DOWNLOAD**.
4. **Choose a data type.**
5. **Choose which records to include.**
6. **Set format options**, then download.

**Screenshot:** Three wizard steps and record scope.

## Configure FASTA headers
For applicable FASTA downloads, you can choose header fields, set delimiters, or write a custom format string. The wizard validates the format and previews the header. Presets and saved workspace header formats can be reused. Available fields come from the API; extensive lists are grouped and filterable.

**Screenshot:** FASTA header field picker and preview.

## Reproduce the download with cURL
Use **Copy curl** to obtain the command line corresponding to the configured data type, records, and columns.

**[Insert a tested example only after verifying the generated command reproduces the selected results.]**

## Working with segmented viruses
Selecting genomes that **contain** certain segments is not the same as limiting a sequence export to those segments. Verify both search criteria and download record scope before exporting HA, NA, or other segment sequences.

## Before publication
- [ ] Verify full-results download with no rows selected
- [ ] Test selected-row downloads
- [ ] Compare FASTA header preview with actual file
- [ ] Test saved header presets and custom format strings
- [ ] Verify Copy curl matches filters and selected columns
- [ ] Capture screenshots
