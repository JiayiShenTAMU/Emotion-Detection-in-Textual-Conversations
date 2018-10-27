# Emotion-Detection-in-Textual-Conversations

#### Task Description

Our task is mainly about **detecting different emotions**, including happy, sad and angry in the users’ daily conversations and comments. For example, given a textual dialogue, i.e. a user utterance along with two turns of context, we want to classify the emotion of user utterance as one of the emotion classes: Happy, Sad, Angry or Others. However, as humans, on reading "Why don't you ever text me!", we can either interpret it as a sad or an angry emotion in absence of context; and the same ambiguity exists for machines as well. Because of lack of facial expressions and voice modulations, detecting emotions in text become harder. 

#### Dataset

The dataset we will use in our project is provided by [CodaLab Competition]( https://competitions.codalab.org/competitions/19790#learn_the_details-overview). This training data set contains 15K records for emotion classes i.e., Happy, Sad and Angry combined. It also contains 15K records not belonging to any of the aforementioned emotion classes. 

#### Model

This emotion analysis problem is a multi -classification problem.

We will use **NaiveBayes** and **SVM** as the baselines of our model. 

Our main method is to use **LSTM** for determining the class of the test set. The vector representation of words (can be implemented using several representations like **word2vec** or simply a bag of words model or models like **GloVe** model etc) are fed into the LSTM, thereby making a fully connected network and get probabilities of each of the classes and output the one with highest probability as our predicted class.

Another idea that we would like to try is turning the sentence first into **tree structure**, and implementing **RNN**、**RNTN** to do the classification.

#### Evaluation

Our evaluation, is same as the one followed by the SemEval task evaluation policy. Here, we are considering micro-averaged $F_1$ score for three emotion classes namely, happy, sad and angry for the predictions made on test set that happen in real world. The **precision** and **recall** are calculated as follows:

$Pµ =\frac{ ΣTP_i} {Σ(TP_i + FP_i)} \ \ \ \ \ \ ∀ i\in {Happy,Sad,Angry} $

$Rµ =\frac{ ΣTP_i} { Σ(TP_i + FN_i)} \ \ \ \ \ ∀i \in {Happy,Sad,Angry}$

Where $TP_i$, $FP_i$, $FN_i$ are true positives, false positives and false negatives of a given class $i$.

#### Reference

[Gupta U, Chatterjee A, Srikanth R, et al. A sentiment-and-semantics-based approach for emotion detection in textual conversations[J]. arXiv preprint arXiv:1707.06996, 2017.](https://arxiv.org/pdf/1707.06996.pdf)

[Socher R, Perelygin A, Wu J, et al. Recursive deep models for semantic compositionality over a sentiment treebank[C]//Proceedings of the 2013 conference on empirical methods in natural language processing. 2013: 1631-1642.](