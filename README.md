# Reddit-Comments-Classification
A set of different models to predict the category of subreddit comments and obtaining their accuracies using 5-fold cross validation.

In this project, first we read the test and training data. Because we used Google Collaboratory framework for this project, we uploaded the test set and train set on Google drive and read the files from Google Drive. You can change the path given in the code with your files' path. Now we explain the functions breifly and after that we explain how to run the code.

The data is a balanced dataset of subreddit comments categorized into 20 classes. The data is provided in CSVs, where the text content of the comment is enclosed in quotes. Each entry in the training CSV contains a comment ID, the text of the comment, and the name of the target subreddit for that comment. For the test CSV, each line contains a comment ID and the text for that comment.

In the Comment_Classification.ipynb we have a class "Models". 

1 --- In this class we have preprocessing_data_xtrain and preprocessing_data_xtest functions that preprocess the comments in training set and comments in test set respectively. 
2 -- We have ensemble_method() that trains the voting classifier method and returns the labels that are results of prediction.
3 --  fit_predict_data(modelname) takes the model name as input ("nb": multinomial naive bayes, "rforest": random forest, "knn": KNN,"dtree": Decision tree, "svm": SVM, "reg": Logistic regression) that returns the labels that are results of prediction.
4--cross_validation_ensemble(). this function perform 5-fold cross validation on voting classifier and prints the accuracy.
5-cross_validation(modelname). it takes modelname as input ("nb": multinomial naive bayes, "rforest": random forest, "knn": KNN,"dtree": Decision tree, "svm": SVM, "reg": Logistic regression) and print the accuracy of 5-fold cross validation for the given model.


HOW TO OBTAIN THE RESULTS:
In order to obtain the results, first we initialize the Models class with x_train, y_train and x_test which are training set comments, training label set, test comments set respectively. Then we run the preprocessing_data_xtrain and preprocessing_data_xtest functions to clean and preprocess the comment sets. Then if we want to retrieve the predicted label set for test comments set, we run the function fit_predict_data(modelname) with the desired modelname and the output is the predicted label set then we can save the result in a CSV file by the corresponding cell in the code (you can find it by its title of the cell). If we want to obtain cross validation accuracy, after running preprocessing_data_xtrain and preprocessing_data_xtest, we run cross_validation(modelname) with the desired model name.

If we want to use Ensemble methods, for obtaining predicted labels of test set, first we run preprocessing_data_xtrain and preprocessing_data_xtest , we run ensemble_method() function. we can save the result in a CSV file by the corresponding cell in the code (you can find it by its title of the cell). 
If we want to obtain cross validation accuracy of the voting classifier, after running preprocessing_data_xtrain and preprocessing_data_xtest, we run cross_validation_ensemble(). 
