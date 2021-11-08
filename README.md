# Neural Network Charity Analysis

## Overview
The purpose of this analysis was to determine if we can reliably predict the liklihood of applicant success if funded by Alphabet Soup using a neural network. Using the data from previously funded applicants, we will determine which data is useful for a neural network and process it to fit the model.

## Results

### Data Preprocessing
After reviewing the raw data, the "IS_SUCCESFUL" column was determined to be the target, and it was already in a numerical binary format, so it required no further pre-processing. "EIN" and "NAME" are unique to each application and cannot provide any predictive usefulness, and were removed prior to running the model. "APPLICATION_TYPE", "AFFILIATION", "CLASSIFICATION", "USE_CASE", "ORGANIZATION", "STATUS", "INCOME_AMT", "SPECIAL_CONSIDERATIONS", and "ASK_AMT" will all be features for the model to evaluate. The feature data that is in string format needs to be binned and encoded prior to running the model.<br/>
Binning:
<img src= "https://raw.githubusercontent.com/AlexisBurton/Src-images/master/19/Binning.png">
Encoding:
<img src= "https://raw.githubusercontent.com/AlexisBurton/Src-images/master/19/Encoding.png">

### Compiling, Training & Evaluating the Model
After preparing the data, it was time to define, compile and train the model, creating checkpoints to save the model weights every 5 epochs.
<img src= "https://raw.githubusercontent.com/AlexisBurton/Src-images/master/19/Define.png">
<img src= "https://raw.githubusercontent.com/AlexisBurton/Src-images/master/19/Train.png">

## Summary
After running the initial model, we tried to optimize the model in order to improve accuracy to over 75%. The first optimization attempt removed "AFFILIATION" and "INCOME_AMT"  as potentially noisy data. It provided a modest improvement from 72.6% to 73.3%. The second optimization attempt used the reduced data from the first optimization, but added a hidden layer of neurons. With an accuracy of 73.2%, the second optimization had no real effect. The third optimization tried grouping the "ASK_AMT" values into ranges, but ultimately decreased the accuracy of the model.