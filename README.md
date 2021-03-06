# walle
Weak audio labels limitations for embeddings

This repo is the implementation of:
 "Limitations of weak labels for embedding and tagging" accepted to ICASSP 2020.
 
**Note: this is still a work in progress, an extension will be done** 
so if there are any bug or if you want details about something, do not hesitate.
 
# Data
The data used in this experiment are derived from DESED dataset.
See data_utils to see how to reproduce the data.

# 3 epxperiments
The 3 experiments use the same network architecture, but trained differently

## Classifier
The classifier is a simple CRNN train end to end.

## Protoypical network
We train the prorotypical network by sampling some data of each class in each batch.
Some of the data are used to make the "prototypes" and the others are used to do the "training".
We associate each data for training to the closer prototype and use a classification loss to train the model.

## Triplet network
We create triplets (anchor, positive, negative) of data and we use the difference of distance in the embedding
space to do the training 
(we add a fix margin to the positive distance to try to increase the distance with the negative.) 


## Reference

N. Turpault, R. Serizel, E. Vincent, "Limitations of weak labels for embedding and tagging", 
in Proc. ICASSP 2020, Barcelona, Spain.