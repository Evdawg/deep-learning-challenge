# Supervised Learning Challenge
Module 21 Challenge: Supervised learning of credit risk classification data.

Graded __/100


# Report:
## Overview:
	This project applied machine learning to attempt to predict successful venture projects for investment. The funding applicant data analyzed is hypothetical as this project is to practice deep learning methods.

## Results:
---

#### Model 1:
##### Data Preproccessing:
- Target variable: "IS_SUCCESSFULL" column. I.E. whether or not the funded project was successful.
- Features variables: All data columns except for application identifier columns of "EIN" and "NAME" were inputted as features.
- Removed variables: "EIN" and "NAME" data was removed for anonymization of investment funding data.


##### Compiling, Training, and Evaluating the Model:
- Number of neurons, layers and activation functions was 14, 3, 1 respectively.
	- There were three layers with 8, 5 and 1 neurons respectively. 
	- A single activation function, "relu" was used for the hidden layers. The output activation funciton was "sigmoid."
	- These parameters were arbitrarily selected as a starting points for the model.

- The model_1 was not able to achieve target performance of 75% accuracy. This first model was 73% accurate.
- To increase model performance, keras-tuner methods were applied to iterate through model hyperparameters to output the top performing model input paraemeters. See "Model Optimization" below for results.


##### Model Optimization:
	- Model 2 trial 1 used keras-tuner methods to automatically search for the best model hyperparameters.
		- Activation functions trialed were 'relu','tanh', and 'sigmoid'
		- Layers were trialed in range of 1 to 6.
		- Neurons per layer were trialed in ranges of 1 to 10.
Model 2 initial tuner optimization results: 73.3% accuracy. Did not meet 75% accuracy target.

	- Model 2 trial 2 used new Layer and Neuron parameter ranges for optimization trials:
		- Layers were trialed in range of 7 to 10.
		- Neurons per layer were increased to range of 10 to 15.
Model 2 trial 2 optimization results: 73.5% accuracy. Did not meet 75% target.
	

	- Model 2 trial 3 repeated initial model 2 tuner optimization except with reduced dataframe columns.
		- Two arbitrary data columns were dropped prior to repeating model 1 trial 1 methods.
Model 2 trial 3 optimization results: 73.2% accuracy. Did not meet 75% target.


## Summary:
---
Model optimization attempted to test multiple ranges of layer and neurons input into the model.
Increasing the amount of layers and neurons in model 2 optimization trials did not significantly improve model accuracy.

A third trial was attempted with a reduced input DataFrame. This DataFrame arbitrarily dropped columns "STATUS" and "SPECIAL_CONSIDERATIONS" to test if reduced data would increase model accuracy.
This third trial did not increase in prediction accuracy.

---

Sources:

[1] edX Boot Camps LLC. Module 21: Day 2 activity 6: getting_real_solution.ipynb

[2] Model optimization:
	edX Boot Camps LLC. Module 21: Day 2 activity 4: auto_optimization_solution.ipynb
	