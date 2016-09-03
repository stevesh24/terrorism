# terrorism

This analysis uses the Globl Terrorist Database (http://www.start.umd.edu/gtd/) 
to attempt to build a model to predict the terrorist group from the features
present in the database.

The original file (gtd1993_0616dist.xlsx) has 156772 entries (rows) and 138
columns. The dataset is described in Codebook.pdf.

After preprocessing (described in preprocessing.ipynb, with rationale
described in rationale.ipynb) there were 38251 entries and 35 features. The 
outcome to predict was the terrorist group name (gname), which after 
preprocessing had 63 unique names, each of which had at least 150 entries.

Random Forest (RandomForest.ipynb) and Gradient Boosting (GradientBoosting.ipynb)
classifiers were fit to the dataset, with the entries comprising the test set and
the other half comprising the training set. The best result for the Random Forest was
given by a model with 10 features, with mean accuracy, test = 0.8683 and mean 
accuracy, training = 0.98068.  Gradient Boosting (with default parameters except
for n_estimators = 200 and max_depth = 5) performed slightly better, with 
accuracy test = 0.91562	and accuracy training = 0.99885.

List of files:


