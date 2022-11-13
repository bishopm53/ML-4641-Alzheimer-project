---
layout: page
title: Alzheimer's MRI Scans Classification
subtitle: Team 23 Project Proposal
---

### Introduction

Our project will study MRI scans of human brains to analyze the signs and progression of Alzheimer’s disease. Alzheimer’s Disease is an extremely common disease that affects 5.8 million adults over the age of 65 (Alzheimer's disease 2022). While there is no cure, early treatment is better for managing and reducing symptoms, and MRIs are a tool that can be used to diagnose and evaluate the stage of the disease.

The application of machine learning to the field of neurological and cognitive health is quickly growing. With the possibility of catching diseases like Alzheimer’s years earlier, treatment and prevention could begin much sooner to reduce the progression and clinical onset of the underlying disease. One piece of research we found discussed the prediction of Alzheimer’s progression using machine learning through the analysis of a current trajectory from two MRI scans separated by a known time interval (Mofrad et al., 2021).

Our data set is a collection of 6,400 MRI scans augmented to over 40,000 training and validation images with classifications of the current state of Alzheimer’s disease in each image. The images are labeled to belong to one of four of the following classes: non-demented, mild demented, moderate demented, and very demented. 

Here is a link to our [data set](https://www.kaggle.com/datasets/uraninjo/augmented-alzheimer-mri-dataset)

### Problem Definition

Our project aims to potentially identify regional, morphological abnormalities in individuals with Alzheimer's Disease. These abnormalities display themselves as atrophy in various brain regions, including the hippocampus and entorhinal cortex (Chandra et al., 2018). We also intend to increase diagnostic accuracy, which can either be integrated with patient history or serve as a proactive measure for individuals not yet showing symptoms of the disease. In turn, patient support can increase, and measures to improve patient prognosis may be implemented. Future clinical trials may also be supported to administer potential treatments, mitigate Alzheimer's Disease progression, and enhance patient quality of life.

![Alt text](https://github.com/bishopm53/ML-4641-Alzheimer-project/tree/master/assets/img/test-image.jpg?raw=true)

### Data Collection

The categorized dataset of over 40,000 augmented MRIs consists of equally sized, 3-channel image files that are generally uniform. We did not modify the dataset too much aside from conversion to grayscale due to the general uniformity and believe the versatility of a model trained on this dataset would contribute to the usability of our project in a real-world situation. Some similar works we found used methods such as skull boundary removal to improve accuracy. Modifications like this are under consideration as we work to improve the accuracy of our model.

### Methods

In order to analyze the signs and progression of Alzheimer’s disease, we will use a convolutional neural network (CNN). In general, deep learning models outperform statistical machine learning methods in image processing tasks, and CNNs are particularly distinguished among other types of neural networks. Moreover, image processing with CNNs has already proven an effective and efficient tool in disease detection, so there is an abundance of literature to draw upon (Khagi et al., 2019).
 
We discovered that it is easy to create a model that is too complex or takes too large of an input and, therefore, is extremely expensive in computation. With only eight layers in our simple CNN, we still had over 121,000 trainable parameters. To mitigate this issue, we implemented principal component analysis (PCA) on our input data.


<img src="assets/img/test-image.jpg" alt = "Alt text" title = "optional">

### Potential Results and Discussion

During our initial dive into creating a convolution neural network for this project, we were left with a choice of how we wanted to implement it. We researched the easiest and most user-friendly way for us, as beginners, to create our own model and found two main options, tensorflow and pytorch. Our team eventually settled on using tensorflow despite some group members having experience with pytorch because of the plethora of documentation on image CNNs in tensorflow.
 
Once this decision was made, we looked towards the data set to see what we needed to do to preprocess the data for our model. We noticed that different MRI images had different hues with some slightly blue, some slightly green, and some slightly pink. So, our first step was to turn all of our images into grayscale to make the images more consistent and only have to work with a 1-channel 256 x 256 matrix for each image, as opposed to a 256 x 256 x 3 input. Once we did this, we ran our model and got an initial accuracy of around 89.71% through 10 epochs of 450 steps. While this was quite good, we noticed that during validation, our accuracy was only 74.85%, meaning that there was a significant amount of overfitting happening. From epochs 10 to 15, training accuracy increased to 93.8% while validation decreased to 74.28%. This took a total of 2.52 hours.
	
After seeing the overfitting problem as well as the complexity of our model by passing the images into the CNN without doing any dimensionality reduction, we applied PCA to a portion of our data and reran the model. This was able to decrease the complexity and running time of the model significantly. To do this we had to flatten the array of each image from 256 x 256 to 1 x 65,536. We passed the flatten images into the PCA model and reduced the number of dimensions to 1024. We reformatted the data into 32 x 32 arrays and trained a new CNN model accounting for the new dimensions. After 10 epochs of 450 steps each, we had 79.41% training accuracy and 77.28% validation accuracy. Through 30 epochs, these values increased to 90.47% and 82.34%, respectively. The increase in accuracy was not the only advantage of PCA; running the dimensionality reduction took 7.9 minutes while training 30 epochs took 7.11 minutes.
 
We hope to run PCA on the entire dataset once we find a solution to memory issues that we encountered with our current implementation. The benefits of PCA are clear from the decrease in training time from 2.52 hours to 15 minutes. Not only are we finding new ways to improve the iterability of the model, we have created a decently accurate model to determine the presence of Alzheimer’s disease in MRIs of the human brain.



### Gantt Chart and Contribution Table

Here is a link to our [Gantt Chart](https://gtvault-my.sharepoint.com/:x:/g/personal/scanastra3_gatech_edu/EV418BSlG0dIvm-2YcQRGKwB812RjocrHM2qpRjKDK-q9A?e=HlPncl)

Here is a link to our [Contribution Table](https://gtvault-my.sharepoint.com/:x:/g/personal/scanastra3_gatech_edu/EfC08hdEY7VAvQ7QMMIQ2TABL5AW9ueuiT-u4cN8wCn8bg?e=FmujgV)

### References

* Chandra, A., Dervenoulas, G., & Politis, M. (2018). Magnetic Resonance Imaging in alzheimer’s disease and mild cognitive impairment. Journal of Neurology, 266(6), 1293–1302. https://doi.org/10.1007/s00415-018-9016-3
* Khagi, B., Kwon, G. R., & Lama, R. (2019). Comparative analysis of alzheimer's disease classification by CDR level using CNN, Feature Selection, and machine‐learning techniques. International Journal of Imaging Systems and Technology, 29(3), 297–310. https://doi.org/10.1002/ima.22316
* Mayo Foundation for Medical Education and Research. (2022, February 19). Alzheimer's disease. Mayo Clinic. Retrieved October 6, 2022, from https://www.mayoclinic.org/diseases-conditions/alzheimers-disease/symptoms-causes/syc-20350447?utm_source=Google&utm_medium=abstract&utm_content=Alzheimers-disease&utm_campaign=Knowledge-panel
* Mofrad, S. A., Lundervold, A. J., Vik, A., & Lundervold, A. S. (2021). Cognitive and MRI trajectories for prediction of alzheimer’s disease. Scientific Reports, 11(1). https://doi.org/10.1038/s41598-020-78095-

