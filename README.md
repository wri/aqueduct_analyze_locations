# Aqueduct Water Risk Atlas | Analyze locations instructions

The Aqueduct Water Risk Atlas allows users to import files with coordinates or addresses. This repo holds the sample excel files and instructions.   

This repo is intended for Vizzuality to pull files from the water risk atlas tool and allows for version control. 

## Input templates

#### Coordinates
[coordinate template](https://github.com/wri/aqueduct_analyze_locations/blob/master/input_templates/example_coordinates.csv)


#### Addresses
[address template](https://github.com/wri/aqueduct_analyze_locations/blob/master/input_templates/example_address.csv)  
[address FAQ](https://github.com/wri/aqueduct_analyze_locations/blob/master/address_faq.md)


## Export templates
After analyzing the locations, users can export the results. 

The format of the first few columns in the output data depends on whether coordinates or addresses have been used as input.

#### First columns when using coordinates
For coordinates, the only difference is a first column with the unique identifier.   
[coordinate template](https://github.com/wri/aqueduct_analyze_locations/blob/master/result_templates/results_first_columns_coordinates.csv)

#### First columns when using adresses
For addresses, keep both the input and match addresses, latitude and longitude. 
[address template](https://github.com/wri/aqueduct_analyze_locations/blob/master/result_templates/results_first_columns_adrresses.csv)

#### Remainder of the columns

The remainder of the files / columns should should contain **all** the results:
1. Annual.  
1. Monthly.  
1. Future Projections. 

There are a few options:

1. Combine the results in a single .xlsx file with tabs. 

  Please try exporting the results after analyzing locations in our [old tool](https://www.wri.org/applications/maps/aqueduct-    atlas)   

Pros: All data in one place, no encoding issues

2. Export a zipped folder with the different results in .csv files  

  Pros: easier since csv is a Carto standard.  
  Cons: However this **WILL** result in encoding issues. Users will double click the csv file and the UTF-8 endcoding will be lost based on the user locale setting  

Users need to understand the results so either convert the columns into human readable format, or include the dicitonary format.

For the annual results:  
template  
dictionary  

For monthly results:
template  
dictionary  

For future projections results:  
template  
dictionary  











