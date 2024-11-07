# Constraints for foundation model training

The foundation model serves as a mapping function from the high dimensional data distribution to a low dimensional latent representation that can be used for any downstream tasks. Based on the accessibility of metadata, the training can be either self-supervised or semi-supervised.

### Self-supervised constraints

The following constraints can be considered solid by using only the waveforms.

* `Temporal consistency`: Suppose the input ECG signal is in shape (sequence_length, num_leads) = (5000, 12). Based on the fact that the pathological properties should exist in every single cardiac cycle, the latent representation should be consistent for ECG segment (t1:t2, 12) and (t3:t4, 12) where the time interval is identical (i.e., t2-t1 = t4-t3).

* `Reconstruction`: To ensure the latent representations contain all the features in the ECG, they should be able to be reconstructed to the original ECG signal.   

* `Masked leads`: Intuitively, we can assume that the encoded latent vector represents the moving pattern of a specific heart. The 12-lead signals are observations from different angles. However, such latent representation should be consistent even though some observations are missed. Therefore, we propose to randomly dropout a few leads in the input while the feature space remain unchanged. 


### Semi-supervised constraints
