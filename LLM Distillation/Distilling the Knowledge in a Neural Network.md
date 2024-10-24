[Distilling the Knowledge in a Neural Network](https://arxiv.org/abs/1503.02531)
## Abstract
- A simple way to improve performance of an ML algorithm is to train many models on the same data and then average
	- Very cumbersome
- Has been shown that you can compress knowledge in an ensemble into a single model
## Introduction
- very simple method may be to just try to match output probability dist of smaller model to prob dist of larger model through taking means of the output of the smaller model prob dist and larger model prob dist as you train
	- When differences between probabilities in the dist are very small can be very hard
- Distillation: raise the temperature of the final softmax until the cumbersome model produces a suitable soft set of targets. Then use the same high temperature when training the small model to match these soft targets
## Distillation
- softmax: $q_{i} = \frac{\exp\left( \frac{z_{i}}{T} \right)}{\sum_{j}\exp\left( \frac{z_{j}}{T} \right)}$ 
- $T$ is typically set to 1 but for higher temperatures a softer probability distributions is created
- The distilled model is trained on a transfer set using a soft target distrubtion for each case int he transfer set which is produced by using a larger model with a high temperature in the softmax
	- The same high temp is used when training the distilled model and after the temp of the distilled model is set to 1

