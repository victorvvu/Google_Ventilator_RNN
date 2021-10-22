# Ventilator Pressure Inference 


This respository contains data from a Kaggle competition 
(Ventilator Pressure Prediction) hosted by Google Brain.

## 1. Summary 

##### Problem Statement

The pandemic has shown the current limitations of ventilators because of it's intesenive, manual procedure. 
Ventilators are used as a last resort for clinicians, since it is highly intrusive, to manually pump oxygen into a patient's lung. 


Machine learning can help reduce barrier of developing new methods for controlling mechanical ventilators. 
This will greatly benefit clinicians by giving them an effective instrument and hopefully reduce the burden of them during these times.
 As a result, ventilator treatments may become more widely available to help patients breathe.

##### Technical Overview
The dataset is comprised of numerous time series of breaths. So I decide to construct a RNN with GRU units. LSTM units usually outperform GRU, however
GRUs train faster and have comprable results. 

## 2. Results
Here the GRU actually performed fairly well against LTSM models on Kaggle. Even though the GRU was out performed by LSTM, I was still able to get pretty good results for a simplier model. Unfortunately, I was not able to save my model, since the kernel froze randomly as I was training my model. However, I was still able to submit my results in the competition. 

I performed cross validations 5 times. Below is the plotted loss fucntion, on one fold


![Loss Function](https://github.com/victorvvu/Google_Ventilator_RNN/blob/main/data_set_imgs/fig%20(3).jpg?raw=true)

Here is the learning rate plotted


![Learning Rate](https://github.com/victorvvu/Google_Ventilator_RNN/blob/main/data_set_imgs/fig2%20(1).jpg?raw=true)

  
## 3. Data Description

- id - globally-unique time step identifier across an entire file

- breath_id - globally-unique time step for breaths

- R - lung attribute indicating how restricted the airway is (in cmH2O/L/S). Physically, this is the change in pressure per change in flow (air volume per time). Intuitively, one can imagine blowing up a balloon through a straw. We can change R by changing the diameter of the straw, with higher R being harder to blow.

- C - lung attribute indicating how compliant the lung is (in mL/cmH2O). Physically, this is the change in volume per change in pressure. Intuitively, one can imagine the same balloon example. We can change C by changing the thickness of the balloon’s latex, with higher C having thinner latex and easier to blow.

- time_step - the actual time stamp.

- u_in - the control input for the inspiratory solenoid valve. Ranges from 0 to 100.

- u_out - the control input for the exploratory solenoid valve. Either 0 or 1.

*Target Variable*
- pressure - the airway pressure measured in the respiratory circuit, measured in cmH2O.

  
## 4. Libraries

- Keras
- Optuna
- sklearn
- pandas
- numpy
- pandas 
## 5. References

https://www.kaggle.com/c/ventilator-pressure-prediction/data
