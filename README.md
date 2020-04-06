# pytorch_CNN_with_Augmentation
## Augmentation experiment record
### Image Transformation Visualization
![image](https://github.com/vbnmzxc9513/pytorch_CNN_with_Augmentation/blob/master/img/img_transform_visualization.png)

### Resnet18 no use pretrained model
![image](https://github.com/vbnmzxc9513/pytorch_CNN_with_Augmentation/blob/master/img/Resnet-18_no_pretrained.png)

### Resnet18 use pretrained model
![image](https://github.com/vbnmzxc9513/pytorch_CNN_with_Augmentation/blob/master/img/Resnet-18_pretrained.png)

### Resnet18 no use pretrained model and image random transformation in each epoch as augumentation 
![image](https://github.com/vbnmzxc9513/pytorch_CNN_with_Augmentation/blob/master/img/no_pretrained_transformation.png)

### Resnet18 use pretrained model and image random transformation in each epoch as augumentation 
![image](https://github.com/vbnmzxc9513/pytorch_CNN_with_Augmentation/blob/master/img/pretrained_transformation.png)

### Resnet18 no use pretrained model and image random transformation in each epoch and balance dataloader as augumentation 
![image](https://github.com/vbnmzxc9513/pytorch_CNN_with_Augmentation/blob/master/img/no_pretrained_transformation_dataloader_balance.png)

### Resnet18 use pretrained model and image random transformation in each epoch and balance dataloader as augumentation 
![image](https://github.com/vbnmzxc9513/pytorch_CNN_with_Augmentation/blob/master/img/pretrained_transformation_dataloader_balance.png)

## Experiment

After a series of experiments, it was found that in terms of parameter changes, the most significant effect was when the learning rate was changed from 0.001 to 0.0001, and the image size was changed from 144 to 224, but the part that modified the image size was the above experiment. It was discovered after the screenshot was taken, so there was no re-experimentation because of time. Learning rate of 0.001 according to the experimental results is too large for this data set. Resizing image bigger can improve accuracy, but it also consumes GPU memory. In the experiment, there were no significant differences between using batch sizes of 64, 32, and 16.
     
     
In terms of enhancement, if a pre-trained model is used, neither the training amount per epoch or the various transformations on the image is too significant, and the model will soon complete convergence. Therefore, the food11-skewed data set may be Pre-trained models Conversely, if no pretrained model is used, Augmentation will have a great effect. However, in the experiments of this Dataset, various transformations are randomly applied to the image, and the subsequent use of WeightRandomSampler does not improve much.
     
     
Surprisingly, applying the WeightRandomSampler to the training of the pretrained model slightly increases the accuracy, but the training on the not pretrained model has no effect but loses accuracy, and it is honestly difficult to make a decision Which method is effective, sometimes the accuracy is a little negligible, but the result shows that if the methods of Augmentation have been done, the accuracy is almost the same even if there is no increase if there is no time to do so in the future Multiple tests. Applying all the methods in this experiment directly will have the best chance to get good training results.
