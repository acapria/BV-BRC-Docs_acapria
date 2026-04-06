# Mobile Element Detection Service 

*Revised: April 6, 2026*

## Overview
The Mobile Element Detection service allows you to identify viruses and plasmids in nucleic acid datasets. The use cases for this pipeline are broad – from detecting novel viruses in complex wastewater samples, to identifying plasmids in isolate genomes. The core of the Mobile Element Detection service is [geNomad](https://portal.nersc.gov/genomad/index.html) which detects viruses and plasmids in assembled contigs. This pipeline can accept short reads or assembled contigs. If raw reads are provided, assembly can be carried out using any of the assembly methods in the [Genome Assembly Service](https://www.bv-brc.org/docs/tutorial/genome_assembly/assembly.html). The output of this pipeline is an assembled contigs file (if short reads are provided) and a tailored geNomad output which links identified viral and plasmid resources to BV-BRC databases. 

A detailed description of the geNomad workflow is provided in the [Mobile Element Detection Service Tutorial](../../../tutorial/mobile_element/mobile_element.html).

## See also
* [Mobile Element Detection Service](https://www.bv-brc.org/app/MobileElementDetection)
* [Mobile Element Detection Service Tutorial](../../../tutorial/mobile_element/mobile_element.html)

## Using the Mobile Element Detection Service
The **Mobile Element Detection** submenu option under the **Services** main menu (Metagenomics category) opens the service input form (*shown below*). *Note: You must be logged into BV-BRC to use this tool.*

![Services Menu](../../images/bv_services_menu.png)

## Options

## Input Configuration 
The service can accept either contigs (FASTA) or reads as input. If 'contigs' is selected, the input form appears as shown below. Select the file from the dropdown menu or navigate to find the file in your workspace using the folder icon.

![Mobile Element Detection Service Input Form](./images/mobile_element_input_form.png) 

If 'reads' is selected, the input form expands to appear as shown below, which adds the options for Genome Assembly (see [Genome Assembly Service Tutorial](https://www.bv-brc.org/docs/tutorial/genome_assembly/assembly.html) for details on configuring the assembly.

![Mobile Element Detection Service Input Form - Reads option](./images/mobile_element_input_form_reads.png) 

## Output 
Select an output folder for the results of the service and provide a name for the job output results. 

## Buttons
**Reset:** Resets the input form to default settings. 
**Reset:** Launches the service , which, upon completion, displays a table below it 

## Output Results
![Mobile Element Detection Service Results](./images/mobile_element_job_results.png) 

The service several files and folders:

**Analysis_Summary.html:** - Report summarizing the results of the service job. It has 2 overall sections, – displaying first contigs identified as viral, and then contigs identified as plasmids.

GOT TO HERE

### Action buttons
After selecting one of the output features by clicking it, a set of options becomes available in the vertical green Action Bar on the right side of the table.  These include

* **Hide/Show:** Toggles (hides) the right-hand side Details Pane.
* **Download:**  Downloads the selected items (rows).
* **Copy:** Copies the selected items to the clipboard.
* **FASTA:** Provides the FASTA DNA or protein sequence for the selected feature(s).
* **ID Map:** Provides the option to map the selected feature(s) to multiple other idenfiers, such as RefSeq and UniProt.
* **MSA:** Launches the Multiple Sequence Alignment (MSA) tool and aligns the selected features by DNA or protein sequence in an interactive viewer.
* **Pathway:** Loads the Pathway Summary Table containing a list of all the pathways in which the selected features are found.
* **Group:** Opens a pop-up window to enable adding the selected sequences to an existing or new group in the private workspace.
* **Feature:** Loads the Feature Page for the selected feature. *Available only if a single feature is selected.*
* **Features:** Loads the Features Table for the selected features. *Available only if multiple features are selected.*
* **Genome:** Loads the Genome View Overview page corresponding to the selected feature.  *Available only if a single feature is selected.*
* **Genomes:** Loads the Genomes Table, listing the genomes that correspond to the selected features. *Available only if multiple features are selected.*

More details are available in the [Action Bar](/quick_references/action_bar) Quick Reference Guide.

