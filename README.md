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
Y_in.csv -	Outcome (gname), 38251 entries, as 1 column of 63 unique names. Each name has at least 150 entries.
Y_out.xlsx - Outcome (gname),  38251 entries, as 63 columns, Each name has at least 150 entries.
final_data.xlsx -	Feature set, 38251 entries and 35 features. Feature list in final_data_list.xlsx
preprocessing.ipynb	-Code and documentation describing preprocessing
data_summary.xlsx	- A count for all columns in original data set (globalterrorismdb_0616dist.xlsx)
final_data_list.xlsx - A list of the final set of 35 features in final_data.xlsx
weaptype recode.xlsx - A list of the codes for the recoding of WeapRecode1 and WeapRecode (found in step #5 of preprocessing.ipynb and rationale.ipynb)
days.jpg - A figure giving the original distribution of days in globalterrorismdb_0616dist.xlsx
months.jpg - A figure giving the original distribution of months in globalterrorismdb_0616dist.xlsx
rationale.ipynb -Code and documentation describing the rationale and some of the descriptive stats for the preprocessing
gradientboosting.ipynb - Code and documentation describing the gradient boosting and the results
randomforest.ipynb - Code and documentation describing the random forest and the results
GB max depth.jpg - Figure giving summarizing the tuning of the Gradient Boosting wrt max_depth
Codebook.pdf - Codebook from http://www.start.umd.edu/gtd/

