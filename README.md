# VitisNet
Molecular Networks for Grapevine

Original files are available at 
https://www.sdstate.edu/agronomy-horticulture-plant-science/functional-genomics-bud-endodormancy-induction-grapevines

Users of VitisNet should cite: VitisNet: “Omics” Integration through Grapevine Molecular Networks. Jérôme Grimplet, Grant R. Cramer, Julie A. Dickerson, Kathy Mathiason, John Van Hemert and Anne Y. Fennell, 2009, PLoS ONE: http://dx.plos.org/10.1371/journal.pone.0008365.

A database for the Grapevine Molecular Networks
Introduction:
VitisNet (vitis-dormancy.sdstate.org) has been built with a program called CellDesigner (celldesigner.org) and can be visualized using Cytoscape (cytoscape.org). A user first identifies a set of genes, transcripts, proteins or metabolites of interest and they can overlay their expression values on the molecular networks (VitisNet) to determine biochemical events of interest. Additional plug-ins available in Cytoscape can be used to analyze the data further. The following tutorial will instruct users on what software is needed, how to obtain that software and how to upload data and visualize them on the molecular networks of VitisNet. A set of data has been provided in the right-hand panel of the VitisNet page that can be used with this tutorial.

Using VitisNet with Cytoscape

1. Installation of the Required Software

