# Final Project – Option 3: Seeds Clustering

## What is this project about?

In this project, I wanted to see how much structure I could find in the Seeds data without using the real wheat variety labels.

The data contains 210 wheat kernels. Each kernel has seven measurements, such as area, perimeter, compactness, length and width. I kept the real variety labels hidden while doing the clustering and only used them at the end to check the result.

## What I did

First, I scaled the seven features because K-Means uses distances and I did not want features with larger values to have more influence.

Then I used PCA to reduce the data to two dimensions so I could make a plot and get a first idea of the structure.

After that, I tested K-Means with values of k from 2 to 7. I used the elbow plot and silhouette score to help choose the number of clusters. The silhouette score was highest for k = 2, but the elbow plot showed that k = 3 was also a reasonable choice, so I used three clusters for the final model.

I only looked at the real wheat varieties after the clustering was complete.

## Results

The first two PCA components explain about **89.0%** of the variance, so the PCA plot gives a useful view of the data.

With **k = 3**, the purity score was about **0.919**. This means the clusters matched the real wheat varieties quite well, although they were not perfect.

Variety 2 (Rosa) was the clearest group. Most of the confusion was between varieties 1 (Kama) and 3 (Canadian).

The notebook includes the PCA plots, elbow plot, silhouette results, cluster sizes, cross-tabulation, purity score and cluster profiles.

## What I learned

I found the PCA visualisation and the basic K-Means steps fairly easy to understand after scaling the data. The hardest part was choosing the number of clusters because the elbow method and silhouette score did not give exactly the same answer.

I think it was useful to keep the labels hidden until the end because this made the clustering a fair test. If I had more time, I would compare K-Means with another clustering method and check how stable the clusters are with different random seeds.

## Limitation

I would not treat the clusters as definite wheat varieties. K-Means will always create groups, and the purity score is good but not perfect. The results are useful evidence that there is real structure in the measurements, but they should not be treated as certain labels.
