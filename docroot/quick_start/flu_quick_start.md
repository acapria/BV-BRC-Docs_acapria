# Getting Started with Influenza Data in BV-BRC

**Audience:** Researchers new to BV-BRC    
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

## 10. Where to go next: Influenza analysis tools and workflows

Once you have identified influenza genomes or sequences of interest, BV-BRC provides tools for comparing sequences, investigating evolutionary relationships, identifying mutations, and analyzing newly generated sequencing data.

### Sequence comparison and variation analysis

- **[Multiple Sequence Alignment (MSA) and SNP Analysis](https://www.bv-brc.org/docs/quick_references/services/msa_snp_variation_service.html):** Align influenza nucleotide or protein sequences to identify conserved regions, substitutions, and other sequence differences. For segmented influenza genomes, select homologous segments, such as HA or NA, for comparison.
- **[BLAST](https://www.bv-brc.org/docs/tutorial/):** Compare an influenza nucleotide or protein sequence against sequences in BV-BRC to identify similar sequences and investigate sequence relationships.
- **[Meta-CATS](https://www.bv-brc.org/docs/tutorial/metacats/metacats.html):** Identify alignment positions that differ significantly between groups of sequences. For example, compare HA sequences from different hosts, geographic regions, or time periods.
- **[Primer Design](https://www.bv-brc.org/docs/tutorial/primer_design/primer_design.html):** Design primers for selected influenza sequences, including targets of interest for PCR-based applications.

### Phylogenetics, classification, and reassortment

- **[Viral Genome Tree and Gene/Protein Tree](https://www.bv-brc.org/docs/quick_references/organisms_taxon/phylogeny.html):** Explore evolutionary relationships among influenza sequences or genomes. Segment-specific phylogenies can help researchers investigate relationships among influenza isolates.
- **[Influenza Reassortment Analysis (TreeSort)](https://www.bv-brc.org/docs/quick_references/services/treesort_service.html):** Investigate potential reassortment events by comparing evolutionary relationships across influenza genome segments.
- **[Subspecies Classification](https://www.bv-brc.org/docs/quick_references/services_menu.html):** Explore supported influenza clade classification workflows, including relevant H1, H3, and H5 classifications.
- **[Influenza HA Subtype Numbering Conversion](https://www.bv-brc.org/docs/quick_references/services_menu.html):** Convert HA amino acid positions between supported influenza numbering conventions to facilitate comparison of mutations across strains and subtypes.

### Influenza sequencing and data submission

- **[Viral Assembly](https://www.bv-brc.org/docs/tutorial/viral_assembly/assembly.html):** Assemble influenza virus sequences from raw sequencing reads using the IRMA-based Viral Assembly Service. The service includes influenza-specific analysis modules for different virus types and sequencing technologies.
- **[Influenza Sequence Submission](https://www.bv-brc.org/docs/quick_references/services_menu.html):** Access the influenza sequence submission service for supported data submission workflows.

### Influenza surveillance and outbreak investigation

- **[Influenza H5N1 Outbreak Tracker](https://www.bv-brc.org/):** Explore curated outbreak information and associated influenza data to support surveillance and research.
- **[Influenza Search](https://www.bv-brc.org/):** Refine searches using subtype, host, geographic location, collection metadata, and genome segment availability. Researchers can use these results as a starting point for downstream analyses.

### Additional BV-BRC resources

- **[BV-BRC Tutorials](https://www.bv-brc.org/docs/tutorial/):** Step-by-step instructions for analysis services and common research workflows.
- **[Tools and Services Quick References](https://www.bv-brc.org/docs/quick_references/services_menu.html):** Overview of available tools, input requirements, and service functionality.
- **[Instructional Videos](https://www.bv-brc.org/docs/videos/index.html):** Video demonstrations of searching, filtering, workspaces, and analysis services.

**Suggested starting point:** New users may begin by finding influenza HA sequences, downloading them in FASTA format, and using MSA to compare sequences. From there, they can explore phylogenetic relationships, investigate sequence variation with Meta-CATS, or use influenza-specific tools for reassortment and classification.
