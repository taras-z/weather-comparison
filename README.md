# Weather Comparison
The weather comparison in different countries is based on METAR records.

## Goal
Some people are weather-sensitive.
Presumably part of them reacts to the speed of air pressure changes.
This nano-research of weather records might help them to select a region with stable air pressure.
Moreover, it's possible to create a comparison of other weather conditions.

## Method
If you want to execute the Notebook and make the comparison yourself or,
might be, compare other countries/cities(stations), you need to perform next steps.

### Data gathering
Firstly, you must download the necessary datasets from
[Iowa State University ASOS Archive](https://mesonet.agron.iastate.edu/request/download.phtml),
put them to the subfolder './data', and load the data of each country to the separate pandas DataFrame.
The next steps must be performed on each one.

### Data extracting 
Secondly, you, probably, want to select a few stations for analysis. 
You must provide 3- or 4-letters codes of meteo stations.
You may find them during the data downloading (see the first step). 

### Drop invalid data
Next, you can drop values outside the valid region of air pressure.
In case of selecting other weather conditions, you must choose another region for data validation.   

### Check values
Then you might audit the values for extremely incorrect data.
If you see too low or too high values, you may tune the data validation region and re-run steps from 'Data extracting'. 
Then you might compute the standard deviation along all data for a country. It's pretty useless :-) because
the datasets consist of values from different stations (in my opinion different environments don't give us chance to
compare the data like that).

### Check the amount of data
At the last preparation step, you might check the amount of valid values by the stations.
Perhaps in the data dropping step, you might drop too many values and the data became unsuitable for analysing.
I have no strict rules for that, you must decide intuitively. If you have the rules, please let me know. 

## Results
At the end of work, you might concatenate all DataFrames into a single one,
calculate the standard deviation for each station, 
and show results in tabular and graphical forms.

## Further improvements
If I should prepare this work for production, I will improve/realise the next features:
1. Store configuration of research in separate files
2. Create the function to download and prepare the dataset (according to the config)
3. Create the function to combine the result dataset
4. Create the function to save/prepare the research report
