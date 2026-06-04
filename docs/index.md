---
title: Extracting geographic features from a larger dataset in QGIS   # Title of the page, which will be displayed in the navigation and the browser title.
layout: page  # Layout type, usually 'page' for standard pages.
nav_order: 1  # Order in the navigation menu.
description: This tutorial will demonstrate how to use QGIS to extract just the features you need from larger spatial datasets, saving them to new files that you can then use to map and analyze your data.   # A brief description of the page for SEO purposes.
permalink: /  # Optional: Custom URL for the page. It will serve as the slug. For example, /home/
created_date:  # Date when the page was created. Should be in YYYY-MM-DD format.
has_children: False  # Set to True if the page has sub-pages.
staff:  # Optional: Nested list of staff members associated with the page.
  - name: Cole White  # PLACEHOLDER: Replace with actual staff member's name.
    link: https://library.utoronto.ca/staff/cole-white # link is optional
maintainer:
  - name: Cole White  # PLACEHOLDER: Replace with actual maintainer's name.
    link: https://library.utoronto.ca/staff/cole-white  # link is optional
# student_staff:  
# - name: Student Name
#   link: https://example.com/student-name
# - name: Another Student
#   link: https://example.com/another-student  # link is optional
---
# Extracting geographic features from a larger dataset in QGIS

You may have noticed that many GIS datasets contain information about a
geographic extent that is larger than your area of interest.

<b>Example:</b> This Statistics Canada layer (downloaded from 
<a href="https://www12.statcan.gc.ca/census-recensement/2021/geo/sip-pis/boundary-limites/index2021-eng.cfm?year=21"
target="_blank">this page</a>), displays all census dissemination areas within
Canada. Suppose you only need to work with (for example) Nova Scotia’s
dissemination areas. This tutorial will demonstrate how to extract just the
features you need, saving them to new files that you can then use to map and
analyze your data.

<a href='{{ '/assets/images/lda.png' | relative_url }}' target="_blank">
<img src='{{ '/assets/images/lda.png' | relative_url }}' alt="Canada
census dissemination area polygons" width='100%' height='100%'  style="border:
3px solid #888888;" />
</a>

### Using Select by Expression


• Open <b>QGIS</b> and load the layer you'd like to extract a subset of features from.

<a href='{{ '/assets/images/qgis-layer-to-subset.png' | relative_url }}' target="_blank">
<img src='{{ '/assets/images/qgis-layer-to-subset.png' | relative_url }}' alt="
Layer to subset in QGIS" width='100%' height='100%' style="border: 3px solid #888888;" />
</a>

• Right-click the layer name in the <b>Layers panel</b> and choose <b>Open
attribute table</b>.

<a href='{{ '/assets/images/qgis-open-attribute-table.png' | relative_url }}' target="_blank">
<img src='{{ '/assets/images/qgis-open-attribute-table.png' | relative_url }}' alt="
Right-click layer -> Open attribute table" width='70%' style="border: 3px solid #888888;" />
</a>

• Click the <b>Select by expression</b> button.

<a href='{{ '/assets/images/qgis-select-by-expression.png' | relative_url }}' target="_blank">
<img src='{{ '/assets/images/qgis-select-by-expression.png' | relative_url }}' alt="
Attribute table -> Select by expression" width='100%' height='100%' style="border: 3px solid #888888;" />
</a>

• <b>Build a query</b> to select your features of interest (more information on
queries in QGIS can be found
<a href = "https://docs.qgis.org/latest/en/docs/user_manual/expressions/expression.html" target="_blank">
in the official documentation.</a>). Click <b>Select features</b>, then click
<b>Close</b>.

<a href='{{ '/assets/images/qgis-selection-query.png' | relative_url }}' target="_blank">
<img src='{{ '/assets/images/qgis-selection-query.png' | relative_url }}' alt='
QGIS selection expression - in this example, "PRUID" = 12' width='100%' height='100%' style="border: 3px solid #888888;" />
</a>

• Result: selected features will be <b>highlighted in yellow</b> on the map canvas, and the
count of selected features will be displayed in the QGIS status bar.

<a href='{{ '/assets/images/qgis-selected-features.png' | relative_url }}' target="_blank">
<img src='{{ '/assets/images/qgis-selected-features.png' | relative_url }}' alt='
Display of selected features in QGIS.' width='100%' height='100%' style="border: 3px solid #888888;" />
</a>

• Right-click the layer name again and choose <b>Export -> Save Selected
Features As...</b>

<a href='{{ '/assets/images/save-selected-features-as.png' | relative_url }}' target="_blank">
<img src='{{ '/assets/images/save-selected-features-as.png' | relative_url }}' alt='
Export -> Save selected features as' width='100%' height='100%' style="border: 3px solid #888888;" />
</a>

• Save the output to your computer as an <b>Esri Shapefile</b>. Click <b>OK</b>.

<a href='{{ '/assets/images/save-as-shapefile.png' | relative_url }}' target="_blank">
<img src='{{ '/assets/images/save-as-shapefile.png' | relative_url }}' alt='
Save as shapefile' width='100%' height='100%' style="border: 3px solid #888888;" />
</a>

### Interactive selections using the attribute table or the map

You can also hand pick individual features for export.

• Open the <b>attribute table</b>. 

<a href='{{ '/assets/images/qgis-open-attribute-table.png' | relative_url }}' target="_blank">
<img src='{{ '/assets/images/qgis-open-attribute-table.png' | relative_url }}' alt="
Right-click layer -> Open attribute table" width='70%' style="border: 3px solid #888888;" />
</a>

• Click the <b>row number box</b> to the left of your record of interest to select it
(the High Park dissemination area in Toronto, in this example). The
attribute table row and its corresponding map feature will be highlighted.
You can Shift-click or Control-click to select multiple records.

<a href='{{ '/assets/images/selection-in-attribute-table.png' | relative_url }}' target="_blank">
<img src='{{ '/assets/images/selection-in-attribute-table.png' | relative_url }}' alt="
Attribute table with one row selected" width='100%' height='100%' style="border: 3px solid #888888;" />
</a>

• If you'd prefer to select features from the <b>map</b> rather than the attribute
table, use the <b>Select</b> tool to do this. Shift-click or Control-click to
select multiple map features.

<a href='{{ '/assets/images/qgis-select-tool.png' | relative_url }}' target="_blank">
<img src='{{ '/assets/images/qgis-select-tool.png' | relative_url }}' alt="
QGIS select tool" width='100%' height='100%' style="border: 3px solid #888888;" />
</a>

• Once you've selected your feature or features of interest, <b>right-click the
layer name</b> again and choose <b>Export -> Save Selected Features As...</b>

<a href='{{ '/assets/images/save-selected-features-as.png' | relative_url }}' target="_blank">
<img src='{{ '/assets/images/save-selected-features-as.png' | relative_url }}' alt='
Export -> Save selected features as' width='100%' height='100%' style="border: 3px solid #888888;" />
</a>

• Save the output to your computer as an <b>Esri Shapefile</b>. Click <b>OK</b>.

<a href='{{ '/assets/images/export-high-park.png' | relative_url }}' target="_blank">
<img src='{{ '/assets/images/export-high-park.png' | relative_url }}' alt='
Save as shapefile' width='100%' height='100%' style="border: 3px solid #888888;" />
</a>

**Techniques:** [Extracting data](https://mdlutoronto.github.io/tutorials-search/?technique=Extracting+data) \|
**Tools:** [QGIS](https://mdlutoronto.github.io/tutorials-search/?tool=QGIS) \|
**Data Format:** [Vector](https://mdlutoronto.github.io/tutorials-search/?dataFormat=Vector)