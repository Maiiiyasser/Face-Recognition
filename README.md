# Face-Recognition
Face recognition classification on the ORL dataset using PCA and LDA.
Assignment #1 Face Recognition (Total 150 Points)
Problem Statement
We intend to perform face recognition. Face recognition means that for a given
image you can tell the subject id. Our database of subject is very simple. It has 40
subjects. Below we will show the needed steps to achieve the goal of the
assignment.
1. Download the Dataset and Understand the Format (10 Points)
a. ORL dataset is available at the following link.
https://www.kaggle.com/kasikrit/att-database-of-faces/downloads/attdatabase-of-faces.zip/1
b. The dataset has 10 images per 40 subjects. Every image is a grayscale
image of size 92x112.
2. Generate the Data Matrix and the Label vector (10 Points)
a. Convert every image into a vector of 10304 values corresponding to the
image size.
b. Stack the 400 vectors into a single Data Matrix D and generate the label
vector y.
The labels are integers from 1:40 corresponding to the subject id.
3. Split the Dataset into Training and Test sets (10 Points)
a. From the Data Matrix D400x10304 keep the odd rows for training and
the even rows for testing. This will give you 5 instances per person for
training and 5 instances per person for testing.
b. Split the labels vector accordingly.
4. Classification using PCA (30 points)
a. Use the pseudo code below for computing the projection matrix U.
Define the alpha = {0.8,0.85,0.9,0.95}
b. Project the training set, and test sets separately using the same
projection matrix.
Prof. Dr. Marwan Torki Eng. Abdelrahman Wael
 Eng. Ismail El-Yamany
c. Use a simple classifier (first Nearest Neighbor to determine the class
labels).
d. Report Accuracy for every value of alpha separately.
e. Can you find a relation between alpha and classification accuracy?
5. Classification Using LDA (30 Points)
a. Use the pseudo code below for LDA. We will modify few lines in
pseudocode to handle multiclass LDA.
i. Calculate the mean vector for every class Mu1, Mu2, ..., Mu40.
ii. Replace B matrix by Sb.
𝑆𝑏 = ∑𝑛𝑘
(𝜇𝑘 − 𝜇)(𝜇𝑘 − 𝜇)
𝑇
𝑚
𝑘=1
Here, m is the number of classes, 𝜇 is the overall sample mean, and 𝑛𝑘 is the
number of samples in the k-th class.
iii. S matrix remains the same, but it sums S1, S2, S3, ...S40.
iv. Use 39 dominant eigenvectors instead of just one. You will
have a projection matrix U39x10304.
b. Project the training set, and test sets separately using the same
projection matrix U. You will have 39 dimensions in the new space.
c. Use a simple classifier (first Nearest Neighbor to determine the class
labels).
d. Report Accuracy for the Multiclass LDA on the face recognition
dataset.
e. Compare the results to PCA results.
