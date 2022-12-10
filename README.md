# video_action_recognition Using TSN _rgb

Download the video action recognition using MMAction2.ipynb file and just run it. reasons for implementing this method will be mentioned below.

The advancements in computer vision especially in image classification domain can't be used in video action recognition task because 2DCNN's can't understanding the time component or temporal dimension in the videos.

To solve this problem we have two choices:
1) using 3D CNN's to model the temporal dimension 
2) 2) using optical flow component to trian the model.
Using the 3D CNN is computationally expensive than the 2D CNN's. Using opticalflow component needs lot of memory to store the optical flow frames for large datset.
 The orginal TSN is based on two stream convnets one is rgb based, another is optical flow based.I have only used rgb based temporal segment method in this model. I didn't use the flow based convnet because the extraction process requires lot of computational power and the extracted frames needs storage.
reason for implementing TSN method: 
1)It uses the 2d CNN in its architecture.(makes the model light) 
2) while training uses single frame from each segments.(reduces the time required for training)
There are various method like TSM, TIN that works well with same or better advantages but I used TSN because of the resources related to TSN in MMaction2.

Model:
Used a pretrained model based on kinetic-400 Dataset.
Dataset:
This dataset contains 10 categories: 5 of them are the categories that are included in UCF101, and the other 5 categories are not. Each catefory has 10 videos, and each video lasts 5 seconds. The resolution of all videos is 320x180. The native FPS is 30.
imported from the following link https://github.com/soapisnotfat/Skyrim-Human-Actions
Training phase: 
  epochs=40
  top1_accuracy improved from 0.1 to 0.8
Testing or validation:
  top1_accuracy=0.8 
 
References:
1)https://mmaction2.readthedocs.io/en/latest/recognition_models.html#tsn
2)https://arxiv.org/pdf/2012.06567.pdf
3)https://github.com/soapisnotfat/Skyrim-Human-Actions


 
