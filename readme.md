In KNN generally why do we use loops?---because by iteratively looping we can observe how the accuracy changes.Some values might overfit the training data , while other might get underfit.
We take a range of values for K like in this we took 1 to 14 so that the we can find the best value of k that fits balance bias , variance ,and the best accuracy on unseen data.


While training and evaluating the models we have put a for loop so that it will iteratively move form 1 to 14  as range(1,15) always take the value starting from 1 and end to 14 only.
for n_nbd in nbd:
    #build the model
    knn=KNeighborsClassifier(n_neighbors=n_nbd)   ---this line create a KNN model
    knn.fit(x_train, y_train) ---this line fits the model for training the data with features and target variables.

train_accuracy.append(knn.score(x_train, y_train))
    test_accuracy.append(knn.score(x_test, y_test)) ---part will store the accuracy score which we had intialize empty list above in the code.


After the loop finishes 1 to 14 and stores all the accuracy scores on the list we will plot all those in a graph ,
the train_accuracy and test_accuracy , try to study the graph and find the value of K
 lets study the graph:
 ----The blue line is the train accuracy starting from 1 to 14 and the orange line is the test accuracy .
 When k=1, train accuracy is high looks like 100percent. and stats gradually decreasing when the k increases.
 the test accuracy from the value of k=1 starts with low, slightly increases and again a down fluctuation.
 We can see highest accuracy is at k=6 and again fluctuation can be seen.
 why we see only the test line for the value beacuse?
   1.The train accuracy in the graph you sent actually refers to the model's performance on a training dataset.This is the data that the model is trained on to learn the patterns that will be used to make predictions on new data. The test line, labeled "test accuracy", shows the model's performance on a separate test dataset. This is important because the training dataset can be memorized by the model, which can lead to overfitting. Overfitting is when a model performs well on the training data but poorly on unseen data . The test dataset helps to identify overfitting because the model has not seen this data before.
   2.In conclusion, both the train and test accuracy lines are important for evaluating a model's performance. The test accuracy line is generally considered to be a more accurate measure of how well a model will perform on new data.

After that we have fit and set:
 the n_neighbors parameter to 6. This parameter determines the number of nearest neighbors to consider when making a prediction for a new data point.

:
trains a KNN classifier with 6 neighbors, then evaluates its performance on both the training data (to understand how well it learned) and the unseen test data (to assess its generalizability).

finally we have make a predciton function for the prediction of outcomes.
Finally, we have load it into the joblib




