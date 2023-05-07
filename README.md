
# CRISPR Repair Outcome Prediction

This is a machine learning model that predicts the outcome of CRISPR-mediated genome editing experiments. Specifically, the model predicts the repair outcome of a double-stranded break (DSB) induced by the CRISPR-Cas9 system. The outcome can be one of the following: non-homologous end joining (NHEJ), homology-directed repair (HDR), or a combination of both.

The model is trained on a dataset of CRISPR-mediated DSB repair outcomes, which includes information about the guide RNA sequence, the target DNA sequence, and the repair outcome. The model uses a neural network architecture that takes as input the guide RNA and target DNA sequences and outputs a probability distribution over the three possible repair outcomes.


## Dataset

**CRISPR Repair Outcome Prediction Task**

[TDC - CRISPROutcome](https://tdcommons.ai/single_pred_tasks/CRISPROutcome/)
## Data Preprocessing

The input data is a set of CRISPR guide RNA sequences and their corresponding repair outcomes, represented as continuous values between 0 and 1. The dataset is preprocessed by one-hot encoding the RNA sequences, where each nucleotide is represented as a binary vector of length 4 (A, C, G, and T). The resulting one-hot encoded sequence has a length of 23 (corresponding to the length of the CRISPR guide RNA), and is used as input to the model.
## Feature Extractor & Model

### Feature Extraction

The feature extraction is performed using a convolutional neural network (CNN) architecture. The one-hot encoded RNA sequence is first passed through a series of convolutional layers, which apply a set of learned filters to the input sequence. The outputs of the convolutional layers are then passed through a series of max-pooling layers, which downsample the output feature maps. Finally, the output of the max-pooling layers is passed through a fully connected layer, which produces a single output representing the predicted repair outcome.

### Model Architecture

The model architecture used in the CRISPR Repair Outcome Prediction is a variant of the standard CNN architecture. The model consists of several convolutional layers, followed by max-pooling layers and a fully connected layer. The convolutional layers use 1D filters of length 4 and varying numbers of output channels. The max-pooling layers use a pool size of 2 and a stride of 2. The fully connected layer has a single output unit, which represents the predicted repair outcome. The model is trained using the mean squared error loss function and the Adam optimizer. The model is evaluated using the mean squared error, Pearson correlation, p-value, and the concordance index.
## Result

**TestSet Performence Metric** 

MSE: 0.01002 , Pearson Correlation: 0.76440 with p-value: 1.62E-59 , Concordance Index: 0.78183
