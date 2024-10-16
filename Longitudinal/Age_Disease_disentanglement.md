# Disentangling Normal Aging From Severity of Disease via Weak Supervision on Longitudinal MRI

## Summary

|   Input   |   Output   |    Type    |   Model   |    Eval    |
| :-------- | :--------- | :--------- | :--------- | :--------- |
| Longitudinal brain MRI volumes 64x64x64 | feature representations | Encoder | U-Net variation | downstream tasks |

The overview of the method: an encoder projects a pair of MRIs to the latent space resulting in a trajectory vector. The blue for normal control subjects while the red are diseased subjects. They encourage the direction of the vector to be consistent with the age axis for normal controls and the residual of the direction to be consistent with the disease severity direction for diseased individuals.

<p align="center">
  <img src="/Longitudinal/assets/disentangle.png" width="800" />
</p>

## Comments
* Define the age axis with the `normal control subjects` by setting the orientation of the feature vectors to be consistent.

* Project the feature vector of the `diseased subjects` to the age axis and use the time interval between the longitudinal data as constraint to the magnitude.
