# German-Traffic-Signals-Classes-Detector
This Repository contains the code, dataset, trained model for GTSRB - German Traffic Sign Recognition Benchmark dataset on kaggle.This model has 43 classes containing different type of classes, more than 50,000 images.
#
It has a custom built Convolutional Neural Network(CNN) model with 8 layers in total.With only 10 epochs    
Training set accuracy: 98.03%  
Validation Set accuracy: 98.64%  
Test Set accuracy: 95.15%  
Train.csv file contains coordinates of ROI in each training image.  
#
Model is saved is 'German_traffic_signal.h5'  
# Links
Link for GTSRB - German Traffic Sign Recognition Benchmark Dataset on kaggle: https://www.kaggle.com/datasets/meowmeowmeowmeowmeow/gtsrb-german-traffic-sign?select=Train.csv  
Drive Link containing pretrained model, dataset and jupyter notebook: https://drive.google.com/drive/folders/1LY6pi2NMzrfpJlPIRrXFFR5jghFveaF-?usp=sharing

# Update
In the recent iteration I have updated  
```
hist = model.fit(X_train, Y_train, epochs = 10, batch_size = 64, validation_data=(X_val, Y_val))
```
with
```
hist = model.fit(X_train, Y_train, epochs = 50, batch_size = 64, validation_data=(X_val, Y_val), callbacks = [tf.keras.callbacks.EarlyStopping(
monitor = 'val_loss', patience = 5, restore_best_weights = True, verbose = 1), tf.keras.callbacks.ReduceLROnPlateau(
monitor = 'val_loss', patience = 8, verbose = 1)])
```
