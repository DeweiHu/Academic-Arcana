# wav2vec 2.0: A Framework for Self-Supervised Learning of Speech Representations

## Summary

|   Input   |   Output   |    Type    |   Model   |    Eval    |
| :-------- | :--------- | :--------- | :--------- | :--------- |
| Sequential data | feature representations | BERT encoder | CNN+Transformer  | downstream tasks |

## Model architecture
<p align="center">
  <img src="/building blocks/assets/wav2vec.png" width="600" />
</p>

# Comments
There are two major components of this model: <br>
`Vector quantization`: the feature representations extracted by the CNNs are quantized by G codebooks. Using multiple groups instead of a big one significantly increase the memory and computation efficiency while providing decent amount of redundancy and flexibility. The codebooks are initialized with random noise and jointly trained in the pretraining process. To enable the gradient passing through the basis selection, the author used the **Gumbel Softmax**. <br>

`Contrastive Loss`: some feature vectors are masked (here masking means replace the vector with a embedded vector). Then try to reconstruct the quantized version of this missing feature in the transformer output. This output vector should be close to the corresponding quantized vector while far apart with the distractors.

 
