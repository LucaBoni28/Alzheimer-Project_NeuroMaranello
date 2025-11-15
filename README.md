# Alzheimer’s Disease Detection with Deep Learning

## Group name: NeuroMaranello
Group members:
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
The needed packages will be installed in the Colab environment with the first command (cell).

##
### Project Milestones
The project's current version contains:  

* ## Milestone 1: Data acquisition and preparation
In this phase of the project, we downloaded the dataset and prepared the data for training using strategies to increase the effectiveness of the training. Our data set is very unbalanced, with the Moderate Dementia Class having a significantly smaller amount of data, as can be seen in the class distribution below:

- 28 subjects for the **Mild Dementia** class
- 2 subjects for the **Moderate Dementia** class
- 100 subjects for the **Non Dementia** class
- 70 subjects for the **Very Mild Dementia** class

Due to this unequal distribution, we used three different techniques to mitigate the negative effects on the training: the Stratified K-Fold, weighted classes and a weighted sampler for the dataloader.

* ## Milestone 2: Baseline evaluation, baseline model
For an efficient data loading we defined the class AlzheimerDataModule using the Lightning Data Module. We inserted the train_dataloader and val_dataloader methods and we implemented into the setup method the three strategies mentioned earlier. In this way by calling the class AlzheimerDataModule, the original dataset is splitted in training and validation sets applying the Stratified K-Fold, the weighted class and weighted sampler.

For the model architecture definition we declared a class using the Lightning Module, which allows to describe through predefined methods the model's architecture, the training_step, the validation_step and the performance metrics. We chose a simple Convolutioanl Neural Network(CNN) with a Fully Connected(FC) Classifier to predict the class confidence values.

Finally, the last implementation is related to the training phase and the last evaluation of the best model. Thanks to the package Lightning Module, the requested code is very clean, because it's sufficient to define the setup of the training by using the trainer method and then start the run calling the mode "fit". 
Since we decided to use the K-Folds technique we put all the setup and training code in a for loop to repeat the training for each fold and also at each iteration the model with the best validation accuracy is saved as the absolute best model for the final evaluation.

The final evaluation is performed by loading the best model previously saved and then call the trainer in "validate" mode.