The user should first download the Cytoscape software into a folder on their computer (Section 1).
Cytoscape (http://www.cytoscape.org/) is the freely available software required for visualizing VitisNet and loading expression data. Go to the download area and follow the instructions. New Cytoscape users should follow the Cytoscape tutorials available on the Cytoscape website
      http://cytoscape.org/cgi-bin/moin.cgi/Presentations/Basic.
It is highly recommended to complete tutorials 01 and 04 to understand the flexibility of Cytoscape and to facilitate using VitisNet networks and loading and using expression data.

2. Visual Style and Viewing Networks
When the network file(s) are loaded, the networks appear under a predefined style. The properties of the styles are accessible under the Vizmapper tab in the Control Panel on the left side of Cytoscape. It is important to understand how to load and modify the visual style. The visual style allows users to customize how the networks are displayed. It is also used for visualizing expression data by modifying the color of the nodes according to the expression of the molecule that they represent.

2.1 Uploading visual style file
To upload th0e visual properties files into Cytoscape, go into the File menu and choose "Import > Vizmap Property File". The "Import Visual Property File" window will open.

2.2 Changing the visual style
Once a visual style has been uploaded, it is available through the VizMapper tab (1). Select it from the "Current Visual Style" drop-down menu (2). You can choose from a variety of different styles that are built into Cytoscape, the prelodeaded style is called Vitis_style.

2.3 Visual style legend
This picture lists the descriptions of the nodes and edges styles from the Vitis_style that are used in the example, but users can experiment and adjust style to their liking as they become familiar with Cytoscape. 

The edge and node styles for Vitis_style are accessible in the "Visual Mapping Browser" section of the Control Panel on the left side of the screen. The descriptions of these styles are accessed by expanding the menu (+) of the elements. Alternatively, users can click on the "Defaults" picture above the "Visual Mapping Browser" selecting node, edge or global tab. Similarly, the user can change node shape, line width, etc.

For example, the background color can be changed by clicking on the "Defaults" image, going to the global tab, clicking on "background color" and picking white (or any other color in the global tab).


4. Probeset Attributes
This section describes how to link microarray features to the unique transcript sequences used in the networks. In the following example data from Affymetrix GeneChip® Vitis vinifera Genome Array hybridizations has been used. If your microarray directly links expression to the gene name used in the molecular networks this step can be skipped.

4.1 Loading probesets attributes
This section is specifically useful for any kind of data where the quantitative values of interest are linked to an identifier which is not use in VitisNet but the corespondance between this identifier and the one use in cytoscape is known. For example microarray data use a probest identifier whose gene it represent is known (probe VIT_0000 is on gene Vitivi00g00000). RNAseq data use the gene name directly so these steps are not requiered.
Loading expression data in Cytoscape is equivalent to assigning an attribute to the items present on the networks. In this example for transcriptomics data, the steps for uploading microarray data obtained from Affymetrix GeneChips are described. A preliminary step is needed to link the probeset IDs to the transcripts. Although several Affymetrix probesets can be related to each individual transcript, there are up to twelve probesets that correspond to one transcript. The probeset with the highest expression across all grapevine microarray experiments in Plexdb has been listed as the first probeset in the first column in the GS_to_probeset.txt file. In the File menu go to "Import > Attribute from Table". The "Import Annotation File" window will open. Load the GS_to_probeset.txt file (1) in the "Data Sources" section. In the "Advanced" section check the "Show Mapping Options" (2) and the "Show Text File Import Options" (3) boxes. In the "Annotation File to Attribute Mapping" section, select CELLDESIGNER_SPECIES as "Key Attribute for Network" (4), as it is the attribute present in both data sets, i.e. the transcript name. In the "Attribute Names" section, check the "Transfer first line as attribute names" (5) box. Click "Import" (located at the very bottom of the window). Close the status window. If users want to map transcripts from another species or grapevine genes with different IDs, this procedure can be used by replacing the probeset name with the orthologous gene name or ID.

4.2 Visualizing probesets
Once the data are loaded, the borders of the transcript nodes that contain a probeset appear with a bold outline (1). You may need to zoom in a little bit to see the bold clearly. However, if the transcripts are not bolded like in the picture below, click on node line width in the visual mapper browser (3). Click and select Discrete Mapper. "1" appears below "Mapping Type". Click in the cell under "discrete Mapping" and type "2". Click enter on the keyboard. Each transcript with a probeset is flagged in the Probeset_presence node attribute column (2) in the Data Panel at the bottom of the frame. If the probeset presence column contains a 1, then the node line thickness with it is multiplied by 2 (3). For visualizing attributes in the bottom frame, click on Node Attribute browser tab; select items from the network by clicking and dragging cursor over desired section; and use the "Select Attributes" icon (see section 4.2) to select desired section; and information will appear in Data Panel (i.e. CELLDESIGNER_NODE_TYPE AND probeset_presence).

5. Expression Data
This section describes how to load expression data from transcriptomic, proteomic and metabolomic studies.

5.1Loading expression data
The expression data can now be assigned to the transcript via the probeset attribute or the gene name, the key is that the ID in the expression file correspond to a name in the citoscape file. This section describes how to load metabolite, protein and transcript expression values. In the File menu go to "Import > Attribute from Table". The "Import Annotation File" window will open. Load the expression file expression_berry.txt (1) in the "Data Sources" section. In the "Advanced" section check the "Show Mapping Options" (2) and the "Show Text File Import Options" (3) boxes. In this experiment, the metabolites and the proteins are directly mapped to the CELLDESIGNER_SPECIES, which are KEGG metabolite numbers and EC numbers or identifiers for the proteins. In the "Annotation File to Attribute Mapping" section, select CELLDESIGNER_SPECIES as "Key Attribute for Network" (4). In the "Attribute Names" section, check the "Transfer first line as attribute names" (5) and click "Import". The transcript expression values are mapped to the probeset attribute. Next, repeat the steps above with the probeset_1 as "Key Attribute for Network" (4) to complete mapping expression description/value to probeset. If you want to map expression to the probesets 2 to 12 repeat that operation to your discretion.

Note: For using your own expression data, users need to create a text file that contains in the first column an ID that can map to an attribute present on the networks. It can be a main ID, referenced here as "CELLDESIGNER_SPECIES". It can also be an intermediate, such as the probeset ID as used in the tutorial for the transcripts. The next column(s) would contain your expression data. For this tutorial, data were clustered, and each expression pattern was represented with a letter in only one column. However, any type of data can be uploaded, including expression values for each condition in one column. The Node Color attribute in Vizmapper can be modified accordingly. The visual style is highly customizable and any kind of attribute can be modified according to the expression.

5.2 Visualizing expression data
When the expression data are loaded, nodes corresponding to metabolites, transcripts, and proteins with differential abundance appear with colors representing their respective abundance. Sometimes the colors don't appear when the networks are loaded. Click on Node color and Discrete mapping. The colors will need to be redefined. Only the expression clusters present on the pathway that you have opened will be visible.
