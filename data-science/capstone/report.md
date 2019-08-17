### I. Introduction
#### 1.1 Background
A small business currently located in Toronto offers services to other business and venues within the city. The business seeks to expand its operations by opening a new office within America. The primary criteria for selecting a location largely involves its similarity with Toronto based on the types of venues around each neighborhood. Among the potential cities to open a new office in, Manhattan appears to be a strong candidate due to its shared status with Toronto as a diverse, financial capital. 
#### 1.2 Business Focus
Although from a general overview Manhattan appears similar to Toronto, the stakeholders within the business would like to perform a deeper analysis regarding the types of venues within both cities to validate their internal similarity. Additionally, if Manhattan is found to be similar to Toronto (>50%), the business would like to find the most common venue type between both cities in order to better focus on those venues.
#### 1.3 Business Interest
The business is interested in identifying potential cities that are similar to Toronto in order to extend their current business model into new locations with minimum change. Furthermore, finding common venue types between both cities will enable the business to better target these venues, maximizing their potential client base.

### II. Data Acquisition
#### 2.1 Data Sources
Data included both location and geographical data regarding neighborhoods in Toronto and Manhattan. In order to obtain geographical data from Toronto, neighborhoods were grouped based on Canadian postal codes provided by [Wikipedia](https://en.wikipedia.org/wiki/List_of_postal_codes_of_Canada:_M) and concatenated with coordinate data provided by [Coursera](https://cocl.us/Geospatial_data). The resultant dataset was filtered to include only neighborhoods located within Toronto (Central, East, West, and Downtown boroughs). <br>
Geographical data from New York was provided by [Coursera](https://cocl.us/new_york_dataset) and filtered to include only neighborhoods located within Manhattan. <br>
All location data was provided by [Foursquare API](https://foursquare.com/) to retrieve the top 100 venues located within a 500 meter radius of each neighborhood in Toronto and Manhattan. The top 5 venue types of each neighborhood were analyzed to derive the frequency of top venue types within each city in order to calculate similarity.
#### 2.2 Data Cleaning
Geographical data regarding neighborhoods in Toronto were extracted from a CSV file and processed into a dataframe containing the code, borough, and neighborhood of each postal code. Postal codes with multiple neighborhoods were concatenated into a single entry, while postal codes with an unassigned borough were dropped. However, postal codes with an unassigned neighborhood were assigned the same name as the borough. Coordinate data was extracted from a CSV file and concatenated to the dataframe as latitude and longitude. <br>
Geographical data regarding neighborhoods in Manhattan were extracted from a JSON file and processed into a dataframe containing the borough, name, latitude, and longitude of each neighborhood. 
#### 2.3 Feature Extraction
Following data cleaning, each dataset contained four features: the borough, name, latitude, and longitude of each neighborhood. There were a total of 38 neighborhoods in Toronto and 40 neighborhoods in Manhattan. No other features were necessary in order to retrieve location data.

### III. Exploratory Data Analysis
