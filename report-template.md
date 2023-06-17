# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### NAME HERE

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
I realized I had to convert my submission into a csv file before submitting. To do that, I created a dataframe and used the to_csv method to write the submission file. I also passed in the index as False to avoid pandas from adding another coulumn to my csv files. 

### What was the top ranked model that performed?
According to the leaderboard, the best performing model is the "WeightedEnsemble_L3" model which has the highest "score_val" of 52.758870. This proved to be the optimal model on the validation data.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
-During rainy days, the demand for bicycles were less i.e summer 2011 to summer 2012 had a record of decreasing demand. However, during sunny day there were higher demands of bicycles.


### How much better did your model preform after adding additional features and why do you think that is?
The score went reduced from 1.81053 to 0.68140 after adding new features. This is because the more features that were added, the better the perfomance of the model, the better the accuracy. I also explicitly stated that the data type was categorical so AutoGluon knows that the features do not represnt numerical values.


## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
The improvement made to the model was significant as the overall performance improved as seen below:

Model score : [52.758870, 30.260269, 36.791013] Kaggle score : [1.81053, 0.68140, 0.47099]

### If you were given more time with this dataset, where do you think you would spend more time?
I think it would make more sense to check the correlation between each features and see how it will improve the overall performance of the model.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.

| model         | hpo1          | hpo2        |  hpo3         |   score  |
|---            |---            |---          |---            |---       |
|  initial      |  default vals | default vals|  default vals | 1.81053  |
| add_features  |  default vals | default vals|  default vals | 0.68140  |
| hpo           |  NN epochs: [10], activation: ['relu',
'softrelu'", "'tanh'], layers:[[100],
[1000], [200, 100]. [300, 200, 100]]           |GBM
num_boost_round:
[100] no. of leaves
[26, 66]                                        | default vals   | 0.47099|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score.png](project1/cd0385-project-starter/project/model_train_score.png)
### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](img/model_test_score.png)
project1/cd0385-project-starter/project/model_test_score.png

## Summary
''' I began the project by doing expoloratory data analysis (EDA) and since Autogluon automates the process of training and selecting models, it saved me time on model selection and tuning. 
Usually when tasked with a project like this, I train the models independently and use a heatmap to compare and make inferences on what the optimal model is. However, using AutoGluon helped train all the models and ranked all the models according to their perfomance. 
I was able to save time and still get enough information about each model and their proceesing times even. 

To further improve model performance, I would tune my hyperparameters(which we already did in the latter part of the project) and also increase the time budget by allocating more time for the search process. This might improve the overall model performance '''