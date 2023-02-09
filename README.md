# Food101TM-using-Tensorflow
started from simple tiny VGG using subset of data (only 10 classes) with accuracy of 0.3 to a model leveraging transferlerning. Came close to deepfood score


foodVision Sequence of models tried to improve accuracy:
model_0: Using entire data (10 classes) ,5 epochs , ting VGG, No transfer learning, No data augmentation, val_acc: 0.31. overfitting observed

model_1: Using entire data (10 classes), 5 epochs , ting VGG, No transfer learning, No data augmentation, reduced 1 layer to try preventing overfitting. overfitting not reduced as maxpool layer remval caused more training params. acc: 0.30 

model_2: Using entire data (10 classes) , 5 epochs ,ting VGG, No transfer learning, Tried data augmentation (sheared, rotatate, flip) + increased stride of MaxPool layer. Val_acc and train_acc curves now parallel thus got rid of overfitting but accuracy still low= 0.42

model_3: Using Transfer learning, Only 10% of data (10 classes) ,data augmentation, 5 epochs. Used resnet  feature extractor (from tensorhub) added output layer on top (23.5 M params, 20k trainiable). acc: 0.779

model_4: Using Transfer learning, Only 10% of data (10 classes) ,data augmentation, 5 epochs. Used resnet  feature extractor (from tensorhub) added output layer on top (4 M params, 12k trainiable). val_acc: 0.86

model_5: (hist_model_2_finetuned) Using fine tuning transfer learning, Only 10% of data (10 classes) ,data augmentation, 10 epochs. 


model_6: Whole dataset with 101 classes. Used as in transfer learning. All layers frozen in base model. val_acc: 0.72

model_7: Whole dataset with 101 classes. Used tuning transfer learning. All layers except last 10 frozen in base model. val_acc: 0.75
