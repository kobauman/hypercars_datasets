# HyperCARS Datasets for Context-Aware Recommender Systems Research

This repository provides datasets that were used in the following paper:
"_HyperCARS: Using Hyperbolic Embeddings for Generating Hierarchical Contextual Situations in Context-Aware Recommender Systems_" 
published in the Information Systems Research journal: https://doi.org/10.1287/isre.2022.0202


### Gowalla Check-in Data

**Gowalla** is a location-based social network platform that enables users to check-in to points of interest (POIs) they visit. Those POIs are grouped into seven categories: Community, Entertainment, Food, Nightlife, Outdoors, Shopping, and Travel. 
Most check-ins in Gowalla came from major cities in the US. The original data was taken from: https://snap.stanford.edu/data/loc-gowalla.html

In our study, we used POIs from New York City (NYC) and San Francisco (SF) because their locations are very dense in these areas. Therefore, many users visit multiple POIs within short periods of time, which constitutes rich contextual information. We calculated **twelve** contextual variables: "_time of the day_," "_day of the week_" (weekday/weekend), "_season_," "_number of check-ins_," "_distance traveled_," and seven variables revealing which of the main categories were visited within the previous three hours. 

In particular, for each check-in, we analyzed other check-ins made by the same user within the previous _three hours_ revealing his/her previous actions that serve as additional contextual information. Within those time windows, we calculated the number of check-ins and the categories of visited places. In particular, for each of the seven main categories, we calculated the percentage of locations from that category visited within the previous three hours. Based on this information, we created categorical variables with values "_none_" if there were no locations in that category, "_some_" if the corresponding percentage is lower than 50%, and "_most_" in case that percentage is greater or equal to 50%.

To avoid the cold-start problem, we select only the active users who have checked-in to at least 3 different locations. Repeated check-ins from the same user in the same location and at the same time have been removed. 
As a result, Gowalla-NYC contains 497,180 check-ins, whereas Gowalla-SF contains 514,347 check-ins. 

Format:


### Yelp Review Data

