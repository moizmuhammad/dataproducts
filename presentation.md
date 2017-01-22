Data Converter (wide to long format)
========================================================
author: Moiz 
date:   Jan 2017

Overview
========================================================

- Published data is often available in wide format

- Data Converter is a simple web service for converting data in wide format 
to long format.

- With this utility any person can convert data (no need to learn or install R)


Wide Format vs Long Format
========================================================
A sample wide format data is shown below

```
   country X2000 X2001 X2003 X2004
1 Pakistan    20    18    15    17
2      USA     5     8     3     2
```
The same data in long format will be represented as

```
   country Year Value
1 Pakistan 2000    20
2      USA 2000     5
3 Pakistan 2001    18
4      USA 2001     8
5       .. ....     .
```


How The Service Works
========================================================

- User uploads the data file in csv format 

- User inputs the total number of id variables. 

- The Service converts the data to long format

- The Service provides a download link 


Service Implementation Details
========================================================

- This service is implementated using the reshape library

- Reshape library has a function called melt that accepts a data frame and a list of id variable for conversion.

- For example to convert the sample data in slide# 2, following command is issued

```r
  melt(dataframe, id=names(dataframe[1])) 
```

- Here dataframe is a object that holds the uploaded data file using read.csv command

Future Enhancements
========================================================

- support for conversion long to wide format

- support for accepting other file formats like tab
