### I. Introduction
#### 1.1 Background
A small business currently located in Toronto offers services to other business and venues within the city. The business seeks to expand its operations by opening a new office within America. The primary criteria for selecting a location largely involves its similarity with Toronto based on the types of venues around each neighborhood. Among the potential cities to open a new office in, Manhattan appears to be a strong candidate due to its shared status with Toronto as a diverse, financial capital. 
#### 1.2 Business Focus
Although from a general overview Manhattan appears similar to Toronto, the stakeholders within the business would like to perform a deeper analysis regarding the types of venues within Manhattan. 
#### 1.3 Interest


### Data Acquisition
#### Data Sources
Data required to solve the business problem included both location and geographical data regarding neighborhoods within Toronto and Manhattan. In order to obtain geographical data from Toronto, neighborhoods were grouped based on Canadian postal codes provided by Wikipedia and concatenated with coordinate data provided by Coursera. The following dataset was filtered to include only neighborhoods located within Toronto (East, Central, and West boroughs). <br><br>
Geographical data from New York was provided by Coursera and filtered to include only neighborhoods located within Manhattan. <br><br>
All location data was provided by Foursquare API to retrieve the top 100 venues located within a 500 meter radius of each neighborhood in Toronto and Manhattan. The top 5 venue types of each neighborhood were analyzed to derive the top unique venue types of each city in order to calculate similarity.
