# Intel-Scene-Classification
This repository includes various approaches I employed when I took part in the Intel Scene Classification Challenge. 
I finished in the top 5%. A detailed explanation of these approaches, along with the confusion matrices can be found in [my article here](https://becominghuman.ai/lessons-from-my-first-deep-learning-hackathon-42ced244a38d).

# Competition details

![Sample image](https://github.com/dipam7/Intel-Scene-Classification/blob/master/images/image_1.png)

![Sample image](https://github.com/dipam7/Intel-Scene-Classification/blob/master/images/image_2.png)


**Note**: I had planned on uploading all the trained models, i.e `.pth` files on Github. However due to size restrictions of the free plan (even after using git lfs) I wasn't able to upload them. The files can be downloaded from my [Kaggle](https://www.kaggle.com/dipam7).
## Explanation of the various approaches used

### 0. [Basic approach](https://github.com/dipam7/Intel-Scene-Classification/blob/master/basic_approach/nb/intel-scene-classification-basic-approach.ipynb)

In this approach we don't do much. We stick to most of fastai's default data augmentations except switching off one or two which
don't make sense. We use ResNet34 as our pretrained model, find the learning rate and train for a few epochs. We manage to achieve
an accuracy of ~93%. In the following approches we try to improve upon this model (in terms of accuracy and confusion b/w certain classes)

![Sample image](https://github.com/dipam7/Intel-Scene-Classification/blob/master/images/image_3.png)


### 1. [Different architectures](https://github.com/dipam7/Intel-Scene-Classification/blob/master/different_models/nb/intel-scene-classification-using-different-models.ipynb)

In this approach, we follow the exact same steps that we used in the basic approach except this time, 
instead of only trying ResNet34, we also try ResNet50 and ResNet101.

**ResNet50**

![Sample image](https://github.com/dipam7/Intel-Scene-Classification/blob/master/images/image_4.png)

**ResNet101**

![Sample image](https://github.com/dipam7/Intel-Scene-Classification/blob/master/images/image_5.png)


### 2. [Progressive image resizing](https://github.com/dipam7/Intel-Scene-Classification/blob/master/progressive_image_resizing/nb/intel-scene-progressive-image-resizing.ipynb)

Experiments have shown that if we train our model with lower resolution images and then use those weights to train our model with higher resolution images, our accuracy improves. 
And this is what we’ve tried in our second approach.

Results below:

![Sample image](https://github.com/dipam7/Intel-Scene-Classification/blob/master/images/image_6.png)


### 3. [Removing confusion](https://github.com/dipam7/Intel-Scene-Classification/blob/master/removing_confusion/nb/intel-scene-removing-confusion.ipynb)

Even after using better models and progressive image resizing, the confusion between some of the classes (mountains and glaciers) did not reduce. In this approach, I tried to train the model with the non-confused classes first and then show it all the classes later (i.e first show it only mountains and later show it glaciers as well). Unfortunately, this approach didn't work well.
Results below:

![Sample image](https://github.com/dipam7/Intel-Scene-Classification/blob/master/images/image_7.png)

### Further learning

When we plot top losses, we see what parts of images that our model is picking up. These parts can be wrong (picking up the background instead of the mountain) and hence cause misclassification. I would like to learn how to improve on this.

![Sample image](https://github.com/dipam7/Intel-Scene-Classification/blob/master/images/image_8.png)




