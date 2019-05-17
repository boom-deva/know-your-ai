# Developing a Framework to Address Bias, Racism, and Sexism in Facial Recognition 
## Training a Convolutional Neural Network (CNN) to Recognize Multicultural Facial Expressions
![image of rasas](https://github.com/jasminevasandani/know-your-ai/blob/master/notebook_images/navarasa_banner.png?raw=true)


## Abstract
Racism, sexism, and bias exists in AI because of what type of data is collected, who creates the algorithms, and the frameworks used to design those algorithms. Any attempt to remove bias from AI that does not take into consideration _at least_ these three stipulations is a farce. As a person who loves a good challenge and is deeply concerned about this topic, I developed a project-based intervention that addresses bias, racism, and sexism in AI, focusing particularly on facial expression recognition. **Here’s what I did: I trained a convolutional neural network (CNN) on images of people of color, gender non-conforming people, young and old people, and people with prominent facial accessories and predicted their facial expressions according to the nine emotions defined by the South Asian emotion spectrum called the “navarasa” (“nava” = nine, “rasa” = emotion).** If this sounds complicated, it’s supposed to be—because eliminating bias from AI requires careful thought and meticulous strategy in order to be truly effective. To complete this project, I created a small, handpicked image dataset, pre-processed the images for modeling, trained my dataset on CNN models, and assessed my predictions. The model with the best fit augmented my image data, and the accuracy score was 69% compared to a baseline score of 12%. Considering the size and quality of my dataset, I am pleased with my results and can use this model as a starting point to train an even larger and better quality dataset. 
![navarasa_faces.png](https://github.com/jasminevasandani/know-your-ai/blob/master/notebook_images/navarasa_faces.png?raw=true)
[Image source for "srngara" face](https://www.flickr.com/photos/tjook/4746803656/in/photolist-9XdG49-vcFh7S-62Lxcp-pZWg1t-ain93R-4pF4Tj-qVmc3t-nAdLsE-6AvFTU-eEBsvZ-oeP8XZ-8VQ7Mk-nSHdPx-Ji7CH-nQkN6k-8esBmm-bnJ5Xz-N3Wfum-WKbD95-q1eDgh-e7wfGD-iGsRxx-aHcyre-rBfkRk-az6phv-avEQh5-aipWsh-dNyWsX-XtizkB-jbhRuk-9rgG3b-nZ9ti4-YoYm6E-31Dnp-p4jisb-qouL-9JdMW-4pSazz-8NpcSZ-pHLuGS-8moqdb-dQGBn4-4BZ2ib-p4jivC-21X7AXj-9goFCZ-95nxEX-bo1c8t-bCumKj-q1eRpW)

## Methodology 
| Data Science Workflow       | Description                                                                                                                                                                         |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Problem Statement**            | Bias, racism, and sexism are built into AI. How might I address this problem? Task: Build a CNN model using an inclusive dataset to recognize non-Western emotions--the “navarasa” (nine emotions) originating in South Asian art aesthetics.                          |
| **Data Acquisition**   | Being mindful of image rights, I only selected public, opensource, and creative commons images. It was difficult to build a large dataset while maintaining balanced classes of _nine_ distinct emotions. In total I acquired 1,032 images. See image sources for more details. The distinctness of each emotion set of images could be improved with enough resources and time. |
| **Data Processing** | Find face in image, crop face to 75 x 110 pixels, convert to grayscale, and convert to numpy array.                                                                                                 |
| **Modeling**                    | Relying on Francois Chollet’s methodologies for deep learning in computer vision applications, I implemented three CNN models: one with the images as they are, the second implementing `ImageDataGenerator`, and the third using a pre-trained model (`VGG16`). |
| **Assessing Predictions**                    | I visualized the probability of predicting certain emotions for each image, a confusion matrix, and predicted versus actual results. |

## Modeling
I implemented three models that could predict facial expression. The most effective was model #2. 
**Model #1: CNN on original dataset of 1,032 images**
  - Test loss: 1.42
  - Test accuracy: 63.7% 
  - Train/Test assessment: overfit 
  - Notes: Given the small dataset and quality of images, it’s no surprise that the model is overfit.
![model_1.png](https://github.com/jasminevasandani/know-your-ai/blob/master/notebook_images/model_1.png?raw=true)

**Model #2: CNN on augmented data**
  - Test loss: 0.89
  - Test accuracy: 69.5% 
  - Train/Test assessment: fit
  - Notes: Image augmentation drastically corrected my model to make it more fit.
![model_2.png](https://github.com/jasminevasandani/know-your-ai/blob/master/notebook_images/model_2.png?raw=true)

**Model #3: CNN on augmented data using `VGG16`**
  - Test loss: 1.41
  - Test accuracy: 56.76% 
  - Train/Test assessment: relatively fit
  - Notes: Despite being trained on `VGG16` (a CNN model pre-trained on ~14 million RGB, 224x224 images belonging to 1000 categories), the model did not perform better. This could be because the original model was trained on RGB images and non-facial expressions, while my dataset consisted of grayscale images exclusively of distinct facial expressions. Further testing needs to be done.
![model_3.png](https://github.com/jasminevasandani/know-your-ai/blob/master/notebook_images/model_3.png?raw=true)

## Model Evaluation
The following image and probability comparisons show what the image and actual emotion is, compared to the predicted emotion is and the probabilities of each emotion that the CNN model detected on the face. You'll see that some images have a high probability of one or two emotions, while others have a wide ranging distribution of predicted emotions. **See notebook for more evaluation visualizations.** 
<br>
![proba_1.png](https://github.com/jasminevasandani/know-your-ai/blob/master/notebook_images/proba_1.png?raw=true)
<br>
![proba_2.png](https://github.com/jasminevasandani/know-your-ai/blob/master/notebook_images/proba_2.png?raw=true)

## Conclusions and Next Steps 
Working on this project was challenging and exhilarating at the same time. I was surprised at the results of my model considering the small dataset and lack of distinct facial expressions belonging to the nine categories. This project can be used as a starting point to expand this project into something bigger. I hope to contribute my skills as a data scientist and researcher to the larger movement of building more inclusive and equitable AI algorithms. 

## Sources 
**Images**
<br>
I hand-selected images from each of these sources. Keep in mind that many royalty-free stock photo resources do not include a wide variety of emotion expression images. The Kanade and Brazilian FEI databases do not allow me to republish or share the images from their databases. Therefore when running this notebook, you can only start by uploading the csv file containing pixel data. **Because of image rights for certain images, this notebook can only be used for research purposes, and no images from this notebook shall be reproduced elsewhere. Appropriate image credit is given where necessary.**
  - [Vice’s Gender Spectrum Collection](https://broadlygenderphotos.vice.com)
  - [Flickr](https://www.flickr.com/) 
  - [Pexels](https://www.pexels.com/)
  - [Unsplash](https://unsplash.com/)
  - [Women of Color in Tech stock photos](https://www.flickr.com/photos/wocintechchat/) 
  - [Indian Movie Face Database](http://cvit.iiit.ac.in/projects/IMFDB/)
  - [Kanade, T., Cohn, J. F., & Tian, Y. (2000)](http://www.consortium.ri.cmu.edu/ckagree/)
  - [Brazilian FEI Face Database](https://fei.edu.br/~cet/facedatabase.html)

**Code References**
<br>
Deep Learning by Francois Chollet.

## Acknowledgements 
Thanks to the following people who guided and supported me as I completed this project: Anuva Kalawar, Awid (Boom) Devahastin Na Ayudhya, Matthew Brems, Riley Dallas, Tim Book.