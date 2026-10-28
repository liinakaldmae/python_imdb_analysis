# When did The Simpsons stop being (that) good?

**The Simpsons IMDb dataset analysis using Python**

The Simpsons is the longest running animated series in history. It started in 1989 and is still going. It seems to be a common perception among the viewers that The Simpsons used to be very good, but at some point turned boring, uninspired or even bad. I want to explore this using IMDb data.

---

## Research question

Is it possible to tell from average ratings and number of votes when The Simpsons stopped being (that) good?

---

## Methodology

- Joined different IMDB datasets (title_akas, title_ratings, title_basics, title_episodes) and filtered to only include The Simpsons tv-show episodes.
- Explored scatterplots to see visually the relations between season, ratings and number of votes.
- Conducted k-means cluster analysis to identify three separate clusters of episodes.

---

## Results

After joining and cleaning the data I was left with 810 episodes of The Simpsons to investigate from 38 seasons.

Scatterplot of season number and average rating showed a noticeable negative correlation between the two variables - higher season number means lower ratings.

<p align="center">
  <img width="600" height="400" alt="plot1-simpsons" src="https://github.com/user-attachments/assets/b774c06d-61a2-4d97-8460-3ea4ee29b449" />
</p>

Scatterplot using the number of votes and average rating showed that the two are positively correlated. Adding season number as color to the scatterplot revealed that the episodes could potentially be grouped into more than two groups based on these variables.

<p align="center">
  <img width="600" height="400" alt="plot2-simpsons" src="https://github.com/user-attachments/assets/f64cf4b2-1fb4-4f20-b1f7-0643bf25700d" />
</p>

Running a k-means cluster analysis using number of votes, average rating and season number revealed that the episodes could be divided into three groups of similar sizes (298, 290 and 222 episodes). Cluster 2 seems to be the one with earliest seasons with highest ratings and highest number of votes. Cluster 1 is the one with the latest seasons, lowest ratings and lowest number of votes. Cluster 0 includes the seasons in between.

| cluster | numVotes | averageRating | seasonNumber | count |
|:-------:|---------:|--------------:|-------------:|------:|
| 0       | 1939.46  | 6.96          | 17.27        | 298   |
| 1       | 1112.34  | 6.46          | 30.43        | 290   |
| 2       | 4253.74  | 8.15          | 5.94         | 222   |

Plotting the clusters visually reveals that the seasons of The Simpsons could be divided in the following way:

1. The most appreciated episodes - seasons 1-10
2. The inbetween episodes - seasons 11-22
3. The least appreciated episodes - seasons 23-38.

<p align="center">
  <img width="600" height="400" alt="python_screenshot" src="https://github.com/user-attachments/assets/c877f1bf-3d9b-4ebd-b0a5-f14941891782" />
</p>

---

## Data source

The analysis uses IMDb's publicly available datasets: [datasets.imdbws.com](https://datasets.imdbws.com/).

IMDb dataset usage is subject to IMDb's [official terms and conditions](https://help.imdb.com/article/imdb/general-information/can-i-use-imdb-data-in-my-software/G5JTRESSHJBBHTGX). This repository focuses on Python analysis and summarized findings rather than redistributing the source datasets.
