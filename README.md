# Using Machine Learning to predict Blood Glucose

## Motivation

  The main purpose of this project was to use machine learning to predict a patient with type 1 diabetes blood glucose.
Complex models that are used in the industry today have the need to receive many inputs, such as carbs and insulin doses.
Those inputs aren't easy to be handled by the patient and have also a good probability of wrong inserts. With that in mind,
a neural network would receive only the blood glucose values from a Continuous Glucose Monitor(CGM - a sensor that shows blood
glucose values for the patient) and show in the output the next values for 30 minutes, preventing the patient from having
to deal with unexpected hipo or hyperglycemia.


## Why LSTM?

LSTM is a certain type of recurrent neural network that will work really well with time series problems. Most of the recurrent
neural networks deal with the problem of long term dependency problem. With the "forget gate layer", this neural network is
able to keep long term data that still important.

## Datasets

The datasets used in this project were generated from UVA/Pandova Type 1 diabetes simulator implemented in Python that you 
can check [here](https://github.com/jxx123/simglucose).

There were used 4 adolescent patients:
  - Patients 7 and 8 were patients without a good blood glucose time in range.
  - Patient 8 was the one used to train the model
  - Patient 1 was a patient with good blood glucose time in range.
  - Patient 10 was a patient with a medium blood glucose time in range.

![alt text](https://github.com/gabriellm1/LSTM_Predicting_BloodGlucose/blob/master/imgs/BGs.png)

## Training and testing

You can check the model training in the [BG_Predictions.ipynb](https://github.com/gabriellm1/LSTM_Predicting_BloodGlucose/blob/master/BG_Predictions.ipynb) file. The code has a lot of comments for your deep understanding.

After training the model with part of patient's 8 data, the resulting model was applied to the rest of the patient 8 data:

#### Patient 08 Test Results - RSME: 15,10

![alt text](https://github.com/gabriellm1/LSTM_Predicting_BloodGlucose/blob/master/imgs/test_result.png)

With the model validated, it was applied to the next three patients:

#### Patient 01 Results - RSME: 5,15

![alt text](https://github.com/gabriellm1/LSTM_Predicting_BloodGlucose/blob/master/imgs/patient01.png)

#### Patient 10 Results - RSME: 5,82

![alt text](https://github.com/gabriellm1/LSTM_Predicting_BloodGlucose/blob/master/imgs/patient10.png)

#### Patient 07 Results - RSME: 15,6

![alt text](https://github.com/gabriellm1/LSTM_Predicting_BloodGlucose/blob/master/imgs/patient07.png)


In the end, the model performed really well. The RSME( Root-Square-Mean Error) was the error variable used to evaluate the model's results.

## Baselines Comparisons

Seeking for a deeper validation, the [Baseline_Comparisons.ipynb](https://github.com/gabriellm1/LSTM_Predicting_BloodGlucose/blob/master/Baseline_Comparisons.ipynb) file shows the application of other predictions
models for the same patients. After running all patient's data for each model, the LSTM model finished with the best performance against all 
others, as you can see in the table below.

![alt text](https://github.com/gabriellm1/LSTM_Predicting_BloodGlucose/blob/master/imgs/baselines.png)


### Project Development

The development of this project was part of a technical initiation research.

Student - Gabriel Monteiro - @gabriellm1

Tutor - Rafael Corsi @rafaelcorsi

Computer Engineering 
Insper 2019-2020
São Paulo, Brazil
