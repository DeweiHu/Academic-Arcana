# Non-Invasive Hemodynamics Monitoring System Based on Electrocardiography via Deep Convolutional Autoencoder

## Summary

|   Input   |   Output   |    Model   |    Eval    |
| :-------- | :--------- | :--------- | :--------- |
| Lead II ECG | ABP, CVP, PAP | U-Net autoencoder | R, RMSE, MSE |

The author use a U-Net variant model to generate cardiovascular and cerebral hemodynamic waveforms from lead II ECG. For cardiovascular hemodynimics: the arterial blood pressure (ABP), central venous pressure (CVP), and pulmonary arterial pressure (PAP) are generated while for cerebral, the intracranial pressure (ICP) is synthesized. The results are evaluated with R, RMSE and MSE. 

<p align="center">
  <img src="/hemodynamics/assets/genwave1.png" width="150" />
  <img src="/hemodynamics/assets/genwave2.png" width="150" />
</p>
