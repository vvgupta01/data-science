#### Introduction
The fundamental business problem underlying the basis of this project is as follows: <br><br>
A small business currently based in Toronto, Canada seeks to expand its business by opening a new office within a major city in America. 
The primary criteria for selecting a location includes its similarity with Toronto based on the types of venues available near each neighborhood. Among the potential candidate cities is Manhattan, New York, which appears similar to Toronto due their status as diverse, financial capitals of their respective countries. As such, stakeholders within the business seek to validate the similarity between neighborhoods in Toronto and Manhattan to ensure whether or not Manhattan should be considered as a potential location.

#### Data
Data required to solve the business problem included both location and geographical data regarding neighborhoods within Toronto and Manhattan. In order to obtain geographical data from Toronto, neighborhoods were grouped based on Canadian postal codes provided by Wikipedia and concatenated with coordinate data provided by Coursera. The following dataset was filtered to include only neighborhoods located within Toronto (East, Central, and West boroughs). <br><br>
Geographical data from New York was provided by Coursera and filtered to include only neighborhoods located within Manhattan. <br><br>
All location data was provided by Foursquare API to retrieve the top 100 venues located within a 500 meter radius of each neighborhood in Toronto and Manhattan. The top 5 venue types of each neighborhood were analyzed to derive the top unique venue types of each city in order to calculate similarity.
