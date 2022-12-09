# Group 9C Capstone

This project is our group's initial foray into the world of Natural Language Processing and Machine Learning. We worked on this as part of the NUS SGUS Fintech Program's Capstone Project. In this repository, we are mainly focusing on delivering two things:
1. Being able to classify statements into different "types" of statements.
2. Being able to extract temporal information from text.

<a href="https://github.com/squaluz/Group-9C-Capstone/blob/main/semeval2010task8_train.txt">Train Data File</a>
Data for training the model

<a href="https://github.com/squaluz/Group-9C-Capstone/blob/main/semeval2010task8_test.txt">Test Data File</a>
Data for testing the model


In file "1 SemEval10 Multiclassification", you will find a code write in python and run on google colab to evaluate several models that can be used for text classification. In the training and test data, we have 10 "types" of statements, including cause-effect, product-producer, instrument-agency etc. We have evaluated 4 different models for doing text classification: Multinomial Naive Bayes, Multinomial Naive Bayes w optimized parameters, Support Vector Machine and Support Vector Machine w Linear Kernel (optimized). The last model returned the greatest accuracy.

After we had showcased file 1 to our stakeholders, we gathered some feedback on how to better the code. In file "2 SemEval10 Binary Classification", we implemented some of these improvements, including changing the classification to a binary one "cause-effect" vs "others". What we noticed is that this change had resulted in skewed train/test data, with many statements in "others". In file "2A SemEval10 Binary Classification", we tried doing oversampling to tackle the skewed data. We also ran the data through a preprocessing step (though for this particular dataset it did not seem to make any difference in accuracies). Lastly, we had done some additional research on the use of gridsearch for hyperparameter tuning and corrected our codes to incorporate that.

In file "3 SVM Binary Classification with Temporal Extraction", we had utilized the model with the best accuracy from file "2 SemEval10 Binary Classification" - Support Vector Machine with Linear Kernel - to conduct a binary classification to identify "cause-effect" statements. The code then uses spacy with a roberta transformer to extract temporal information. This performed much better than spacy without the transformer - better in the sense it could pick out dates in any form eg. "04.10.2022" and also relevant time period information like "Q2" which normal spacy could not do.




