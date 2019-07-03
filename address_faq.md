# Instructions for using files with addresses.

## **Q: How should I format my excel address file?**

A: Your excel file should contain two columns: location name and address. See the [template](https://github.com/wri/aqueduct_analyze_locations/blob/master/example_coordinates.csv)

If your address components (street name, city, county) are in different columns, you should merge them into a single column. See the questions below on how to merge columns.  


## **Q: I have an excel file where street name, city and country are in separate columns, how can I combine them into one column?**

A: In Excel and Google Sheets, you can use =TEXTJOIN()  

As delimiter you can use a comma “,” or a comma and space “, “ 
for ignore_empty you can use TRUE 

=TEXTJOIN(", ",TRUE,A2:D2) 

Change the range (A2:D2) to match your input data. 

Finally, copy the values (not the formulas) of the site name and address columns to a new excel file and safe as .csv or .xlsx. To copy the values only, selected both columns by holding Ctrl and paste using Ctrl+Alt+V  

## **Q: What is the preferred address format?**

A: Your address format should be in the following [format](https://developers.google.com/maps/faq#geocoder_queryformat):
1.  Specify addresses in accordance with the format used by the national postal service of the country concerned.  
1.  Do **not** specify additional address elements such as business names, unit numbers, floor numbers, or suite numbers that are not included in the address as defined by the postal service of the country concerned.   
1.  Use the street number of a premise in preference to the building name where possible.
1.  Use street number addressing in preference to specifying cross streets where possible.  
1.  Do not provide 'hints' such as nearby landmarks.  

You can test individual addresses [here](https://google-developers.appspot.com/maps/documentation/utils/geocoder/)

## **Q: I don’t know the exact street name, what should I do?**

A: Results are only as good as the input data so always try to check your input data before running the analysis. We use the centroid of the spatial unit defined by the user. If the user specifies a city without a street, we use the centroid of the city. Always be as specific as possible.  
