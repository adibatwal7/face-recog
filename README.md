# Facial Verification System using Siamese Neural Networks
## Introduction
This repository contains a facial verification system implementation based on Siamese Neural Networks. The system is designed to verify whether two facial images belong to the same person by learning a similarity metric, rather than classifying specific identities.
Siamese Neural Networks are particularly effective for facial verification tasks as they can be trained on pairs of images to determine their similarity. This approach is especially valuable when dealing with limited training data per identity or verifying identities not seen during training.
## Project Overview
This implementation provides an end-to-end solution for facial verification, including:

- Face detection and alignment preprocessing
- Feature extraction using a Siamese architecture
- Similarity computation and threshold-based verification
- Evaluation metrics for system performance
## Pipeline Process
The facial verification system employs a comprehensive processing pipeline implemented in main.py. Initially, input images are preprocessed through face detection using a cascade classifier, followed by alignment based on facial landmarks to normalize pose variations. These aligned faces are then fed into the Siamese Neural Network architecture where twin convolutional networks with shared weights process the images in parallel. Each network generates a fixed-length embedding vector that represents the facial features in a high-dimensional space. The system then calculates the Euclidean distance between these embeddings to determine similarity. A threshold-based decision mechanism, optimized during training, determines if the faces belong to the same person. The pipeline includes additional components for handling various image conditions such as different lighting and angles, with normalization techniques applied throughout to ensure robust performance across diverse inputs.
##Dataset Organization
The dataset is structured into three distinct folders that serve specific purposes in training the Siamese Neural Network. The "anchor" folder contains the reference facial images that serve as the baseline for comparison. The "positive" folder holds different images of the same individuals present in the anchor folder, enabling the network to learn intra-class similarities. For the "negative" folder, I collected diverse facial images from the Kaggle "Labeled Faces in the Wild" (LFW) dataset, which provides a rich variety of facial images across different individuals, expressions, lighting conditions, and backgrounds. This three-folder organization facilitates the contrastive learning approach, where the network is trained to minimize the distance between anchor-positive pairs while maximizing the distance between anchor-negative pairs. This structure is particularly effective for training the model to distinguish between subtle facial differences while remaining robust to variations in appearance for the same individual.
