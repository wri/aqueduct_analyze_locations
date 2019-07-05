
Date: 2019/07/05
Author: Rutger Hofste

Thank you for downloading Aqueduct data. This document will help you understand the data. Before diving into the results, make sure to familirize yourself with our technical notes (todo:insert link). For questions, check out our FAQ page (todo:insert link)

Downloaded data comes in three flavors:
1. Annual Baseline
1. Monthly Baseline
1. Future Projection

# Annual Baseline

Identifiers:  
**string_id**, string, contains a unique string for each geometry. Geometries are the union of hydrological basins, provinces and groundwater aquifers. The string_id is a combination of pfaf_id-gid_1-aqid. See the description of those columns.  
**aq30_id**, numerical, unique identifier.  
**pfaf_id**, numerical, six digit Pfafstetter code for the hydrological basins.  
**gid_1**, string, identifier for sub-national units based on the GADM dataset. It Iso A3 country code, followed by numeric values separated by underscores for each sub-national unit.   
**aqid**, numerical, identifier for groundwater Aquifers based on WHYMAP.   

Extra identifiers:
**gid_0**, string, ISO A3 country name based on GADM. See GADM for more information.   
**name_0**, string, National or political entity name based on GADM. See GADM for more information.    
**name_1**, string, Sub-national or political entity name based on GADM, See GADM for more information.   

Indicator columns:  

Grouped columns:  







