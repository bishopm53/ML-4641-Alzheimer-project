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



### Methods

In order to analyze the signs and progression of Alzheimer’s disease, we will use convolutional neural networks (CNNS). In general, deep learning models outperform statistical machine learning methods in image processing tasks, and CNNs are particularly distinguished among other types of neural networks. Moreover, image processing with CNNs has already proven an effective and efficient tool in disease detection, so there is an abundance of literature to draw upon (Khagi et al., 2019). 


<img src="assets/img/test-image.jpg" alt = "Alt text" title = "optional">

### Potential Results and Discussion

The primary results of our model will be the classification of the images into one of the four classification labels. The discussion will be centered around an analysis of the performance, in which we will provide a confusion matrix and metrics to evaluate our model. One of the metrics we will use is accuracy which is suitable since our data is relatively balanced across the classes. We will also look at other metrics such as precision, recall, F1 scores, and others as needed. Additionally, we will talk about the impact the fine-tuning of hyperparameters had on our CNN model and evaluate if we were able to achieve improved performance metrics.

### Gantt Chart and Contribution Table

Here is a link to our [Gantt Chart](https://gtvault-my.sharepoint.com/:x:/g/personal/scanastra3_gatech_edu/EV418BSlG0dIvm-2YcQRGKwB812RjocrHM2qpRjKDK-q9A?e=HlPncl)

Here is a link to our [Contribution Table](https://gtvault-my.sharepoint.com/:x:/g/personal/scanastra3_gatech_edu/EfC08hdEY7VAvQ7QMMIQ2TABL5AW9ueuiT-u4cN8wCn8bg?e=FmujgV)

### References

* Chandra, A., Dervenoulas, G., & Politis, M. (2018). Magnetic Resonance Imaging in alzheimer’s disease and mild cognitive impairment. Journal of Neurology, 266(6), 1293–1302. https://doi.org/10.1007/s00415-018-9016-3
* Khagi, B., Kwon, G. R., & Lama, R. (2019). Comparative analysis of alzheimer's disease classification by CDR level using CNN, Feature Selection, and machine‐learning techniques. International Journal of Imaging Systems and Technology, 29(3), 297–310. https://doi.org/10.1002/ima.22316
* Mayo Foundation for Medical Education and Research. (2022, February 19). Alzheimer's disease. Mayo Clinic. Retrieved October 6, 2022, from https://www.mayoclinic.org/diseases-conditions/alzheimers-disease/symptoms-causes/syc-20350447?utm_source=Google&utm_medium=abstract&utm_content=Alzheimers-disease&utm_campaign=Knowledge-panel
* Mofrad, S. A., Lundervold, A. J., Vik, A., & Lundervold, A. S. (2021). Cognitive and MRI trajectories for prediction of alzheimer’s disease. Scientific Reports, 11(1). https://doi.org/10.1038/s41598-020-78095-

