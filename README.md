## Note - This repo is still WIP

# Rakuten France Multimodal Product Data Classification 

I took part in the Rakuten Data Challange and solved the various components for the multimodal product classification.  
This challenge focuses on the topic of large-scale product type code multimodal (text and image) classification where the goal is to predict each product’s type code as defined in the catalog of Rakuten France.  

As a part of the challangae, I have:

## 1. Trained a VGG 16 model from scratch
VGG16 is a convolution neural net (CNN) architecture which is considered
to be one of the excellent vision model architecture till date. Most
unique thing about VGG16 is that instead of having a large number
of hyperparameter it focuses on having convolution layers of 3x3
filter with a stride of 1 and always uses the same padding and
maximum pooling layer of 2x2 filter of stride 2.
You can read more about [VGG16](https://neurohive.io/en/popular-networks/vgg16/)

The model has 134 million trainable paramters. 

In order to avoid overfitting, I applied early stopping on validation accuacy. 

**Model hyperparameters**
• The model has steps per epoch equal to 100 i.e. the total
number of steps (batches of samples) before declaring one
epoch finished and starting the next epoch.  
• For the early stopping the patience is 20 epochs, with
monitor on validation accuracy.  
• Total number of steps (batches of samples) to validate
before stopping i.e. the validation steps are set to 100  
• Total number of epochs is 50.  

## 2. Built a Neural Network for doing multiclass classification using text data
  
Text mining is the process of automatically extracting "high
quality" information from text. High-quality information is
typically derived by transforming the free (unstructured) text in
documents and databases into normalized, structured data suitable
for analysis or to drive machine learning (ML).

Here, I converted the text field into a TF-IDF matrix after doing proper text pre-processing using SpaCy.  
TF-IDF is intended to reflect how
relevant a term is in a given document. The intuition behind it is
that if a word occurs multiple times in a document, we should boost
its relevance as it should be more meaningful than other words that
appear fewer times (TF). At the same time, if a word occurs many
times in a document but also along many other documents, maybe
it is because this word is just a frequent word; not because it was
relevant or meaningful (IDF).  

This TF- IDF matrix was used as an input in a Neural Network with custom  achitecture and 16 million trainable parameters. 

## 3. Compared various Ensemble Learning Techniques on the TF - IDF matrix obtained from the text data
  
The TF- IDF marix obtained above was used a input of various ensemble learning models viz. XGBoost, AdaBoost, Random Forest, Gradient Boost etc.  

This gave me an opportunity to do a comparitive study of various Ensemble Learning models and also apply the knowledge gained during the ensemble learning course I followed. 

Note - Due to the NDA signed during the competition can not upload the data files here.  

More details about the data challange can be found here:
https://challengedata.ens.fr/participants/challenges/35/
