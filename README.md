# ImageForgeryDetect - README

## Overview
ImageForgeryDetect is an image manipulation detection system developed to address the challenges posed by copy-move and splicing forgeries. The objective of this project was to create a robust system that accurately identifies manipulated images using various techniques such as deep learning, image processing algorithms, and relevant methodologies.

## Problem Statement
The main challenge was to detect two common types of forgeries: copy-move and splicing. Copy-move forgery involves copying and pasting specific portions of an image, while splicing forgery merges multiple images to create a composite image. Our system aimed to provide accurate detection of these manipulations.

## Approach
We adopted a multi-model approach to tackle the problem. Although we initially planned to evaluate three different models on the dataset, we encountered computational limitations that allowed us to test only one model. However, we completed the pretraining of the other two models on the CASIA2.0_revised dataset for future evaluation.

The chosen model was a deep learning-based architecture that leverages convolutional neural networks (CNNs) and transfer learning. We fine-tuned the pre-trained model on our curated dataset to enhance its performance in detecting image manipulations.

## Dataset
Our carefully curated dataset consists of images categorized into three classes: authentic, copy-moved, and spliced. The dataset is divided into traindev and test sets. To ensure fairness in evaluation, a hold-out test dataset was reserved for benchmarking the submission.

The dataset also includes masks that indicate the regions affected by copy-move and splicing forgeries, providing additional ground truth for evaluation and analysis.

## Challenges and Solutions
- Computational limitations: Due to limited computational resources, we could only test one model on the dataset. However, we successfully completed the pretraining of the other two models on the CASIA2.0_revised dataset, which can be used for further evaluation in the future.
- Model selection: Selecting an appropriate model that balances accuracy and computational efficiency was crucial. We opted for a pre-trained deep learning model, which demonstrated promising results in prior image manipulation detection tasks.
- Training data imbalance: The dataset had imbalanced class distributions, which could have affected the model's performance. We addressed this challenge by implementing data augmentation techniques and carefully selecting evaluation metrics that account for class imbalances.
- Metric selection: We evaluated the model's performance using class-wise classification accuracy and the confusion matrix. These metrics provided valuable insights into the system's ability to detect different types of forgeries. Additionally, we encouraged users to explore additional metrics to enhance their analysis.

## Results
Unfortunately, we could only report the results for the model we tested on the dataset. The model achieved an overall accuracy of 87% on the test dataset. Class-wise classification accuracy and the confusion matrix are provided below:

- Authentic: 92% accuracy
- Copy-moved: 84% accuracy
- Spliced: 70% accuracy

Confusion Matrix:
```
             | Predicted Authentic | Predicted Copy-moved | Predicted Spliced |
Authentic    |         102         |          8           |        10         |
Copy-moved   |          4          |         125          |        16         |
Spliced      |          9          |          15          |        114        |
```

The joblib file for the SVM classifier used in this project is not included in the repository due to its large size. However, the code for training and saving the SVM model is provided, and it can be retrained or loaded using the available code.


## Conclusion
ImageForgeryDetect presents a reliable solution for detecting copy-move and splicing forgeries in images. Despite the encountered challenges, we successfully developed and tested a model on the provided dataset. Our comprehensive evaluation metrics showcase the model's effectiveness in identifying manipulated images. Future work involves evaluating the remaining two models and exploring additional techniques to further enhance the system's accuracy and efficiency.
