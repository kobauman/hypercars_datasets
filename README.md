# HyperCARS Datasets for Context-Aware Recommender Systems Research

This repository provides datasets that were used in the following paper:
"_HyperCARS: Using Hyperbolic Embeddings for Generating Hierarchical Contextual Situations in Context-Aware Recommender Systems_"
published in the Information Systems Research journal [1]: https://doi.org/10.1287/isre.2022.0202


### Gowalla Check-in Data

**Gowalla** is a location-based social network platform that enables users to check-in to points of interest (POIs) they visit. Those POIs are grouped into seven categories: Community, Entertainment, Food, Nightlife, Outdoors, Shopping, and Travel. 
Most check-ins in Gowalla came from major cities in the US. The original data was taken from: https://snap.stanford.edu/data/loc-gowalla.html

In our study, we used POIs from New York City (NYC) and San Francisco (SF) because their locations are very dense in these areas. Therefore, many users visit multiple POIs within short periods of time, which constitutes rich contextual information. We calculated **twelve** contextual variables: "_time of the day_," "_day of the week_" (weekday/weekend), "_season_," "_number of check-ins_," "_distance traveled_," and seven variables revealing which of the main categories were visited within the previous three hours. 

In particular, for each check-in, we analyzed other check-ins made by the same user within the previous _three hours_ revealing his/her previous actions that serve as additional contextual information. Within those time windows, we calculated the number of check-ins and the categories of visited places. In particular, for each of the seven main categories, we calculated the percentage of locations from that category visited within the previous three hours. Based on this information, we created categorical variables with values "_none_" if there were no locations in that category, "_some_" if the corresponding percentage is lower than 50%, and "_most_" in case that percentage is greater or equal to 50%.

To avoid the cold-start problem, we select only the active users who have checked-in to at least 3 different locations. Repeated check-ins from the same user in the same location and at the same time have been removed. 
As a result, Gowalla-NYC contains 497,180 check-ins, whereas Gowalla-SF contains 514,347 check-ins. 

Format:


### Yelp Review Data

**Yelp** dataset (https://www.yelp.com/dataset) contains ratings and reviews of businesses, such as restaurants, hotels, shopping, etc., provided by Yelp users describing their experiences. 

For this study, we used 1,100,276 reviews for the restaurants in Pennsylvania state of the US. We selected this region and category of businesses because they contain the largest number of reviews in the latest version of the Yelp dataset.

To extract contextual variables from user reviews, we utilized Context Parser developed by [2]. This method produced twelve contextual variables including 
"_company of the visit_," "_occasion_," "_time of the day_," "_type of the meal_," "_day of the week_," "_came by car_," "_applied discount_," "_prior visits_," "_came by recommendation_," "_made reservation_," "_takeout_," and "_if the user is traveling_." 

The provided dataset includes 605,092 reviews that, according to Context Parser, contain values of at least one of the contextual variables. 


[1] Bauman, K., Tuzhilin, A., & Unger, M. (2024). HyperCARS: Using Hyperbolic Embeddings for Generating Hierarchical Contextual Situations in Context-Aware Recommender Systems. Information Systems Research. https://doi.org/10.1287/isre.2022.0202

[2] Bauman, K., & Tuzhilin, A. (2022). Know thy context: parsing contextual information from user reviews for recommendation purposes. Information Systems Research, 33(1), 179-202. https://doi.org/10.1287/isre.2021.1036


## Papers

If you are using these datasets in your research, please cite our papers: 

@article{bauman2024hypercars,
  title={HyperCARS: Using Hyperbolic Embeddings for Generating Hierarchical Contextual Situations in Context-Aware Recommender Systems},
  author={Bauman, Konstantin and Tuzhilin, Alexander and Unger, Moshe},
  journal={Information Systems Research},
  year={2024},
  publisher={INFORMS}
}


@article{bauman2022know,
  title={Know thy context: parsing contextual information from user reviews for recommendation purposes},
  author={Bauman, Konstantin and Tuzhilin, Alexander},
  journal={Information Systems Research},
  volume={33},
  number={1},
  pages={179--202},
  year={2022},
  publisher={INFORMS}
}


