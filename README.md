# Personalized-Cancer-Diagnosis
Applying various machine learning classification techniques on a dataset which contains around 3.3K datapoints of Gene ( Gene causing cancer ), Variations ( Variations in the architecture of amino acids or variations in protein-protein interactions ) and TEXT ( Medical Literature which will help in classifying the type of cancer) . Here our task is to classify the given datapoint consisting information of Gene and Variation into one of the 9 cancer classes mentioned in the dataset using medical literature
# Case Study Explanation :
Objective: Predict the probability of each data-point belonging to each of the nine classes.
[ 1 ] We have two files, named as 'training_variants' and 'training_text' which contains the whole dataset.
[ 2 ] Reading Dataset :- Lets read and save the data point (gene and variation data) in pandas dataframe(data_variants).
Number of data points : 3321
Number of features : 4
Features : ['ID' 'Gene' 'Variation' 'Class']
   *  ID : the id of the row used to link the mutation to the clinical evidence
   *  Gene : the gene where this genetic mutation is located
   *  Variation : the aminoacid change for this mutations
   *  Class : 1-9 the class this genetic mutation has been classified on
Lets read and save the data point (text data) in pandas dataframe(data_text).
Number of data points : 3321
Number of features : 2
Features : ['ID' 'TEXT']
  * ID : the id of the row used to link the mutation to the clinical evidence
  * TEXT : clinical evidence (text) that human experts/pathologists use to classify the genetic mutations
[ 3 ] Preprocessing of text data:-
  * Stopword removal using nltk library
  * Merged data_variants, data_text into one dataframe
  * Null checking using 'result[result.isnull().any(axis=1)]'
  * Filling the null data 'result.loc[result['TEXT'].isnull(),'TEXT'] = result['Gene'] +' '+result['Variation']'
[ 4 ] Data splitting:- Splitting data into train, test and cross validation (64:20:16)
