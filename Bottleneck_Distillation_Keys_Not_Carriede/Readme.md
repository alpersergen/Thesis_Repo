# Distillation between BERT and DistilBERT with Discrete Key-Value Bottleneck

This repository contains code for knowledge distillation from a teacher model (BERT with Discrete Key-Value Bottleneck) to a student model (DistilBERT with Discrete Key-Value Bottleneck) using the GLUE benchmark datasets. The distillation process aims to transfer knowledge from the more complex teacher model to the more compact and faster student model.

## Models

- `BERTwithBottleNeck`: BERT model with a discrete key-value bottleneck.
- `DistilBERTwithBottleNeck`: DistilBERT model with a discrete key-value bottleneck.

## Data Preprocessing

We use the `CustomDataset` class to preprocess and create custom datasets from the GLUE benchmark datasets for training, validation, and testing.

## Optimization

We use the AdamW optimizer to update the parameters of the student model during training.

## Distillation Loss

We calculate the distillation loss, which is the Kullback-Leibler (KL) divergence between the teacher and student model logits, scaled by a temperature factor. This loss guides the student model towards the teacher's predictions.

## Training Loop

We train the student model using the distillation loss and evaluate its performance on the validation set.

## Metrics

We calculate metrics such as F1 Score, Matthews Correlation Coefficient (MCC), and accuracy to evaluate the performance of the student model during training and validation.

## How to Use

To use this code for distillation between BERT and DistilBERT with Discrete Key-Value Bottleneck, follow these steps:

1. Install the required libraries: Make sure you have installed the necessary libraries, including Transformers and other dependencies.
2. Prepare Data: Load the GLUE benchmark datasets (MNLI, RTE, CoLA, MRPC, QNLI, SST2, STSB, QQP) and create custom datasets using the `CustomDataset` class.
3. Train the Student Model: Run the training loop to distill knowledge from the teacher to the student model. Adjust hyperparameters such as batch size, learning rate, and number of epochs as needed.
4. Evaluate the Student Model: Evaluate the performance of the student model on the validation set using F1 Score, MCC, and accuracy metrics.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

This project is based on knowledge distillation techniques and makes use of the Transformers library. Special thanks to the authors and maintainers of these libraries for providing the tools to facilitate research in natural language processing.