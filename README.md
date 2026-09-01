# Animal vs Vehicle Recognition with CIFAR-10

## Project objective
This project implements a convolutional neural network (CNN) to classify images into two classes: animals and vehicles. The system uses CIFAR-10, a standard benchmark dataset containing labeled images of everyday objects and animals, and remaps the original labels into a binary classification problem.

## Business context
The project is designed as a prototype for road-safety and urban monitoring scenarios. In a real-world setting, a system like this could support wildlife detection near roads, reduce the risk of animal-vehicle collisions, and improve visual monitoring pipelines in smart-city environments.

## Dataset
- Dataset: CIFAR-10
- Images: 32x32 RGB
- Total classes: 10
- Re-mapped task: 2 classes
  - Animal = 1
  - Vehicle = 0

Animal classes used in this project:
- bird
- cat
- deer
- dog
- frog
- horse

Vehicle classes used in this project:
- airplane
- automobile
- ship
- truck

## Methodology
1. Load CIFAR-10 data.
2. Normalize pixel values to the [0, 1] range.
3. Flatten labels and transform them into a binary target.
4. Build a CNN for binary image classification.
5. Train the network on the training data and validate on the test set.
6. Monitor key metrics such as loss, accuracy, precision, recall, and validation loss.
7. Use early stopping and checkpointing to save the best model.
8. Evaluate the final model using a confusion matrix and classification report.

## Model architecture
The architecture is designed for a lightweight but effective CNN:
- convolutional blocks with ReLU activation
- batch normalization
- max-pooling layers
- flattening
- dense layer
- dropout regularization
- final sigmoid output layer for binary classification

Because the problem is binary, the final layer contains a single output neuron with sigmoid activation, and the chosen loss function is binary cross-entropy.

## Training setup
- Optimizer: Adam
- Loss: binary cross-entropy
- Metrics: accuracy, precision, recall
- Callback: EarlyStopping
- Callback: ModelCheckpoint

## Evaluation metrics
The model is assessed through:
- accuracy
- precision
- recall
- validation loss
- validation accuracy
- confusion matrix
- classification report

These metrics provide both an overall view of the model quality and a more detailed view of class imbalance, false positives, and false negatives.

## Results
The training process shows a clear reduction in loss and a strong increase in both training and validation metrics. The final model reaches strong validation performance, indicating that the CNN successfully learns to distinguish between animal and vehicle images.

## Limitations
This project is a simplified prototype and does not yet include full production-grade optimizations such as aggressive data augmentation, transfer learning, or extensive hyperparameter tuning. In addition, the label distribution is not perfectly balanced, which can influence classification behavior if not handled carefully.

## Conclusion
This project demonstrates that a CNN can effectively perform binary image classification on CIFAR-10 when the labels are remapped to the required task structure. The final network delivers a solid performance for animal-vs-vehicle recognition and provides a practical foundation for further improvement and deployment.
