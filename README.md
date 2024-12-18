# Improving Brain MRI Image Classification via Deep Learning Models Using Best Practices
[![Made With Python](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=black)](https://www.python.org/) [![Tensorflow-Badge](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=TensorFlow&logoColor=white)](https://www.tensorflow.org/) [![Keras-Badge](https://img.shields.io/badge/Keras-D00000?style=for-the-badge&logo=Keras&logoColor=white)](https://keras.io/) [![Jupyter-Notebook-Badge](https://img.shields.io/badge/Jupyter-F37626.svg?&style=for-the-badge&logo=Jupyter&logoColor=white)](https://nbviewer.jupyter.org/github/strikersps/Brain-MRI-Image-Classification-Using-Deep-Learning/blob/main/Brain-Tumor-MRI-Image-Classification.ipynb) [![NVIDIA-Tesla-T4-Badge](https://img.shields.io/badge/NVIDIA-TeslaT4-76B900?style=for-the-badge&logo=nvidia&logoColor=white)](https://colab.research.google.com/github/d2l-ai/d2l-tvm-colab/blob/master/chapter_gpu_schedules/arch.ipynb) ![Repo-Size-Badge](https://img.shields.io/github/repo-size/strikersps/Brain-MRI-Image-Classification-Using-Deep-Learning?color=%23ff0000&style=for-the-badge) [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1Nm8JLCptOMqFHRtnXZeux_qoW9wtAgD_?usp=sharing)
------------------------------------------------------------------------------------------------------------------------------------------------------------------
[![GitHub-Contributors](https://img.shields.io/github/contributors/strikersps/Brain-MRI-Image-Classification-Using-Deep-Learning.svg)](https://github.com/strikersps/Brain-MRI-Image-Classification-Using-Deep-Learning/graphs/contributors) [![GitHub-Issues](https://img.shields.io/github/issues/strikersps/Brain-MRI-Image-Classification-Using-Deep-Learning?style=flat-square)](https://github.com/strikersps/Brain-MRI-Image-Classification-Using-Deep-Learning/issues) [![GitHub-Stars](https://img.shields.io/github/stars/strikersps/Brain-MRI-Image-Classification-Using-Deep-Learning?style=flat-square)](https://github.com/strikersps/Brain-MRI-Image-Classification-Using-Deep-Learning/stargazers) [![GitHub-Forks](https://img.shields.io/github/forks/strikersps/Brain-MRI-Image-Classification-Using-Deep-Learning?style=flat-square)](https://github.com/strikersps/Brain-MRI-Image-Classification-Using-Deep-Learning/network/members)  

![Brain-MRI-Image-Classification-Using-Deep-Learning-Cover-Photo](https://github.com/strikersps/Brain-MRI-Image-Classification-Using-Deep-Learning/blob/main/Project-Cover-Photo.jpg)  

## Introduction  
- The occurrence of brain tumor patients in India is steadily rising, more and more cases of brain tumors are reported each year in India across varied age groups. The International Association of Cancer Registries (IARC) reported that there are over 28,000 cases of brain tumours reported in India each year and more than 24,000 people reportedly die due to brain tumours i.e **85.7%** people die annually from the total reported cases. Brain tumors are a serious condition and in most cases fatal in later stages if not detected early on.

- Healthcare sector can benefit significantly from the field of Artificial Intelligence by developing systems which have the capability to detect these fatal diseases in the early stages because most diseases when detected early can be treated successfully before it's too late and same is the case with various different kinds of cancer.

## Goal of this Forked Repository from strikersps ##

1. **Continue the development of the model by implementing best practices for multi-class classification to increase the model's precision.**
   - Avoid utilizing measures designed for binary circumstances, such as accuracy and F1-score, when analyzing a multi-class model, as they may not provide comprehensive information.
   - Choose metrics such as macro- or micro-averaged recall and precision, which take into account all classes and eliminate class imbalance bias.
   - Use weighted versions of precision, recall, and F1-score for varying class sizes.
   - Analyze each class's performance using the confusion matrix to better understand model behavior. (Already done by strikersps)
   - Consider using Cohen's kappa for imbalanced datasets to verify agreement beyond chance.
   - Employ multiclass log-loss to examine prediction confidence in greater detail.
3. **Investigate the impact on the models by using:**
   - No augmentation
   - Different augmentation hyperparameters
   - Balancing the dataset with real MRI images of brain tumors (if possible)
4. **Explore the effect of classifying each plane of the MRI images: Axial, Sagittal, and Coronal**
   - Each plane individually
   - All three planes from the same patient
5. **Use CUDA and cuDNN to train the model with my GTX 1050 Ti and compare its performance to Google Colab's Intel Xeon CPU.**
6. **Develop a front-end interface for users to classify images online using TensorFlow.js and WebGPU.**
7. **Utilize OpenVINO to optimize the trained model for deployment on various hardware platforms, ensuring improved performance and reduced latency during inference.**


## About Dataset  
- Refer to [README.md](https://github.com/strikersps/Brain-MRI-Image-Classification-Using-Deep-Learning/blob/main/Brain-Tumor-Dataset/README.md) file in the [Brain Tumor Dataset directory](https://github.com/strikersps/Brain-MRI-Image-Classification-Using-Deep-Learning/tree/main/Brain-Tumor-Dataset) in this repository to get a clear idea about the dataset and the preprocessing steps.  
- The below image gives a glimpse about the different kinds of tumors with its localisation through a binary map after pre-processing the `.mat` file in which the image data was stored.  
![Brain-MRI-Images-With-Localisation-Masks](https://github.com/strikersps/Brain-MRI-Image-Classification-Using-Deep-Learning/blob/main/Brain-Tumor-MRI-With-Localisation-Masks.png)    

## Past Results: Questionable Accuracy!!!
- Developed 3 Deep Neural Network models i.e. Multi-Layer Perceptron, AlexNet-CNN, and Inception-V3 in order to classify the Brain MRI Images to 4 different independent classes.  
- Inception-V3 model used is a pre-trained on the ImageNet dataset which consist of 1K classes but for this project we have tuned the later part i.e. the Fully-Connected part of the model while retaining the weights of the CNN part to satisfy the needs of this work. 
- Below table provides the results obtained on the testing dataset: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1Nm8JLCptOMqFHRtnXZeux_qoW9wtAgD_#scrollTo=nobbz__oKJgb)
![Model-Results-On-Testing-Dataset](https://github.com/strikersps/Brain-MRI-Image-Classification-Using-Deep-Learning/blob/main/Model-Results-On-Testing-Dataset.png)
- **The pre-trained Inception-V3 model has performed significantly well with an accuracy of `82.57%` as compare to AlexNet-CNN and Multi-Layer Perceptron deep neural network model.**  

## Results: (On going)  
