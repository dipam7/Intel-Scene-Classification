# Intel-Scene-Classification
This repository includes various approaches I employed when I took part in the Intel Scene Classification Challenge. 
I finished in the top 5%. A detailed explanation of these approaches, along with the confusion matrices can be found in [my article here](https://becominghuman.ai/lessons-from-my-first-deep-learning-hackathon-42ced244a38d).

-- add a folder for images and insert image_1 and image_2 here

**Note**: I had planned on uploading all the trained models, i.e `.pth` files on Github. However due to size restrictions of the free plan (even after using git lfs) I wasn't able to upload them. The files can be downloaded from my [Kaggle](https://www.kaggle.com/dipam7).
## Explanation of the various approaches used

### 0. [Basic approach](https://github.com/dipam7/Intel-Scene-Classification/blob/master/basic_approach/nb/intel-scene-classification-basic-approach.ipynb)

In this approach we don't do much. We stick to most of fastai's default data augmentations except switching off one or two which
don't make sense. We use ResNet34 as our pretrained model, find the learning rate and train for a few epochs. We manage to achieve
an accuracy of ~93%. In the following approches we try to improve upon this model (in terms of accuracy and confusion b/w certain classes)

-- insert image_3

### 1. [Different architectures](https://github.com/dipam7/Intel-Scene-Classification/blob/master/different_models/nb/intel-scene-classification-using-different-models.ipynb)

In this approach, we follow the exact same steps that we used in the basic approach except this time, 
instead of only trying ResNet34, we also try ResNet50 and ResNet101.

**ResNet50**

-- insert image

**ResNet101**

--insert image_5

### 2. [Progressive image resizing](https://github.com/dipam7/Intel-Scene-Classification/blob/master/progressive_image_resizing/nb/intel-scene-progressive-image-resizing.ipynb)

Experiments have shown that if we train our model with lower resolution images and then use those weights to train our model with higher resolution images, our accuracy improves. 
And this is what we’ve tried in our second approach.

Results below:

--insert image_6

### 3. [Removing confusion](https://github.com/dipam7/Intel-Scene-Classification/blob/master/removing_confusion/nb/intel-scene-removing-confusion.ipynb)





