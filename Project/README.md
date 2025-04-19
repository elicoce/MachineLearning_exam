
# ASL Alphabet Recognition

This project focuses on classifying American Sign Language (ASL) alphabet letters using various machine learning techniques, including classical algorithms and deep learning models. A key part of the project is the use of data augmentation to enhance the model’s performance, especially given the limited size and diversity of the dataset.

###  Dataset
Source:  https://www.kaggle.com/datasets/ayuraj/asl-dataset


The dataset used in this project is the ASL Alphabet Dataset on Kaggle, which contains images of hand gestures representing each letter of the ASL alphabet, as well as digits 0-9. 

For this project the letters J and Z were excluded from the dataset because they require motion, which is not captured in static images.

The small dataset size pose challenges for training deep learning models effectively.


 ### Project Overview

The project pipeline consists of several stages: 

- Data Preprocessing: class removal, normalization, and standardization
- Supervised Learning: K-Nearest Neighbors, Naive Bayes, Random Forest
- Neural networks
- Data augmentation
- Testing modified images on models trained with original data
- Convolutional neural networks

### Data Preprocessing:

- Grayscale Conversion: Remove the RBG channels to reduce input dimensionality.

- Resizing: All images were resized to a consistent shape of 128x128 pixels for compatibility with the models.

- Normalization: Pixel values were scaled to a range of [0, 1].

- Standardization: Some models were standardized for zero mean and unit variance, depending on the algorithm.

- Class Filtering: Classes J and Z were removed due to their motion-based nature.

### Machine Learning Algorithms:

Several classical machine learning algorithms were implemented using Scikit-learn: K-Nearest Neighbors (KNN), Naive Bayes, Random Forest.

These algorithms were evaluated on flattened image vectors using: Train/Test split, Cross-validation, Confusion matrix and classification report.

Deep Learning Models:

Two types of neural networks were used: Fully connected NN and Convolutinal NN with various number of layers.


###  Data Augmentation

Given the small dataset size, data augmentation was used to increase the diversity of the training data and prevent overfitting. Various transformations were applied to simulate different conditions under which hand gestures might be captured.

The transformations included:

   - Random Rotation: Images were randomly rotated within specified ranges (e.g., between 30° and 70° or -50° and -30°), simulating different hand orientations.

  - Random Resized Crop: A random portion of the image was cropped and resized to 128x128 pixels, with the crop size varying between 80% and 100% of the original image size.

- Random Perspective: The perspective of the image was randomly distorted to simulate different angles from which the gesture might be viewed.
- Affine Transformations: These involved translations (shifting) in both horizontal and vertical directions, as well as combining scaling, rotation, and translation to create even more variability in the dataset.

The goal of these augmentations was to allow the model to generalize better by exposing it to various forms of the gestures, even with limited data.


### Conclusion

This project demonstrates the effectiveness of combining classical machine learning models and deep learning techniques for recognizing hand gestures in ASL. The use of data augmentation was critical in improving model performance, particularly with deep learning models like CNNs, which showed the best generalization when trained on both original and augmented data.

Key Takeaways:
- Data augmentation greatly improved model robustness and generalization by simulating different hand positions, rotations, and perspectives.

- CNNs outperformed traditional machine learning algorithms such as KNN, Naive Bayes, and Random Forest, especially when trained on augmented datasets.

- Grayscale conversion and resizing helped simplify the models without losing crucial information from the images.
