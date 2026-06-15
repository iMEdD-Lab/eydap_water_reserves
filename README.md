
# Eydap water reserves tracker

A repository that contains the entire data of EYDAP on the water reserves of Attica, from 1985 to the latest date, and utilises a python script to download the most recent data.

The dataset contains the daily amount of cubic meters of extractable reserves of the reservoirs:
1. Eyinos
2. Marathonas
3. Mornos
4. Yliki
5. Total amount of water between all the reservoirs

## Files
The repository contains 3 .csv files: 
1. water_reserves_old: a fallback file that contains the data from 1985 to 6/6/2026 and remains unchanged.
2. water_reserves_latest: the file that the latest data is appended to.
3. latest_day_compare: a file that contains the data of the latest day available, and the equivalent date of previous years.

The eydap_rss_downloader.py contains the code that is run daily (except weekends, when EYDAP does not refreshes its data) via Github Actions. It gets the RSS feed from EYDAP, formats the data as a dataframe, loads the historical data and builds a dataframe that contains both the historical and the latest recordings. 
Also, the function build_latest_day_compare in the code finds the latest date in the df, and gets those recordings, as well those of the equivalent date of all the previous years. 
