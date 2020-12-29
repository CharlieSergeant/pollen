# Pollen Detection and Classification

The focus of this research is to automate the pollen data collection at the regional Pollen Counting Station for StarRx Technology Center at Kean University. Currently, the data is counted and analyzed by hand. This project proposes an architecture for fully automated pollen grain counting and classification using deep learning through Convolutional Neural Networks (CNN) and implements software for the automation process. Multiple CNN architectures were implemented and tested for optimal classification results. The software will demonstrate how deep learning feature extraction methods detect and classify pollen from microscopic videos for real time classification. The model will also account for location and time of year the video is recorded through a time dependent Recurrent Neural Network (RNN) due to certain types of pollen being more prevalent during different times of the year and locations.

## Data Pipeline (Pollen vs Not Pollen Classifier)
Training
1. Create custom dataset of pollen images
2. Load dataset to script
3. Image preprocessing (data augmentation, resizing, labeling)
4. Train on deep convolutional neural network transfer learned from imagenet weights (current network architecure: Xception https://arxiv.org/abs/1610.02357)

Testing
1. Load optimal trained weights from 4
2. Video classifier: load frame (every 20th frame is loaded)
3. Image preprocessing (denoise image using color and contour size thresholding,resize image)
4. Split image into (192,192,3) sections to be fed to classifier
5. Classify regions as Pollen or Not Pollen and output count per frame
