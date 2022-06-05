**Pneumonia Classfication Problem: Identity signs of pneumonia in X-ray images**

**Data Used:**
 - RSNA Pneumonia detection problem https://www.kaggle.com/c/rsna-pneumonia-detection-challenge
 - 26684 X-ray images with tags
    - 1: 20672  
    - 0: 6012

**Preprocessing:**
 - Original Shape (1024 x 1024) to Resize Image (224 x 224)
 - Standardise the pixel values into the interval [0,1] by scaling with 1/255
 - Split data into train and validation
 - Store converted images in corresponding 1/0 folder
 - Computed mean and std deviation for image normalization
 - Augmentation: (All Random)
    - Rotation
    - Translations
    - Scales
    - Resized Crops

**Training:**
 - Netwrok used: Resnet18
   - Changed imput channels from 3 to 1
   - Chaged output channel from 1000 to 1
 - Loss Function: BCEWithLogitsLoss
   - Directly applied to logits (raw prediction)
   - Negative output: No pneumonia
 - Optimizer: ADAM
 - Train for 50 epochs
