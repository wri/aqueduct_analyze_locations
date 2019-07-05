This document will help you understand the downloaded Aqueduct data. Before diving into the results, make sure to familiarize yourself with our technical notes (todo:insert link). For questions, check out our FAQ page (todo:insert link)

Downloaded data comes in three flavors:
1. Annual Baseline
1. Monthly Baseline
1. Future Projection

# Annual Baseline

## Identifiers:  
**string_id**, string, contains a unique string for each geometry. Geometries are the union of hydrological basins, provinces and groundwater aquifers. The string_id is a combination of pfaf_id-gid_1-aqid. See the description of those columns.  
**aq30_id**, numerical, unique identifier.  
**pfaf_id**, numerical, six digit Pfafstetter code for the hydrological basins.  
**gid_1**, string, identifier for sub-national units based on the GADM dataset. It contains the Iso A3 country code, followed by numeric values separated by underscores for each sub-national unit.   
**aqid**, numerical, identifier for groundwater Aquifers based on WHYMAP.   

## Extra identifiers:  
**gid_0**, string, ISO A3 country code based on GADM. See GADM for more information.   
**name_0**, string, National or political entity name based on GADM. See GADM for more information.    
**name_1**, string, Sub-national or political entity name based on GADM, See GADM for more information.   
**area_km2**, numerical, area of the geometry in km2 (union of sub-basin, province and groundwater aquifer).  

## Indicators: 

For each of the 13 indicators the columns contain the indicator abbreviation plus the type {indicator}\_{type}, e.g.:  
"bws_raw" is baseline water stress, raw value. The indicator abbreviations and types are listed below.  

### Physical risk quantity:  
**bws**, Baseline water stress,  
**bwd**, Baseline water depletion,  
**iav**, Interannual variability,  
**sev**, Seasonal variability,  
**gtd**, Groundwater table decline,  
**rfr**, Riverine flood risk,  
**cfr**, Coastal flood risk,  
**drr**, Drought risk

### Physical risk quality:
**ucw**, Untreated connected wastewater,  
**cep**, Coastal eutrophication potential.

### Regulatory and reputational risk:
**udw**, Unimproved/no drinking water,   
**usa**, Unimproved/no sanitation,  
**rri**, Peak RepRisk ESG index.  

## Types:  
**\_raw**, double, raw value. Units depend on the indicator. See the technical note.  
**\_score**, double, each indicator is mapped to a [0-5] scale.  
**\_label**, string, A label explaining the category of the indicator includin threshold. e.g. "Extremely High (more than 1 in 100)"  
**\_cat**, integer, integer for each category [-1,4], can be used for visuals.  

## Grouped water risk

see the technical note for a description of aggregating the 13 indicators into sub-groups and an overall water risk score using the composite index approach. The grouped water risk scores use the follwing format:

w_awr_{weightingscheme}\_{group}\_{type}  

w_awr, stand for weighted aggregated water risk. Mainly used to keep them separate from the remaining indicators.    

e.g. w_awr_min_rrr_score is the aggregated score using the mining weighting scheme for the regulatory and reputational risk group.


### Weighting Scheme
**def**, Default  
**agr**, Agriculture  
**che**, Chemicals  
**con**, Construction Materials  
**elp**, Electric Power  
**fnb**, Food & Beverage  
**min**, Mining  
**ong**, Oil & Gas  
**smc**, Semiconductor  
**tex**, Textile  

### Groups

**qan**, Physical risk quantity  
**qal**, Physical risk quality  
**rrr**, Regulatory and reputational risk    
**tot**, Total, Overall water risk.

### Types

In addition to the types for the individual indicators, we have
\_weight_fraction, the fraction [0-1] of the group towards the overall water risk score. NoData is excluded from the weights and therefore the fractions can be lower than 1 depending on data availability. See the technical note for the weights per industy and indicator.  

# Monthly Baseline



# Future Projection

There are four indicators, three target years, three scenarios, three data types	

## Identifiers  
**BasinID**, integer, Sub-basin identifiers.   
**dwnBasinID**, integer, Next downstream sub-basin.   
**Area_km2**, double, Area of sub-basin in square kilometer.
**Shape_Leng**, double, Perimeter of the sub-basin in kilometer.  
	
## Indicators  
The indicators use the following format:  
{II}{YY}{SS}{R}{X}	 

II,	indicator code  
YY,	year code   
SS, scenario code    
T, data type code    
X, suffix    

### {II}	Indicator codes  
ws	water stress  
sv	seasonal variability  
ut	water demand  
bt	water supply  
	
### {YY}	Year codes  
20	2020  
30	2030  
40	2040  
	
### {SS}	Scenario codes  
24	ssp2 rcp45 (optimistic)  
28	ssp2 rcp85 (business as usual)  
38	ssp3 rcp85 (pessimistic)  
	
### {T}	Data types  
c	change from baseline  
t	future value  
u	uncertainty value  
	
### {X}	Suffixes  
l	label string  
r	raw value  
	
For example the layer {ws4028cl} is "projected change in water stress by the year 2040 under a business as usual (ssp2 rcp85) scenario"	 










