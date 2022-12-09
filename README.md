# Predicting learning difficulties in ASD patients

## Data
The project was developed using data available at the following web site : https://www.kaggle.com/datasets/uppulurimadhuri/dataset
This dataset includes 1985 patients with Autism Spectrum Disorder (ASD) with information on 28 variables 

## Project description
Announcement: this is my first coding project

Project date : November-December 2022

We used RStudio application for the project, version : 2022.11.0-daily+222
The project was run on MacBook Pro 2017 with Monterry version 12.1 

The goal was to create a predictive model using the data to predict the presence of learning disorder in this population
We wanted to use simple demographic variables that any family member knows (age, sexe, ethnicity, presence of ASD in the family) and combine with the results 
of a 10-question test called Autism Spectrum Quotien (ASQ) available online or at the general docrtor's office to detect learning disorder in the ASD population 

After removing unwanted data for the model, we created a neuronal network with the neuralnet package in R and we fitted 30 different neuronal networks using the keras package. Then, we calculated the sensitivity, specificity and accuracy of each model to compare them.

## Challenges
2 challenges we had during the project : 
1) Firslty, the precision curves for some of the models were very chaotic telling us the model was loosing precision for a brief period of time. We observed that this was most frequent with networks with more nodes. One of the possible explanation is that the batching was originally done sequentially instead of randomly. This was adjusted in the second version (V2).
2) The models were all very performant in terms of accuracy with results between 90 and 95% for all models. One of the explanation was the use of the ASQ score without looking firslty at its relation with learning disorder. At the end of the project, in an attempt to explain the "too-good-to-be-true" performance of our models, we plotted the relation between the two and it is easy to see that all the patients with a score of 2-10 had a learning disorder. 

## Explanations 
Few explanations about some decision we made during the project 
1) Normalization : It is very common to normalize the data before using it in neuronal networks. We decided not to do it as most of the data used where binary (No = 0, Yes = 1).
2) Imputing missing data: We decided to impute missing data with most frequent for categorial data and mean/mode for continuous data. They looked like they were missing at random. We could have simply deleated the patients with missing data as they represent less than 2% of the data and that we did not even use variables with missing data. We decided to impute the data mainly to practice doing so in a coding project and because we thought it would not have a big impact on variance as it was less than 2% as stated before. 

## Content
1) Code R : the first version of our project including only the best model 
2) Code R FittingModels: the first version of our project including the total 30 models
3) Code R V2 : the final version with addition of random sampling in the model fitting 
4) Code R FittingModels V2: the final version with addition of random sampling in the model fitting 
5) README file

## License 
No License 
