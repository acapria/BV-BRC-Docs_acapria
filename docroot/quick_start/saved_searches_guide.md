# Saved Searches in BV-BRC

> **Status:** Draft for BV-BRC 3.60.21 review. **Audience:** All BV-BRC users. **Placement:** `docroot/common_tasks/`.

## Overview
BV-BRC 3.60 lets users save searches to their workspace and reopen them later, including from another browser.

## Save a search
1. Run a search and review the results.
2. Optionally select specific rows.
3. Click **SAVE** in the green action bar; it is available even with no rows selected.
4. **[Verify exact naming and save dialog steps.]**
5. Find the saved search under **Workspaces**.

**Screenshot:** SAVE action and Workspaces menu.

## Reopen and edit
Open the saved search from Workspaces. The search criteria appear in the results header. For influenza searches, **Edit Search** reopens the form with the prior selections.

Saved searches remember up to **1,000 selected rows** and re-highlight rows that still match. The interface reports how many selected rows no longer match.

## Bookmarks and browser navigation
The rebuilt Influenza Search retains selections through Back, refresh, and bookmarks; very large searches may restore within the same browser tab instead.

## Saved search versus genome group
A saved search stores search context and selected-row state. It is not equivalent to a genome group and should not be described as migrating legacy genome IDs.

## Before publication
- [ ] Verify save dialog and workspace location
- [ ] Test reopening in another browser
- [ ] Test 1,000-row limit and missing-row notice
- [ ] Test Edit Search and bookmark behavior
- [ ] Capture screenshots
