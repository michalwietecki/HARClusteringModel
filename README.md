# Human Activity Recognition Clustering Models

This project was made for Introduction to ML classes at Faculty of Mathematics and Information Sciences at Warsaw University of Technology

## Authors
- [Jan Opala](https://github.com/opalajan)
- [Michał Wietecki](https://github.com/michalwietecki)

## Data used
The data comes from the dataset [Human Activity Recognition with Smartphones](https://www.kaggle.com/datasets/uciml/human-activity-recognition-with-smartphones).
It consists of various measurements of bodily movement during activity of subjects including walking, laying and sitting. Participants recorded spatial data using gyroscopes and accelerometres from their smartphones. Various statistics in three axes were recorded for body and gravity in both time domain and frequency domain.

## Overview
We decided to transform the data labels using two different mappings: VHS (vertical movement | horizontal movement | stationary) and WSL (walking | stationary | laying).

Visualization of VHS mapping:
![VHS visualized](https://github.com/JanOpala/HARClusteringModel/blob/main/vhs_3d.png)

Visualization of WSL mapping:
![WSL visualized](https://github.com/JanOpala/HARClusteringModel/blob/main/wsl_3d.png)

In our project we applied several clustering techniques (namely k-means, k-means Mini-Batch, Gaussian Mixture and Spectral clustering) and each obtained cluster was compared to existing labels of movement as well as to our mappings via ARI (Adjusted Rand Index).

Our final model for which the calculated ARI was the greatest was Gaussian Mixture model for 10 principal components of the dataset (obtained after we performed PCA) for WSL mapping. The ARI score 
was approximately 0.686, hence almost 70% of the values were clusterized appropriately to types of movement.

WSL labels after PCA (10 principal components):

![Labels after PCA](https://github.com/JanOpala/HARClusteringModel/blob/main/original_labels_pca.png)

GMM clusters:

![Gaussian Mixture Model](https://github.com/JanOpala/HARClusteringModel/blob/main/final_model_gmm10.png)

As it can be seen our model can recognize 'walking' movement at almost all times. The problem is to distinguish between 'sitting' and 'laying' movements for which accuracy is significantly lower. A potential expansion to our project would be to create an additional model to classify those two movements or to suggest a different, more sutiable mapping. 
