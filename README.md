![cover_image](https://github.com/astroboy07/Glitch-Classification-Adanced-LIGO/blob/master/Extras/GW_LIGO.png)

# Glitch-Classification-Adanced-LIGO

## Repo's Structure

This repository has two main folder. The Extras as name suggests has all the extra files that are non-essential and Notebook contains the python notebook file which has CNN model buitl using TensorFlow used for "glitch" classification of Advanced LIGO.

## Python notebook 

The python notebook file was originally ran on Kaggle's website with GPU accelerator (`Tesla P100-PCIE-16GB`) and the `tensorflow 2.4.1` version is used. Now we will explain the notebook in detail.

> ### Dataset

The dataset is obtained from Kaggle under the name [Gravity Spy (Gravitational waves)](https://www.kaggle.com/datasets/tentotheminus9/gravity-spy-gravitational-waves). It has 22 classes of "glitches" labeled and organized into training, validation and, test directories. The training, validation and, test datasets has 22348, 4800, and 4720 files respectively. The files in these directories have the images and corresponding labels in them.

> ### Model

We used Transfer Learning to train our datasets. We chose `Resnet50V2` ([ResNet paper](https://arxiv.org/abs/1603.05027)) from `tensorflow.keras.appications` as the base model which has already been trained on ImageNet datasets. We trained our "glitch" datasets on this base model and acheived training accuracy of **95%**.

> ### Model's evaluation

Our model performs incredibly good on the "unseen" test datasets too. The test accuracy is almost **92%**. We evaluate our model with various metrics. 

* We create the confusion matrix which gives us an overall idea of how model performs on all the classes. The digonal elements, representing the correct predictions, have darker shades which consolidates our model's accuracy.

* We then dive further and evaluate model's performance class-wise. We show the table with precision, recall, and f1 scores for all the classes.

> ### Visualization of model's performance

To visualize model's class-wise performance:

* we plot the f1 scores for all classes as a horizontal bar chart which goes from class with highest to lowest f1 score. We also put a red vertical line which represents the arbitrary threshold of 85% and only above this threshold we can truly say that the predicted label matches with the true label.

* we randomly choose 3 images from the test dataset and show model's prediction using color codes, red if model predicts wrong label and green if model predicts right label and also the prediction probability. On the same figure we also show a bar chart of model's top 3 prediction.






