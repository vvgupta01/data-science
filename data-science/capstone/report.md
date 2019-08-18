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
Following data cleaning, each dataset contained four columns: the borough, name, latitude, and longitude of each neighborhood. There were a total of 38 neighborhoods in Toronto and 40 neighborhoods in Manhattan. <br>
Features within the dataset included the top 5 venue types for each neighborhood, which were appended to each dataset and analyzed following venue retrieval. 

### III. Exploratory Data Analysis
#### 3.1 Venue Analysis
Following venue exploration, a total of 1689 venues were retrieved from Toronto representing 236 unique venue types, while a total of 3317 venues were retrieved from Manhattan representing 337 unique venue types. As the top 5 venue types for each neighborhood were considered, a total of 190 top venue types for Toronto and 200 top venue types for Manhattan were analyzed, representing 81 and 65 unique top venue types respectively.

| City      | Neighborhoods | Venues | Venue Types | Top Venues | Top Venue Types |
| --------- | ------------- | ------ | ----------- | ---------- | --------------- |
| Toronto   | 38            | 1689   | 236         | 190        | 81              |
| Manhattan | 40            | 3317   | 337         | 200        | 65              |

#### 3.2 Venue Frequency
Following venue analysis, venues for each city were one-hot encoded and grouped together by venue type before being averaged. The most common venue types were found for each city, as well as the most common venue types between cities. The most common venue types within each city are as follows:

Toronto | Top Venue Type     | Frequency | Manhattan | Top Venue Type     | Frequency |
------- | ------------------ | --------- | --------- | ------------------ | --------- |
1       | Coffee Shop        | 0.115789  | 1         | Coffee Shop        | 0.090     |
2       | Cafe               | 0.105263  | 2         | Italian Restaurant | 0.085     |
3       | Italian Restaurant | 0.057895  | 3         | Pizza Place        | 0.055     |
4       | Restaurant         | 0.052632  | 4         | Cafe               | 0.050     |
5       | Park               | 0.047368  | 5         | Bar                | 0.045     |

Similarily, the most common venue types between cities are as follows:

| Top Venue Type     | Average Frequency |
| ------------------ | ----------------- |
| Coffee Shop        | 0.1028950         |
| Cafe               | 0.0776316         |
| Italian Restaurant | 0.0714474         |
| Park               | 0.0436842         |
| Hotel              | 0.0332895         |

The similarity index between Toronto and Manhattan was calculated based on the shared frequency of top venue types located in both cities. 

#### 3.3 Neighborhood Clustering
Neighborhoods within Toronto and Manhattan were partitioned into k=5 clusters through k-means clustering in order to better visualize the types of venues located in both cities. The investigation summary of each cluster is as follows:

| Cluster | Neighborhoods | Representation | Label      |
| ------- | ------------- | -------------- | ---------- |
| 0       | 13            | 16.66667%      | Store      |
| 1       | 4             | 5.128205%      | Park/Bus   |
| 2       | 59            | 75.64103%      | Food       |
| 3       | 1             | 1.282051%      | Garden     |
| 4       | 1             | 1.282051%      | Playground |

All clusters were represented by the neighborhoods in Toronto; however, only clusters 0 and 2 were represented by the neighborhoods in Manhattan. Even so, cluster 2 was the most common cluster consisting of over 75% of neighborhoods in both cities, while clusters 3 and 4 were only represented by a single neighborhood each. 

### IV. Results
_Note: Basic results regarding venue analysis can be found in the above section. This section references datasets in the above section to provide a more focused analysis._
#### 4.1 Venue Analysis Results
On the surface, both Manhattan and Toronto contain similar amount of neighborhoods, suggesting they are internally similar. However, the he venue analysis suggests Manhattan contains nearly twice as many venues as Toronto (~196%), with Toronto and Manhattan having an average of 44 and 83 venues per neighborhood within a 500 meter radius respectively. Similarily, due to the significant difference in venues, Manhattan contains approximately 43% more unique venue types, suggesting its city is more diverse than Toronto. However, when comparing the top venue types of each city, Toronto has approximately 25% more unique venue types. This suggests that while Manhattan has more diversity in terms of venues available, Toronto has more diversity and consistency in terms of common venues. <br>
Despite their differences, Toronto and Manhattan also share several venue types, representing a total of 380 venue types with 66% venue type similarity. Further analysis into the frequency of top venue types between both cities reveals that the most common venues are coffee shops, which are represented in over 10% of all neighborhoods. Together, the top five shared venue types represent nearly a third (~33%) of all neighborhoods. A full analysis yields a similarity index of 50.8684%, suggesting that over half the frequency of top venue types in Toronto are shared with Manhattan.
#### 4.2 Cluster Analysis Results
Clustered maps for Toronto and Manhattan respectively are as follows:
![Toronto Cluster Map](res/toronto_cluster_map.jpg "Toronto Cluster Map")
![Manhattan Cluster Map](res/manhattan_cluster_map.jpg "Manhattan Cluster Map")
