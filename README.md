# UC Berkeley Club Recommendation System

Combines collaborative filtering and word2vec club description similarity. Originally written for sproul.club club recommendation system.

The goal of this notebook is to return 5 relevant, personalized club recommendations for each user. 

This recommendation system uses the Turi Create Item Similarity Algorithm to perform collaborative filtering on a simulated list of userID's (simulated favorites, interests). The simulated data points can be replaced with real user data once collected (the datapoints we need are **UserID (integer), Favorites (a list of club name strings),and Interests (a list of tag numbers**). 

Once recommendations from item similarity are returned, the goal is then to ensure that recommendations are attuned to user interests (and not just random due to item similarity)
- The script filters out club recommendations that do not have tags that match their interest tags. This will get rid of a decent percentage of the item similarity recommendations (at least in ths simulated data, since it is completely random)
- Then, all missing recommendations (since we want 5 per user) will be filled with recommendations using our generic recommender based on favorited clubs
- If the user has no favorited clubs then missing recommendations will be filled with clubs from users' specific interests
- If a user has no interests, then the recommender will recommend all item similarity recommendations.
