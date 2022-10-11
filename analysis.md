1. Looking at the "GoEmotion by Emotion" graph, we can see that the data is unbalanced. Over 50000 data points are marked as neutral, whereas most other emotion labels have less than 10000 data points. For sentiments, the data is unbalanced, but less so. We can see that positive and neutral emotions are around a third of the total dataset, however abiguous counts for only ~11% of the dataset. As a result, we need to be careful about which metrics we use. If we use only accuracy to evaluate the performance of our models, we could run into issues. For example, a model that labels everything as 'neutral' could have a relatively high accuracy. Since this is something we want to avoid, we should use a different metric such as precision, recall, or F1 score.
2. 
3. 

Bryce Nichol
- Dataset Preparation & Analysis (Task 1)
- 2.1, 2.2
- Embeddings as Features (Task 3)
- 4.1
