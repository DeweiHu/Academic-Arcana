# ECG-FM: An Open Electrocardiogram Foundation Model

## Summary

|   Input   |   Output   |    Type    |   Model   |    Eval    |
| :-------- | :--------- | :--------- | :--------- | :--------- |
| Random subset of 12-lead ECG | feature representations | BERT encoder | CNN+Transformer  | downstream tasks |

<p align="center">
  <img src="/ECG/assets/FM.png" width="700" />
</p>

## Comments
There are three major techniques implemented for pre-training: <br>
`wav2vec 2.0`: wav2vec 2.0 masks spans of CNN latent representations. Each token has a 6.5% probability of being a starting index, where if selected, we mask the subsequent 10 tokens. This results in approximately 49% of a sample’s tokens being masked. The wav2vec 2.0 quantization module is applied to quantize the latent features using two trainable codebools of 320 codes. A codebook diversity loss is applied to encourage more equal usage of codebook entries.
 
`CMSC`: Exploiting how underlying heart function is relatively stable moment-to-moment, CLOCS’ Contrastive Multi-segment Coding (CMSC) is a contrastive objective which we apply between the global representations.
It treats temporally adjacent ECG segments as positive pairs, where the negative pairs are derived from other segments.

`RLM`: Random Lead Masking, an ECG-specific augmentation wherein each individual lead is masked at random with probability p = 0.5. It was demonstrated that by exposing the model to diverse lead combinations during pretraining, it can be robustly finetuned using an arbitrary set of leads.
