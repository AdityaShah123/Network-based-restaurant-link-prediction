# Network-based Restaurant Link Prediction

## Project Overview

This project focuses on **restaurant check-in prediction** within the **Foursquare network in New York City**. The goal is to predict future connections (check-ins) between users and restaurants by using various **link prediction techniques**. Applications of this research include **customized restaurant suggestions** and **strategic commercial alliances**.

## Introduction

Link prediction is a fundamental problem in network analysis with applications in **social networks** and **recommendation systems**. In this project, we attempt to predict potential check-ins using **network scoring methods** that help anticipate future connections between users and venues.

## Dataset Details

The dataset used is the **FourSquare - NYC Restaurant Check-Ins Dataset**, which contains check-in, tip, and tag data of restaurant venues in NYC. The dataset spans from **October 24, 2011, to February 20, 2012** and includes:
- **3,112 users**
- **3,298 venues**
- **27,149 check-ins**
- **10,377 tips**

### Files in the Dataset:
1. **NY.Restaurants.checkins.csv** - Two columns: user ID and venue ID for each check-in.
2. **NY.Restaurants.tips.csv** - Three columns: user ID, venue ID, and tip/comment text.
3. **NY.Restaurants.tags.csv** - Two columns: venue ID and a set of tags associated with the venue.

## Problem Statement

The goal of this project is to predict future restaurant check-ins by using link prediction techniques. Users and restaurants are treated as vertices in a **bipartite network**, and the objective is to identify the **most effective scoring method** for predicting user-venue connections with a balance between **precision and recall**.

## Data Visualization

We used **degree distributions** and a **spring arrangement** to visualize the user-venue interactions within the social network. By analyzing these patterns, we could identify hubs (popular users and venues) and better understand the structure of user behaviors.

## Scoring Methods

Several scoring methods were used to predict links between users and venues:

1. **Distance Score**: Predicts connections based on the shortest distance between nodes in the network.
2. **Common Neighbors**:
   - **User-based**: Predicts connections if users share common venues.
   - **Venue-based**: Predicts connections if venues attract the same users.
3. **Tip-based Prediction**: Uses **cosine similarity** and **TF-IDF** to predict connections based on user-provided tips.
4. **Preferential Attachment**: Assumes that venues with more connections have a higher chance of receiving new check-ins.
5. **Community Detection Score**: Predicts links based on community structures within the network.
6. **k-Nearest Neighbors (k-NN)**: Evaluates node similarity and predicts links based on the closest neighbors.

## Results

The following table summarizes the **precision** and **recall** for each scoring method:

| Scoring Method                   | Precision (%) | Recall (%) |
| --------------------------------- | ------------- | ---------- |
| Negative Shortest Distance Score  | 0.282         | 17.273     |
| User Common Neighbors Score       | 34.029        | 8.854      |
| Venue Common Neighbors Score      | 54.741        | 13.797     |
| Tip-based Prediction              | 0.029         | 11.298     |
| Preferential Attachment Prediction| 0.270         | 4.780      |
| Community Detection Score         | 2.849         | 15.970     |
| k-Nearest Neighbors (k-NN)        | 2.87          | 83.72      |

The **k-NN** method achieved the **highest recall** (83.72%) but with a relatively low precision (2.87%), indicating its ability to capture a large number of true positives but with many false positives. **Venue Common Neighbors Score** also performed well, with a precision of 54.74%.

## Conclusion

Each scoring method offers unique advantages and trade-offs between precision and recall. The **k-NN** method excels at identifying possible connections, while **common neighbors** methods show the importance of shared user-venue connections. Future research could explore hybrid models combining these techniques or incorporating dynamic features for more accurate predictions.

## Technologies Used

- **Python**: For data processing, analysis, and visualizations.
- **NetworkX**: For network graph representations.
- **Scikit-learn**: For implementing machine learning algorithms like k-NN.
- **Pandas & Numpy**: For data handling and manipulation.

## Future Enhancements

- **Hybrid models** combining multiple scoring methods to improve accuracy.
- Incorporating **dynamic features** such as temporal changes in user preferences.
- Exploring **deep learning architectures** for complex pattern recognition in social networks.

## References

1. Yang, D., Zhang, D., Yu, Z., & Yu, Z. (2013). Fine-grained preference-aware location search leveraging crowdsourced digital footprints from LBSNs.
2. Yang, D., Zhang, D., Yu, Z., & Wang, Z. (2013). A sentiment-enhanced personalized location recommendation system.
