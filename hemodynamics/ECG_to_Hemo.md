# Non-Invasive Hemodynamics Monitoring System Based on Electrocardiography via Deep Convolutional Autoencoder

## Summary

|   Input   |   Output   |    Type    |   Model   |    Eval    |
| :-------- | :--------- | :--------- | :--------- | :--------- |
| Lead II ECG | ABP, CVP, PAP | Generative | U-Net autoencoder | R, RMSE, MSE |

The author use a U-Net variant model to generate cardiovascular and cerebral hemodynamic waveforms from lead II ECG. For cardiovascular hemodynimics: the arterial blood pressure (ABP), central venous pressure (CVP), and pulmonary arterial pressure (PAP) are generated while for cerebral, the intracranial pressure (ICP) is synthesized. The results are evaluated with R, RMSE and MSE. 

<p align="center">
  <img src="/hemodynamics/assets/genwave2.png" width="350" />
  <img src="/hemodynamics/assets/genwave1.png" width="350" />
</p>

**Left**: generated waveforms of ABP, CVP, and PAP for (a) normal and (b, c, d) abnormal hemodynamics. <br>
**Right**: arrhythmic ECG predictions for cardiovascular hemodynamics.

Note that the ratio of arrhythmic samples in the training dataset is not mentioned. 

## Comments
Theoratically, the mapping between ECG and hemodynamics can never be perfect since they contain different information. What is the point of doing this instead of do prediction of e.g., pulmonary hypertension directly from ECG? The evaluations are unintuitive.

## Take-aways
Hypertension on ECG: P wave appears later, wider P wave, higher T wave with extended PR intervals, ST segment depression, higher QRS amplitude.
