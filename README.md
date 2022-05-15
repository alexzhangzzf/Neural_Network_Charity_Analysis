# Neural Network Charity Analysis
## Overview of the analysis
We use machine learning and neural networks to create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup. We use Alphabe Soup's dataset with over 34,000 organizations which received funding to train our model.
## Results
### data Preprocessing
- IS_SUCCESSFUL IS considered the target for my model to predict wether the applicant is successful funded by Alphabet Soup.
- APPLICATION_TYPE, AFFLILIATION, CLASSIFCATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS AND ASK_AMT are considered features for my model.
- EIN and NAME are identification column and are removed from the input data.
### Compiling, Training and Evaluating the Model
#### Initial model
- I used two hidden layers with 8 and 5 neurons with activation model of ReLU for hidden layer and sigmoid funciton for output layer as input data is positive nonlinear for binary classification.
- Model has loss of 55.37% and accuracy of 72.83% so I failed to ahieve the target predictive accuracy of 75%. <br/>
![model](/resources/model.png) <br/>

#### Optimization
- Optimization 1
    - I adjusted the input data by creating more bins for CLASSIFICATION column.
    - More neurons are added to hidden layers (100, 40).
    - Increase epochs from 50 to 250.
    The optimization 1 increased accuracy from 72.83% to 72.98%, loss also increases to 57.40%.<br/>
![opti1](/resources/opti1.png) <br/>
- Optimization 2
    - Because ASK_AMT column is noisy with many outliers shown by box plot so I dropped this column.
    - I changed the neurons to 50 and 20, kept the same epochs number.
    - Tried other activation functions like tanh or sigmoid function for both layers or tried a combination of them but overall results are similar.
    Overall, I tried using different activation functions and dropping a column, but ther results is similar. Accuracy is 72.92%, loss is 55.99%. <br/>
![opti2](/resources/opti2.png) <br/>   
- Optimization 3
    - Kept all the columns.
    - Added third hidden layer
    - Tried more neurons and epochs but the accuracy is lower so I changed back to neurons as (8,5,5) and 50 epochs.
    Overall the accuracy inceased to 733.01% and loss is 55.11%. It increased by 0.2% but failed to achieve target accuracy.<br/>
![opti3](/resources/opti3.png) <br/>  
## Summary
- Adjustment to input data was made. Different activation functions and different number of neurons, epochs and hiddden layers are tried. Optimization increased the accuracy by 0.2% but failed to achieve the target accuracy of 75%. It suggests more neurons and epochs are not necessarily helpful to increase the accuracy as it could cause overfitting.

- Recommandations 
    - More optmization is needed to increase the accuracy of this predictive model. I would recommnad to deep dive into input data to further remove noisy outliers for better predictions. 
    - More activations functions are recommanded to compare with traditional relu like softmax, softplus or selu functions.

 