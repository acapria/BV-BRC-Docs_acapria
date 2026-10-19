# Archaeopteryx.js Phylogenetic Tree Viewer

## Overview
Archaeopteryx.js draws a phylogenetic tree and lets you change what it shows and how it is laid out, colour and shape its nodes by the data the tree carries, search it, and download it as an image or as a tree file. The control panel on the left holds every control; the sections below describe them in the panel's order, each with the icon it draws and what it does. The same descriptions are in the viewer itself: the card button in the panel header opens them for the tree on view.

A control appears only when the tree on view gives it something to do: a tree without confidence values has no Confidence checkbox, a tree whose tips are not dated has no Time \| Div switch, and a tree without an alignment has no Alignment checkbox. A control that reads differently in another layout or on another kind of tree is listed once, with each of its wordings; a button whose icon changes shows every icon it can wear.

## See also
  * [Gene Tree Service](https://www.bv-brc.org/app/GeneTree)
  * [Gene Tree Quick Reference Guide](/quick_references/services/genetree)
  * [Gene Tree Tutorial](/tutorial/genetree/genetree)
  * [Phylogenetic Tree Service](https://www.bv-brc.org/app/PhylogeneticTree)
  * [Phylogenetic Tree Quick Reference Guide](/quick_references/services/phylogenetic_tree_building_service)
  * [Phylogenetic Tree Tutorial](/tutorial/phylogenetic_tree/phylogenetic_tree)


## Controls

### Panel header

| Control                                                                                                                                                                 | What it does                                                    |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------|
| Archaeopteryx.js                                                                                                                                                        | About Archaeopteryx.js                                          |
| <img src="glyphs/info.svg" class="no-scaled-link" style="height:1.3em" alt="info" /> Tree properties and statistics, and About Archaeopteryx.js                         | Tree properties and statistics (⌘I), and About Archaeopteryx.js |
| <img src="glyphs/cheat_sheet.svg" class="no-scaled-link" style="height:1.3em" alt="cheat sheet" /> Control panel cheat sheet                                            | Control panel: what each control does                           |
| <img src="glyphs/moon.svg" class="no-scaled-link" style="height:1.3em" alt="moon" /> <img src="glyphs/sun.svg" class="no-scaled-link" style="height:1.3em" alt="sun" /> | Switch between light and dark                                   |
| –                                                                                                                                                                       | Hide / show the controls                                        |

### Tree picker

| Control                                                                                        | What it does                 |
|------------------------------------------------------------------------------------------------|------------------------------|
| <img src="glyphs/tree_prev.svg" class="no-scaled-link" style="height:1.3em" alt="tree prev" /> | previous tree                |
|                                                                                                | Tree 1 of 10 -- pick another |
| <img src="glyphs/tree_next.svg" class="no-scaled-link" style="height:1.3em" alt="tree next" /> | next tree                    |

### Layout and display type

| Control                                                                                                        | What it does                                                                                                                                                                                                       |
|----------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <img src="glyphs/rectangular.svg" class="no-scaled-link" style="height:1.3em" alt="rectangular" />             | rectangular layout: the root at the left, the tips in even rows down the page                                                                                                                                      |
| <img src="glyphs/circular.svg" class="no-scaled-link" style="height:1.3em" alt="circular" />                   | circular layout: the tree as a fan, every tip label carried out to a common ring                                                                                                                                   |
| <img src="glyphs/unrooted.svg" class="no-scaled-link" style="height:1.3em" alt="unrooted" />                   | unrooted layout: equal-angle, drawing no root branch at all                                                                                                                                                        |
| <img src="glyphs/phylogram.svg" class="no-scaled-link" style="height:1.3em" alt="phylogram" />                 | phylogram: branch lengths drawn to scale, so the tips end ragged. Greyed in the circular layout, which always carries its labels to the outer ring, so there the aligned phylogram is the one drawn                |
| <img src="glyphs/aligned_phylogram.svg" class="no-scaled-link" style="height:1.3em" alt="aligned phylogram" /> | aligned phylogram: branch lengths to scale, with every tip carried on to a common column, or in the circular layout to the outer ring. Greyed in the unrooted layout, which has no column or ring to carry them to |
| <img src="glyphs/cladogram.svg" class="no-scaled-link" style="height:1.3em" alt="cladogram" />                 | cladogram: topology only, branch lengths ignored, every tip flush                                                                                                                                                  |
| Time                                                                                                           | lay the tree out by TIME (each branch at its stated length in time; from the node dates where the tree arrived showing divergence)                                                                                 |
| Div                                                                                                            | lay the tree out by DIVERGENCE (substitutions per site: as the tree records it, or on a BEAST tree each branch's time x its clock rate)                                                                            |
| Clock plot                                                                                                     | clock plot: each tip's date against its divergence from the root, with a line through the tips (its slope is the rate); a panel linked to the tree                                                                 |

### Visualizations

| Control  | What it does                                                            |
|----------|-------------------------------------------------------------------------|
| Color by | colorize the node label and the node itself by a field the tree carries |
| Shape    | change the node shape by a field the tree carries                       |

### Display Data

**Labels**

| Control       | What it does                                                                                                                                |
|---------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| Node Name     | to show/hide node names (node names usually are the untyped labels found in New Hampshire/Newick formatted trees)                           |
| Taxonomy      | to show/hide node taxonomic information                                                                                                     |
| Sequence      | to show/hide node sequence information                                                                                                      |
| Metadata      | to show/hide the nodes' metadata (phyloXML properties: species, host, …) in their labels; Metadata fields… chooses which, and in what order |
| Confidence    | to show/hide confidence values                                                                                                              |
| Branch Length | to show/hide branch length values                                                                                                           |
| Ext. Labels   | to show/hide external node labels                                                                                                           |
| Int. Labels   | to show/hide internal node labels                                                                                                           |

| Control          | What it does                                                    |
|------------------|-----------------------------------------------------------------|
| Metadata fields… | choose which metadata fields the labels show, and in what order |

**Nodes**

| Control       | What it does                                                                                     |
|---------------|--------------------------------------------------------------------------------------------------|
| Node Events   | to show speciations and duplications as colored nodes (e.g. speciations green, duplications red) |
| Branch Events | to show/hide branch events (e.g. mutations)                                                      |

**Options**

<table>
<colgroup>
<col style="width: 28%" />
<col style="width: 72%" />
</colgroup>
<thead>
<tr class="header">
<th>Control</th>
<th>What it does</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Auto-hide Labels</td>
<td>automatically hide external labels, and branch values that would overprint a name or each other, where the tree is too dense for them to be readable</td>
</tr>
<tr class="even">
<td>Short Names</td>
<td>to shorten long node names</td>
</tr>
<tr class="odd">
<td>Support Dots</td>
<td>to mark a branch with support of at least 95% with a dot at its midpoint, where there is room to draw it</td>
</tr>
<tr class="even">
<td>Alignment</td>
<td>to show/hide the sequence alignment beside the tree (rectangular layout only)</td>
</tr>
<tr class="odd">
<td>Sequence Logo</td>
<td>to summarize the alignment under it as a sequence logo: each column a stack of letters, as tall as that column's information content and shared out by residue frequency. Over the tips currently on screen, so entering a clade summarizes that clade</td>
</tr>
<tr class="even">
<td>Visual Styles</td>
<td>to use visual styles (node and font colors, shapes) and branch colors, if present in the tree file</td>
</tr>
<tr class="odd">
<td>Visualizations</td>
<td>to show or hide the Color and Shape visualizations chosen above</td>
</tr>
<tr class="even">
<td>Heat Map</td>
<td>to show/hide a cell per tip and numeric field beside the tree, every column on one color scale; concentric rings in the circular layout (not in the unrooted one, where a column has no ring to be)</td>
</tr>
<tr class="odd">
<td>Domain Architectures</td>
<td>to show/hide the protein domain architectures beside the tips</td>
</tr>
<tr class="even">
<td>Genes</td>
<td>to show/hide the genome regions beside the tips: each gene an arrow on a backbone, coloured by family, the rows lined up on one family</td>
</tr>
<tr class="odd">
<td>Scale</td>
<td>to show/hide the scale bar at the bottom left of a phylogram: a round length in the tree's branch-length unit (it gives way while the scale axis is on)</td>
</tr>
<tr class="even">
<td><p>Scale Axis</p></td>
<td><p>to show/hide a labeled distance axis from the root to the deepest tip (phylogram; rectangular and circular layouts)</p>
<p>to show/hide the geologic (ICS) time axis and node-age bars (a distance axis while the branches show divergence) (phylogram; rectangular and circular layouts)</p>
<p>to show/hide the calendar time axis and node-age bars (a distance axis while the branches show divergence) (phylogram; rectangular and circular layouts)</p></td>
</tr>
<tr class="odd">
<td><p>Scale Grid</p></td>
<td><p>to show/hide grid lines (rings, in circular) at the scale axis ticks</p>
<p>to show/hide grid lines (rings, in circular) at the time axis's intervals or ticks</p></td>
</tr>
</tbody>
</table>

### Domain Architectures

| Control | What it does                                                                               |
|---------|--------------------------------------------------------------------------------------------|
| −       | narrow the domain tracks (hold to repeat)                                                  |
| \+      | widen the domain tracks (hold to repeat)                                                   |
| −       | Decrease the E-value threshold by a factor of 10                                           |
| \+      | Increase the E-value threshold by a factor of 10                                           |
| Labels  | where the domain names go: on the boxes (rectangular layout only), in a legend, or nowhere |
| Glow    | a soft glow in each domain's own colour around its box                                     |

### Genome regions

| Control | What it does                                                                                                                                                                                                                                                    |
|---------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| −       | narrow the gene track (hold to repeat)                                                                                                                                                                                                                          |
| \+      | widen the gene track (hold to repeat)                                                                                                                                                                                                                           |
| Anchor  | the family the rows line up on: its gene sits at the same place in every genome, pointing right, and the neighbours follow (a genome with it on the other strand is mirrored). Auto picks the family single-copy in the most genomes; None left-aligns the rows |
| Family  | which family annotation colours the genes and anchors the rows (a BV-BRC export carries both PGfams and PLfams)                                                                                                                                                 |
| Labels  | where the gene symbols go: on the arrows (rectangular layout only), in a legend of the families, or nowhere                                                                                                                                                     |

### Heat Map

| Control          | What it does                                                                                     |
|------------------|--------------------------------------------------------------------------------------------------|
| Order columns    | how the matrix columns are ordered; a clustered order also draws the clustering above the matrix |
| Reorder columns… | drag the columns into the order you want; doing so sets Manual                                   |

### View & Tools

<table>
<colgroup>
<col style="width: 28%" />
<col style="width: 72%" />
</colgroup>
<thead>
<tr class="header">
<th>Control</th>
<th>What it does</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Y+ / +</p></td>
<td><p>zoom in vertically (or Shift+mousewheel)</p>
<p>zoom in (or mousewheel over the tree)</p></td>
</tr>
<tr class="even">
<td><p><img src="glyphs/rotate_ccw.svg" class="no-scaled-link" style="height:1.3em" alt="rotate ccw" /> X-</p></td>
<td><p>zoom out horizontally (or Shift+Alt+mousewheel)</p>
<p>rotate counter-clockwise</p></td>
</tr>
<tr class="odd">
<td><img src="glyphs/expand_vertical.svg" class="no-scaled-link" style="height:1.3em" alt="expand vertical" /></td>
<td>fit and center tree, expand vertically</td>
</tr>
<tr class="even">
<td><img src="glyphs/fit_all.svg" class="no-scaled-link" style="height:1.3em" alt="fit all" /></td>
<td>fit and center tree display (Home or Esc for an almost complete reset)</td>
</tr>
<tr class="odd">
<td><p><img src="glyphs/fit_width.svg" class="no-scaled-link" style="height:1.3em" alt="fit width" /> <img src="glyphs/labels_horizontal.svg" class="no-scaled-link" style="height:1.3em" alt="labels horizontal" /> <img src="glyphs/labels_radial.svg" class="no-scaled-link" style="height:1.3em" alt="labels radial" /></p></td>
<td><p>fit the tree to the window width, keeping the current vertical zoom</p>
<p>node labels: radial -- click to flip</p>
<p>node labels: horizontal -- click to flip</p></td>
</tr>
<tr class="even">
<td><p><img src="glyphs/rotate_cw.svg" class="no-scaled-link" style="height:1.3em" alt="rotate cw" /> X+</p></td>
<td><p>zoom in horizontally (or Shift+Alt+mousewheel)</p>
<p>rotate clockwise</p></td>
</tr>
<tr class="odd">
<td><p>Y- / -</p></td>
<td><p>zoom out vertically (or Shift+mousewheel)</p>
<p>zoom out (or mousewheel over the tree)</p></td>
</tr>
<tr class="even">
<td><img src="glyphs/ladderize_asc.svg" class="no-scaled-link" style="height:1.3em" alt="ladderize asc" /> <img src="glyphs/ladderize_desc.svg" class="no-scaled-link" style="height:1.3em" alt="ladderize desc" /></td>
<td>ladderize all</td>
</tr>
<tr class="odd">
<td><img src="glyphs/whole_tree.svg" class="no-scaled-link" style="height:1.3em" alt="whole tree" /></td>
<td>return all the way to the complete tree (if in a sub-tree)</td>
</tr>
<tr class="even">
<td><img src="glyphs/up_one_level.svg" class="no-scaled-link" style="height:1.3em" alt="up one level" /></td>
<td>move up by one level towards the complete tree (if in a sub-tree)</td>
</tr>
<tr class="odd">
<td><img src="glyphs/uncollapse_all.svg" class="no-scaled-link" style="height:1.3em" alt="uncollapse all" /></td>
<td>uncollapse all</td>
</tr>
<tr class="even">
<td><p><img src="glyphs/midpoint.svg" class="no-scaled-link" style="height:1.3em" alt="midpoint" /></p></td>
<td><p>re-root the tree: MAD or midpoint</p>
<p>Time trees can't be re-rooted: their branch lengths are times measured from this root.</p>
<p>This tree is marked as not re-rootable (rerootable="false").</p></td>
</tr>
<tr class="odd">
<td><img src="glyphs/representatives.svg" class="no-scaled-link" style="height:1.3em" alt="representatives" /></td>
<td>select representative tips: one per group of close tips</td>
</tr>
</tbody>
</table>

### Sizes

| Control | What it does              |
|---------|---------------------------|
| Font    | font size, for all labels |
| Node    | node shape size           |
| Branch  | branch line width         |

### Search

| Control        | What it does                                                                                                |
|----------------|-------------------------------------------------------------------------------------------------------------|
| Search A field | the field to search in                                                                                      |
| Search A match | how to match                                                                                                |
| Search A       | enter text to search for -- ',' means OR, '+' means AND; pick the field and match mode from the menus above |
| R              | reset (remove) search result A                                                                              |
| Search B field | the field to search in                                                                                      |
| Search B match | how to match                                                                                                |
| Search B       | enter text to search for -- ',' means OR, '+' means AND; pick the field and match mode from the menus above |
| R              | reset (remove) search result B                                                                              |
| Match case     | search in a case-sensitive manner                                                                           |
| Inverse        | select the nodes that do NOT match                                                                          |

### Download

| Control     | What it does                                                                                                                        |
|-------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Name        | the file name: each format adds its own extension                                                                                   |
| As shown    | SVG, PDF and PNG show what is on screen: the part of the tree in view, at the current zoom                                          |
| Full size   | SVG, PDF and PNG show the whole tree, drawn large enough for every name                                                             |
| 2×          | PNG at 2 times the resolution of the screen                                                                                         |
| 4×          | PNG at 4 times the resolution of the screen                                                                                         |
| 8×          | PNG at 8 times the resolution of the screen                                                                                         |
| Download…   | download the tree: choose the format from the menu                                                                                  |
| Copy Newick | copy the tree to the clipboard in Newick format                                                                                     |
| Copy PNG    | copy the tree to the clipboard as a PNG image, to paste into a document or a slide: drawn as the Graphics and PNG choices above say |

**Download… menu: Graphics**

| Format | What it does                                |
|--------|---------------------------------------------|
| SVG    | vector: edit it in Inkscape or Illustrator  |
| PDF    | vector: ready to print or to put in a paper |
| PNG    | image, at 4× the screen's resolution        |

**Download… menu: Tree**

<table>
<colgroup>
<col style="width: 28%" />
<col style="width: 72%" />
</colgroup>
<thead>
<tr class="header">
<th>Format</th>
<th>What it does</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>phyloXML</td>
<td>keeps everything the tree carries: taxonomy, sequences, dates, metadata</td>
</tr>
<tr class="even">
<td>Newick</td>
<td>names, branch lengths and support values only</td>
</tr>
<tr class="odd">
<td><p>Nexus</p></td>
<td><p>the tree: names, branch lengths and support values</p>
<p>the tree and its alignment, in one file</p></td>
</tr>
</tbody>
</table>

**Download… menu: Tip data**

| Format | What it does                                                                                       |
|--------|----------------------------------------------------------------------------------------------------|
| TSV    | a table, one row per tip: names, taxonomy, sequence names, branch lengths and every metadata field |
| FASTA  | every molecular sequence the tips carry                                                            |

## Keyboard shortcuts

The same actions on every platform; only the modifier differs: ⌘ on macOS, Ctrl on Windows and Linux. In the viewer, ⌘/ (Ctrl+/) shows this list, drawn for the platform you are on, and the About box (a click on the program name) links to it.

| macOS    | Windows / Linux | What it does                                     |
|----------|-----------------|--------------------------------------------------|
| ⌘0       | Ctrl+0          | Fit the tree to the window                       |
| ⌘+       | Ctrl++          | Zoom in                                          |
| ⌘−       | Ctrl+−          | Zoom out                                         |
| ⌘⇧↑      | Ctrl+Shift+↑    | Zoom in vertically                               |
| ⌘⇧↓      | Ctrl+Shift+↓    | Zoom out vertically                              |
| ⌘⇧→      | Ctrl+Shift+→    | Zoom in horizontally (circular: rotate)          |
| ⌘⇧←      | Ctrl+Shift+←    | Zoom out horizontally (circular: rotate back)    |
| ⌘⇧E      | Ctrl+Shift+E    | Expand vertically until the labels fit           |
| ⌘⇧L      | Ctrl+Shift+L    | Next layout: rectangular, circular, unrooted     |
| ⌘⇧D      | Ctrl+Shift+D    | Next display type: phylogram, aligned, cladogram |
| ⌘⇧X      | Ctrl+Shift+X    | Time / divergence scale, or the scale axis       |
| ⌘⇧O      | Ctrl+Shift+O    | Ladderize (order the tree)                       |
| ⌘⇧U      | Ctrl+Shift+U    | Uncollapse every clade                           |
| ⌘F       | Ctrl+F          | Go to the search box                             |
| ⌘G       | Ctrl+G          | Next search hit                                  |
| ⌘⇧G      | Ctrl+Shift+G    | Previous search hit                              |
| ⌘⇧\<     | Ctrl+Shift+\<   | Previous tree of the file                        |
| ⌘⇧\>     | Ctrl+Shift+\>   | Next tree of the file                            |
| ⌘I       | Ctrl+I          | Tree properties and statistics                   |
| ⌘/       | Ctrl+/          | This list                                        |
| Esc      | Esc             | Back to the whole tree, the launch view          |
| O        | O               | Move the overview to the next corner             |
| PageUp   | PageUp          | Larger font                                      |
| PageDown | PageDown        | Smaller font                                     |

The mouse wheel zooms; with Shift it zooms vertically only, with Shift+Alt horizontally, with Ctrl+Shift it sizes the font.

## Node menu

A click on a node, on its point or its label, opens a menu named after the node. What it offers depends on the node: a tip cannot be collapsed, a child of the root cannot be switched to or re-rooted on, the root has no menu, and an entry the tree does not allow is greyed, with a tooltip that says why.

<table>
<colgroup>
<col style="width: 28%" />
<col style="width: 72%" />
</colgroup>
<thead>
<tr class="header">
<th>Entry</th>
<th>What it does</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Display Node Data</td>
<td>show what the file says about this node: name, branch length, date, taxonomy, sequence, properties and the rest, in a window to copy from</td>
</tr>
<tr class="even">
<td>Switch to Subtree</td>
<td>show only the clade under this node, as a tree of its own (for a tip, its parent's clade); the whole-tree button of View &amp; Tools, or Esc, returns to the whole tree</td>
</tr>
<tr class="odd">
<td>Collapse/Uncollapse</td>
<td>fold the clade under this node into a wedge, or open it again; greyed for a tip and in the unrooted layout</td>
</tr>
<tr class="even">
<td>Uncollapse Subtree</td>
<td>open every collapsed clade under this node; greyed when nothing below it is collapsed</td>
</tr>
<tr class="odd">
<td>Swap Descendants</td>
<td>exchange the order of this node's child clades</td>
</tr>
<tr class="even">
<td>Ladderize Subtree</td>
<td>order the clades under this node by size, largest first or smallest first in turn</td>
</tr>
<tr class="odd">
<td><p>Reroot</p></td>
<td><p>re-root the tree on the branch above this node; when the new root would change the clade of an internal node that carries data, a warning says how many before anything changes</p>
<p>Time trees can't be re-rooted: their branch lengths are times measured from this root.</p>
<p>This tree is marked as not re-rootable (rerootable="false").</p></td>
</tr>
<tr class="even">
<td>Select/Deselect Node</td>
<td>add this node to the selection, or take it out; offered when the host page enables manual node selection</td>
</tr>
<tr class="odd">
<td>Select/Deselect All Ext Nodes</td>
<td>add every tip under this node to the selection, taking out those already in it; offered when the host page enables manual node selection</td>
</tr>
<tr class="even">
<td>Download Ext. Node Data</td>
<td>download the tips under this node as a tab-separated table: name, taxonomy, sequence, branch length and one column per property</td>
</tr>
<tr class="odd">
<td>List Sequences in Fasta</td>
<td>show the molecular sequences of the tips under this node in FASTA format, in a window to copy from; offered when the tree carries sequences</td>
</tr>
<tr class="even">
<td>Download Sequences in Fasta</td>
<td>download the molecular sequences of the tips under this node as a FASTA file; offered when the tree carries sequences</td>
</tr>
<tr class="odd">
<td>Delete Subtree</td>
<td>remove this node and its whole clade from the tree on view; the visualizations and the search are recomputed on what is left; not offered in a subtree view</td>
</tr>
<tr class="even">
<td>Access DB [accession]</td>
<td>open the database record of this node's accession (NCBI protein or nucleotide, RefSeq, UniProt) in a new browser tab; offered when the node has one, among its properties or sequences or as a UniProt-style name such as CASP9_HUMAN</td>
</tr>
<tr class="odd">
<td>Delete External Node</td>
<td>remove this tip from the tree on view; the visualizations and the search are recomputed on what is left; not offered in a subtree view</td>
</tr>
</tbody>
</table>
