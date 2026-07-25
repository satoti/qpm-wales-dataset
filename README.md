# QPM Wales Dataset

This is the Wales dataset produced by the Qualitative Place Model (QPM), the framework developed for the PhD thesis *Qualitative Representation and Management of Place in GIS: A Multi-Hierarchical Framework* (Cardiff University). It holds the places and the administrative, electoral and postal units of Wales as the model describes them qualitatively, the qualitative spatial relationships between them, and the SPARQL queries used to test the model in the thesis.

The aim of the work is to represent places and units qualitatively and natively inside a GIS, so their locations can be described qualitatively through meaningful spatial relations (direction, containment and proximity) rather than through coordinates alone. The RDF provided here is the exported output of the model, in a form that can be reasoned over and queried. These files are therefore the model's output for Wales together with the queries that test it, and they allow the results reported in the thesis to be reproduced.

## What the dataset contains

**QPM\_Wales\_Places\_DataSet.ttl.gz** holds the Welsh places together with the full administrative spatial units that contain them: all 52,821 places of Wales together with the complete administrative hierarchy (1,720 units), with point geometry stored as GeoSPARQL WKT. This is the place-level dataset behind the place analysis in the thesis, including the qualitative place descriptions (directional and containment relations), and it is the graph the queries asked at the scale of the whole of Wales are run against.

**QPM\_Administrative\_Hierarchy.ttl.gz**, **QPM\_Electoral\_Hierarchy.ttl.gz** and **QPM\_Postal\_Hierarchy.ttl.gz** hold the three traditional hierarchies of Wales, each as its own graph, with their qualitative place descriptions (directional and containment relations) and DGGS representations (1,720 administrative units, 775 electoral units and 747 postal units respectively).

Each hierarchy is provided as a separate graph because each one is evaluated on its own in the thesis. The uniqueness of the qualitative place descriptions is tested within each hierarchy separately, the coverage of each hierarchy is measured separately, and these are the graphs on which the inverse and transitive closure is applied, so that the inferential gain of each hierarchy can be reported by itself before the hierarchies are considered together.

**QPM\_CrossHierarchy\_Evaluation\_Graph.ttl.gz** holds the qualitative spatial relationships that hold between units of different hierarchies, together with the H3 and S2 discrete global grid representations and the qualitatively created places. These are the parts of the model presented in the later chapters (Chapters 4 to 6), and this is the graph most of the competency-question evaluation is run against.

**QPM\_Competency\_Question\_Queries\_Thesis.txt** holds the SPARQL queries behind the evaluation. Each query is documented, includes the code to load the relevant graph and run it, and states the graph it is run against, so any query can be copied and run on its own.

## Format and vocabulary

The graphs are in RDF/Turtle and the geometry uses GeoSPARQL (`geo:asWKT`). The model vocabulary uses the namespace:

&#x20;  @prefix qpm: <http://qpm.ontology/2025#> .


The graphs are provided gzip-compressed (`.ttl.gz`) and should be decompressed before use, or loaded with a tool that reads gzipped Turtle directly.

## Loading the graphs

The graphs should be loaded and queried separately, or each into its own named graph, and are not meant to be merged into a single graph.

## Source data and licence

The place and boundary data are derived from Ordnance Survey OpenData, © Crown copyright and database right, used under the Open Government Licence and processed to the extent of Wales. This dataset is released under the Creative Commons Attribution 4.0 International (CC BY 4.0) licence.

## Citing this dataset

Please cite the thesis and this dataset:

Abdurauf Satoti, 2026, \*Qualitative Representation and Management of Place in GIS: A Multi-Hierarchical Framework\*, PhD thesis, Cardiff University. Dataset DOI: https://doi.org/10.5281/zenodo.21542540.

