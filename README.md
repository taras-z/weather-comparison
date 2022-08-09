# Weather Comparison
The weather comparison is based on METAR records.

## Goal
Some people are weather-sensitive.
Presumably, a part of them reacts to the speed of air pressure changes.
This  tiny research of weather records may help them to select a region with consistent air pressure.
Moreover, you can use this approach for other weather conditions.

## Processing
If you want to execute the Notebook and make a comparison yourself or compare other countries/cities(stations),
you need to [prepare the environment](./ENV_PREPARE.md) and perform the following steps.

### Data gathering
Firstly, you must download the relevant datasets from
[Iowa State University ASOS Archive](https://mesonet.agron.iastate.edu/request/download.phtml),
add them to the subfolder `./data`, and load the data of each country to the separate pandas DataFrame.
The next steps must be performed on each dataset separately.

### Data extracting 
Secondly, for better result you are strongly recommended to select several stations for analysis. 
You must provide 3- or 4-letters codes of the meteo stations.
You can find them when you download the data (see the first step). 

### Drop invalid data
Next, you can drop values outside the valid region of air pressure.
In case of selecting other weather conditions, you must choose another region for data validation.   

### Check values
Then, you audit the values for extremely incorrect data.
If you see values which are too low or too high, you must adjust the data validation region and
re-run steps from 'Data extracting'. 

### Check the amount of data
At the last preparation step, you need to check the amount of valid values for each station.
Perhaps, at the data dropping step, you could have dropped too many values and the data became unsuitable for analysis.
I have no strict rules for that, you have to decide intuitively. If you have the rules, please let me know. 

## Results
At the end of the work, you must concatenate all DataFrames into a single one,
calculate the standard deviation for each station, and show results in tabular and graphical forms.

## Further improvements
If I should prepare this work for production , I will improve/realise the next features:
1. Store configuration of research in separate files
2. Create a function to download and prepare the dataset (according to the config)
3. Create a function to combine the result dataset
4. Create a function to save/prepare the research report

## Contacts

Your feedback is welcome in the [Issue Section](https://github.com/taras-z/weather-comparison/issues).