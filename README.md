# An Optimized DGNN Architecture for Skeleton-Based Action Recognition

**CS 7643 - Deep Learning (Fall 2023)**

**Authors:**
- Sean Donnelly (sdonnelly8@gatech.edu)
- Clay Dustin (cdustin3@gatech.edu)
- Niko Lahanis (nlahanis3@gatech.edu)
- Andrew Mueller (amueller39@gatech.edu)

## Abstract
This project addresses Skeleton-Based Action Recognition (SBAR) using Directed Graph Neural Networks (DGNN). We introduce two novel architectural enhancements: Attention Layers and Dropout Layers, aimed at improving SBAR model performance. Using the NTU RGB+D 60 dataset, our enhanced model shows substantial accuracy gains over the baseline DGNN, especially with the inclusion of attention layers, while maintaining generalization through dropout layers.

## Introduction
Computer Vision (CV) has advanced significantly with applications like self-driving vehicles and facial recognition. Our focus is on Skeleton-Based Action Recognition (SBAR), leveraging Directed Graph Neural Networks (DGNNs). The human body is represented as a graph, with bones as edges and joints as vertices. DGNNs have shown strong performance in this area by converting human movement from video/image data into a Directed Acyclic Graph (DAG).

## Proposed Enhancements
### Attention Layers
Attention layers allow the DGNN to focus on essential nodes and learned features, improving predictive power.

### Dropout Layers
To counter overfitting, dropout layers promote better generalization during model training.

## Methodology
### Dataset
We used the NTU RGB+D 60 dataset, comprising 113,945 samples over 60 classes, captured from 106 subjects and 32 camera setups. Our training focused on the Cross-View benchmark, with 54,468 samples for training and 59,477 for testing.

### Model Architecture
We built upon the baseline DGNN architecture, which uses Graph Temporal Convolution (GTC) layers, comprising DGN and TCN blocks. Our enhancements included the integration of attention and dropout layers within this framework.

### Training and Testing
Models were trained for 20 epochs on 25% of the dataset, and the highest-performing model was further trained on 50% of the data for 60 epochs. We used Cross-Entropy loss and Top K accuracy metrics.

## Results
Attention layers (specifically Attention 2 and Attention 3) significantly improved accuracy compared to the baseline DGNN. However, with more convolution layers and larger channel dimensions, the baseline model performed better, indicating that convolution layers effectively model multi-scale motions.

## Computational Demands
Due to computational constraints, we had to reduce the training data size and the number of layers. Training was done on an NVIDIA GeForce RTX 3080 GPU, and a preliminary cloud setup was tested on Google Cloud's Vertex AI platform.

## Challenges and Successes
### Challenges
- Cloud/Machine limitations
- Large dataset size
- Model ambiguity

### Successes
- Significant accuracy increase with Attention 2 and Attention 3
- Improved generalization with dropout layers

## Conclusion and Future Work
Our work highlights the potential of attention and dropout layers in DGNNs for SBAR. Future research should explore these enhancements on larger datasets and other frameworks. Further scaling and analysis are needed to fully understand their efficacy.

## Work Division
- **Sean Donnelly:** Version Control, Model Implementation, PyTorch Geometric Investigation, Model Training
- **Clay Dustin:** Google Cloud Implementation, Model Training, Model Evaluation/Results
- **Niko Lahanis:** Google Cloud Implementation, Business Case Analysis, Model Testing
- **Andrew Mueller:** Attention Layer Design, Model Implementation, Model Training

## Acknowledgements
Special thanks to ROSE Lab for providing the NTU RGB+D 60 dataset and to our peers and instructors for their valuable feedback and support.
