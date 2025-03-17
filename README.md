# STT_Lab4

CS203: Software Tools & Techniques for AI

Lab Assignment 04: Active Learning and Cost-Effective Labeling

Lead TA: Eshwar Dhande (eshwar.dhande@iitgn.ac.in)

Submission Guidelines:

Submit your Google Collab Notebook with clear documentation.
Deadline: 02/02/2025 11:59:59 PM (IST) 
No late submissions will be accepted; No deadline extensions will be given.
Objective: This lab aims to explore active learning techniques to reduce annotation costs by selectively choosing the most informative data points for labelling. Students will implement and compare different active learning strategies: uncertainty sampling, query-by-committee, and random sampling.

Task 1: Setup the Dataset:

-Load the MNIST dataset using the Hugging Face datasets library. \n
-Convert the image data into Numpy arrays and normalize pixel values to the range [0,1].
-Flatten each image into a vector of 784 features.
-Split the dataset into training and testing sets.
-Randomly select an initially labeled dataset of 200 samples from training samples.
-Generate an "Unlabeled Pool," the Initial Dataset excluding 200 samples.


Task 2: Implement Random Sampling for Active Learning:

-Train a Random Forest Classifier (you can use “from sklearn.ensemble import RandomForestClassifier”)  on the initial dataset of 200 samples.
-Implement an active learning loop for 20 iterations:
-Randomly select a sample from the unlabeled pool.
-Get the selected sample and its true label.
-Add the sample and label to the labeled dataset.
-Remove the selected sample and label from the pool.
-Retrain the model on the updated dataset.
-Check the model's accuracy on the test set.
-Print accuracy after every iteration.

Task 3: Implement Uncertainty Sampling for Active Learning.:

-Train a Random Forest Classifier (you can use “from sklearn.ensemble import RandomForestClassifier”)  on the initial dataset of 200 samples.
-Implement an active learning loop for 20 iterations:
-Compute uncertainty (Label Entropy) for each sample in the unlabeled pool using entropy.
-Select the sample with the highest uncertainty and query its true label.
-Add the queried sample to the labelled dataset and remove it from the unlabelled pool.
-Retrain the model and check the model's accuracy on the test set.
-Print accuracy after every iteration.

Task 4: Implement Query-by-Committee for Active Learning;

-Initialize a committee of 5 Random Forest models, each trained on the initial dataset.
-In the active learning loop for 20 iterations:
-For each unlabeled sample, compute predictions from all committee members.
-Measure disagreement by calculating Vote Entropy.
-Select the sample with the highest disagreement and query its true label.
-Update the labelled dataset and retrain all models.
-Check the model's accuracy on the test set.
-Print accuracy after every iteration
-Note: For calculating Label Entropy and Vote Entropy, do not use functions from the library; write code from scratch.

Task 5 : Evaluation & Report:

-Compare the final model accuracy across all three strategies.
-Plots the graph of accuracies for all three methods for 20 iterations.
-Analyze which method leads to the most cost-effective improvement in accuracy.
-Discuss findings and limitations in a brief report.

Grading Breakdown:

Implementation (60%): Correct implementation of all three active learning strategies.
Analysis & Report (20%): Analysis quality, findings discussion, and report clarity.
Code Documentation & Clarity (20%): Proper comments, structure, and code readability.

