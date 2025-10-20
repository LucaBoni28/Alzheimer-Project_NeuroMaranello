# Alzheimer’s Disease Detection with Deep Learning

## Group name: NeuroMaranello
Members of group:
- Luca Boninsegna YPOUBM
- Samuele Rosato YKQGE5
- Belarmino Gorlach-Lira N9Z4S5

### Description of the problem
Alzheimer’s disease (AD) is a progressive neurodegenerative disorder that impacts memory and cognitive abilities. Early detection plays a crucial role in improving patient care and enabling timely medical intervention. This project will explore the use of deep learning models for classifying Alzheimer’s disease from MRI images.

The provided GitHub repository (see below) offers a simplified framework for building and training deep learning models to detect Alzheimer’s, including data preprocessing, CNN-based model design, and performance evaluation. Students will work on extending, experimenting with, and improving this baseline.

### Tasks
Students will study Alzheimer’s detection using deep learning and implement a CNN-based classifier using the provided dataset and code framework. The focus will be on training the model to distinguish between different stages of Alzheimer’s (e.g., Mild Demented, Moderate Demented, Severe Demented, and Non-Demented). Students should also evaluate model performance using accuracy, precision, recall, F1-score, and confusion matrix.

#### Basic Task:
Use the baseline CNN provided in the GitHub repo to train a classifier for Alzheimer’s detection from MRI scans. Evaluate the model and present performance metrics.

#### Advanced Task:
Experiment with improvements such as transfer learning (e.g., VGG16, ResNet, EfficientNet), data augmentation techniques, or fine-tuning hyperparameters to boost performance. Students can also test the model’s robustness across different datasets or apply Grad-CAM for interpretability.

#### Dataset:
https://www.kaggle.com/datasets/marcopinamonti/alzheimer-mri-4-classes-dataset
https://www.kaggle.com/datasets/preetpalsingh25/alzheimers-dataset-4-class-of-images

### Get started
The code has been developing to be run directly from Google Colaboratory, thus it's sufficient to open the file in Colab and run the single cells either one by one or all in one.

##
### Project Milestones
The project's current version contains the Project Milestone 1: Data acquisition and preparation. 

## Milestone 1: Data acquisition and preparation
In this phase of the project, we downloaded the dataset and prepare the data for training using strategies to increase the effectiveness of the training. Our data set has is very unbalanced, with the Mild Demented class having a significantly smaller amount of data, as can be seen in the class distribution below:

28 subjects for the Mild Dementia Class
2 subjects for the Moderate Dementia Class
100 subjects for the Non Dementia Class
70 subjects for the Very Mild Dementia Class

Due to this, we used the Stratified K-Fold technique plus a weighted data loader to try to make the most of the data available to us.
