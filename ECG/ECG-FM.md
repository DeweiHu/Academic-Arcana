# ECG-FM: An Open Electrocardiogram Foundation Model

## Summary

|   Input   |   Output   |    Type    |   Model   |    Eval    |
| :-------- | :--------- | :--------- | :--------- | :--------- |
| Random subset of 12-lead ECG | feature representations | BERT encoder | CNN+Transformer  | downstream tasks |

## Comments
There are three major constraints implemented for pre-training: <br>
`wav2vec 2.0`: <br>

`CMSC`: Exploiting how underlying heart function is relatively stable moment-to-moment, CLOCS’ Contrastive Multi-segment Coding (CMSC) is a contrastive objective which we apply between the global representations.
It treats temporally adjacent ECG segments as positive pairs, where the negative pairs are derived from other segments.

`RLM`: Random Lead Masking, an ECG-specific augmentation wherein each individual lead is masked at random with probability p = 0.5. It was demonstrated that by exposing the model to diverse lead combinations during pretraining, it can be robustly finetuned using an arbitrary set of leads.
