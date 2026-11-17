# Getting Started with Influenza Data in BV-BRC

**Audience:** Researchers new to BV-BRC  
**Type:** Evergreen, beginner-friendly tutorial  
**Status:** Draft; capture screenshots and verify navigation in the deployed site

## What you will learn
By the end of this guide, you should be able to find influenza records, understand the difference between genomes and individual segment sequences, review metadata, download data, and identify a suitable next analysis.

## 1. What is BV-BRC?
The Bacterial and Viral Bioinformatics Resource Center (BV-BRC) provides searchable bacterial and viral data and tools for bioinformatics analyses. This tutorial focuses on influenza data. Start at [BV-BRC](https://www.bv-brc.org/).

**[Screenshot 1: BV-BRC homepage, with main navigation highlighted.]**

## 2. Find the influenza search
Open BV-BRC and locate **Influenza Search** in the site's search navigation. Use the influenza-specific search interface rather than starting with an advanced service submission form.

**[Verify the exact navigation path in production; screenshot 2: how to open Influenza Search.]**

## 3. Choose a research question
Start with a simple question, such as: *Which influenza A records from a particular host and location include an HA segment?* Decide whether you want to compare genomes, retrieve individual segment sequences, or examine metadata.

## 4. Build your first search
1. Choose the influenza virus type or subtype of interest.
2. Optionally filter by host or host group.
3. Optionally filter by geographic location and collection date.
4. Select a segment, such as **HA**, if your question concerns a particular gene segment.
5. Run the search and inspect the results before adding more filters.

The rebuilt search allows multiple host, country, and subtype selections. Available host and country choices may depend on the host group and continent selected. **[Screenshot 3: beginner search with only a few filters.]**

## 5. Understand the results
BV-BRC can display related information in **Genomes**, **Sequences**, **Features**, and **Proteins** views. These are different levels of information:

| View | What you are looking at | When to use it |
|---|---|---|
| Genomes | A genome-level record and associated metadata | Find isolates/records and examine segment coverage |
| Sequences | Individual nucleotide sequences, including viral segments | Retrieve HA, NA, or another segment |
| Features | Annotated regions or genes | Examine annotated genes or functional features |
| Proteins | Protein products | Work with translated proteins and protein-level analyses |

Influenza A and B have eight genome segments; influenza C and D have seven. A record may contain fewer than the expected number. **Do not equate a full segment count with sequence quality or completeness.**

**[Screenshot 4: same search shown in Genomes and Sequences tabs; screenshot 5: a verified genome detail page.]**

## 6. Find a particular segment
Select **HA** or **NA** in the segment filters. Be aware of two different operations:

- **Require all selected segments:** return genomes that contain every selected segment.
- **Restrict returned sequences:** show only the selected segments in the sequence results.

For example, requiring both HA and NA in a genome does not necessarily mean you are viewing only HA and NA sequences. **[Screenshot 6: both segment controls.]**

## 7. Check completeness and metadata
Inspect the collection date, host, location, subtype, accession, segment, and available status fields. The **Complete/Partial** status of a sequence is distinct from whether the parent genome is considered complete. Use sequence length and status filters when relevant to your analysis.

## 8. Download your results
1. Open the relevant results table.
2. Select specific rows, or leave all rows unselected if you intend to download the whole result set.
3. Choose **DOWNLOAD**.
4. In the three-step wizard, select data type, record scope, and output options.
5. For FASTA, review the header preview and download the file.

**[Screenshot 7: three download steps and example FASTA preview.]**

## 9. Save your search for later
Use **SAVE** in the green results action bar. Find saved searches in **Workspaces**. A saved search preserves criteria and may restore selected rows; it is different from creating a genome group.

**[Screenshot 8: SAVE and Workspaces.]**

## 10. Where to go next
- To compare homologous influenza segments, consult the Multiple Sequence Alignment (MSA) tutorial.
- To explore evolutionary relationships, consult Genome Tree and other relevant phylogenetic tutorials.
- For advanced searching and exports, see the Influenza Search reference and Download Wizard guide.
