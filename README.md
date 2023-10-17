# person-reidentification
The target of this project is to make a model that detects a person over different camera frames.

Firstly, I took the CUK03 dataset from Kaggle (Chinese university of hong kong dataset). It has pairs of images taken of same person from different camera angles and also pairs of images of differet people, thus it is a good dataset for our target task.

Then I loaded the dataset and printed certain entries to analyze the imput and found that all the images are of shape (3, 160, 60), which makes the task a bit less cumbersome.

For validation tasks, Siamese networks are one of the best neural networks as they take in the images and compare the features using euclidian distance. Relational networks are also a good approach, but for simplicity, lets use siamese networks. 

The model takes two images, passes them through convolution layers (The FEATURE EXTRACTOR) separately and then calculates "cross input neighbourhood differences" as mentioned in the research paper "An Improved Deep Learning Architecture for Person Re-Identification". Then the resulting matrix is passes through a series of convolution layers and then flattened and after a couple of linear layers, the output is of 2 neurons. one to indicate a match, one to indicate "not a match"


