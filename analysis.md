4.1- Looking at the "GoEmotion by Emotion" graph, we can see that the data is unbalanced. Over 50000 data points are marked as neutral, whereas most other emotion labels have less than 10000 data points. For sentiments, the data is unbalanced, but less so. We can see that positive and neutral emotions are around a third of the total dataset, however abiguous counts for only ~11% of the dataset. As a result, we need to be careful about which metrics we use. If we use only accuracy to evaluate the performance of our models, we could run into issues. For example, a model that labels everything as 'neutral' could have a relatively high accuracy. Since this is something we want to avoid, we should use a different metric such as precision, recall, or F1 score.

4.2 - 
Multinomial Naive-Bayes
    emotion score:0.161
    sentiment score: 0.545
Decision Trees
    emotion score: 0.358
    sentiment score:0.545
Multi-Layered Perceptron
    emotion score: 0.383
    sentiment score:0.554
The emotion score for MNB may be lower than the other types of classifications may be because that this model assumes features being mutually independent. This assumption is not usually the case in real life thus making it less accurate. 

When looking at the report of precision, recall and f1-score for MNB, all of the scores for the different classes of emotions are 0 except that of neutral which are 0.49 (precision), 0.5 (recall) and 0.49(f1 score). This could be due to the fact that this model will ignore irrelevent features (ex. unknown features) thus not allowing overfitting to occur. 

The sentiment scores being generally higher than that of the emotions could be due to the fact that there are much less lables needed to be classified into than the emotions lables. There are only 4 classes in sentiment compared to 28 classes in emotions. 

---Using GridSearchCV---

Top Multinomial Naive-Bayes
    emotion score:0.4
    sentiment score: 0.55
Top Decision Trees
    emotion score: 0.39
    sentiment score:0.42
Top Multi-Layered Perceptron
    emotion score: 0.42
    sentiment score:0.57
    
Like earlier, the multinomial naive-bayes performing less well than the other two models could be due to its nature of assuming independence between features and ignoring irrelevent features. However, its emotion score is higher than before which could be thanks to the added hyperparameter. For multinomial naive-bayes we can try adding more hyperparameters as parameters for gridsearch so we can find the best hyperparameters for this classifier.

The scores after using hyperparameters are only slightly better than without hyperparameters. When looking at decision trees, having a depth of 8 is better than having a depth of 3 and having a minimum sample split of 5 is better than 3. From this, we can deduce that allowing more precise splitting and categorizing of data allows for better accuracy. And to reach the optimal hyperparameters for decision tree classifier we have to choose a larger number to see what is the optimal depth and minimum sample split.

When changing the size of training and testing sets, this changes the accuracy of the model. In our case, the size of the training dataset were lowered to 50% and the testing dataset raised to 50%. This lowered the overall accuracy for every model in all cases. Which was expected since there are less data sets to which the model can train to. 
For example, looking at the decision trees: 
    emotion f1 accuracy = 0.12
    sentiment f1 accuracy = 0.27
    emotion f1 accuracy with gridSearch = 0.29
    sentiment f1 accuracy with gridSearch = 0.32
    
For the multi-layered perceptron case, there were convergence warnings where the maximum iterations has been reached but the optimization hasn't converged yet. The speed at which the MLP model can be trained isn't the most optimal since it could take a very long time before finding convergence despite it performing about the same compared to other models. As we had 3 hyper parameters, activation which had 4 different values, hidden layers with 2 values and solver with 2 which made the classifier run multiple times, we couldn't reach the desired number of iterataion so we didn't end up with the optimal result for this classifier.



4.3 -  

Bryce Nichol
- Dataset Preparation & Analysis (Task 1)
- 2.1, 2.2
- Embeddings as Features (Task 3)
- 4.1

Monica Chen
- 2.3.1, 2.3.2
- 2.4 for MNB and DT
- 2.5
- 4.2

Hoda Nourbakhsh
- 2.3.3 to 2.3.6
- 2.4 for MLP, Top-MNB, Top-DT, Top-MLP
- 4.2