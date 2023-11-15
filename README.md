# RandomForest_Image_Prediction
In this project, I've used the Random Forest classifier with parameter fine tuning to achieve maximum accuracy when predicting faces on lfwpeople Dataset
Random forest classifier is a meta estimator, which can be used to fit various decision tree classifiers on different sub-samples of a given data set. Random forest uses averaging to improve accuracy of predictions as well as to control overfitting. There are several parameters we can choose depending on their properties.

The code didn’t execute with the parameter min_impurity_split and therefore the parameter was removed as it was not usable in the given data set. It was able to get an accuracy rate of 0.5428571428571429 in the first attempt with the default parameters
n_estimators : refer to the number of trees in the forest which is an integer and default value is set to 100. Maximum accuracy was obtained when the n_estimator value was set between 84-90.
Criterian : function is used to measure the quality of a split. “gini” is used to measure Gini impurity and the other parameters “log_loss” and “entropy” are both used for shanon gain. Click here for more details of formula. 0.6304347826086957 when entropy is used as criterian which is higher than the accuracy score of 0.6242236024844721 from using ‘gini’ as the criterian which is 0.6242236024844721. further studies to the test results shows that when using ‘entropy’ the precision was 1.0 for several items which seems to be due to overfitting of the test data. Therefore ‘gini’ is used as the criterian to minimise overfitting.

Max_depth: used to define the maximum depth of a tree in Random forest. By defaultthis value is ‘None’, where the nodes are expanded until pure leaves are obtained or min_sample_split value is reached.
Bootstrap: default value is True whether bootstrap samples are used in building trees. False is used in our data set to use whole data set in building trees, which seems to increase the accuracy of algo. Which is 0.5838509316770186 and 0.6521739130434783
Max_features : max features is set to ‘auto’ where max_features=sqrt(n_features).using ‘sqrt’ will give the same results, where other values(‘log2’, None, int, Float) will give a lesser accuracy to given data set. 
Min_sample_split: defines the least number of samples required to split an internal node. Default value is set to 2 and classifier gives the best accuracy when the value is set to 2 or 3 which is 0.6366459627329193
N_jobs : number of jobs running in parallel is defined. It shows an optimal values of 0.6490683229813664 when number is set to 21 and 0.6428571428571429 when set to 4. However, it was unable to find a relation whether the accuracy increases when the number of jobs increases as the accuracy was changed at each running cycle.
Min_sample_leaf: defines the minimum number of samples at a node. Default value is used for our data set which is 1, inorder to maximise the number of leaves.
Features like min_weight_fraction_leaf are not used which will determine the minimum weighted fraction of the sum total of weights required at a leaf node, inorder to allow equal weight at the samples. There are other features which can be enabled and edited by enabling bootstrap. Keeping those values as the default values, an maximum features showed higher accuracy In the facerec dataset. The algorithm was able to get a highest accuracy of 0.6490683229813664 when optimizing the parameters used in the Random forest classifier, but the issue of overfitting data was not overcomed.
Reducing the number of n_components used for PCA seems to increase the accuracy as well as overcome the issue of overfitting. Weighted average accuracy of 0.72 and macro avg accuracy of 0.76 was obtained by reducing value of n_components to 50. 

 increased number of faces used from 70 to 100
n jobs2, n_estimators 200
n jobs=5, estimators 200
