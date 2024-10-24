[Rethinking Kullback-Leibler Divergence in Knowledge Distillation for Large Language Models](https://arxiv.org/abs/2404.02657)

## Abstract
- KL divergence widely used in knowledge distillation to compress LLMs
- Conventionally thought that reverse KL divergence (RKL) is "mode-seeking" so it is preferable over forward KL divergence (FKL) which is "mean-seeking"
- Actually, neither mode-seeking nor mean-seeking properties manifest in knowledge distillation for LLMs
- Both RKL and FKL converge after sufficient number of epochs
	- RKL focuses on tail part of distributions while FKL focuses on the head part at the beginning epochs
- Proposes Adaptive KL divergence (AKL)
## Intro
- Look at [[Distilling the Knowledge in a Neural Network]] for knowledge distillation problem in general
- vanilla KD Method (proposed in [[Distilling the Knowledge in a Neural Network]]) try to train a better "student" model by aligning logits $q_{\theta}$ in the student model with logits $p$ from the teacher model (i.e. the larger model) via FKL
	-  $$ FKL(p,q_{\theta}) = \sum_{z}p(z)\log\left( \frac{p(z)}{q_{\theta}(z)} \right)$$
	- $$ RKL(p,q_{\theta})=\sum_{z}q_{\theta}(z)\log\left( \frac{q_{\theta}(z)}{p(z)} \right) $$
	- Typically (due to asymmetry) $FKL \neq RKL$.
- The mean-seeking and mode-seeking behaviors rely on 2 assumptions
	1. student dist. $q$ is unimodal (e.g. Gaussian)
	2. teacher dist $p$ and student dist $q$ are continuous
- Intuitively, these conditions do not hold for knowledge distillation for LLMs
	- paper proves this theoretically and empirically
## Preliminary 
- Formulation of language generation tasks:
	- aim to generate a response $\textbf{y}=\{ y_{t} \}_{t=1}^T$
	- Traditional FKL aims to align the token generation distributions which can be decomposed into step-wise KL divergence as below
	- $$ \mathcal{J}_{FKL}=\sum_{t=1}^TFKL(p(y_{t}|\textbf{y}_{<t})) = \sum_{t=1}^T\sum_{j=1}^V p(Y_{j}|\mathbf{y_{<t}})\log\left( \frac{p(Y_{j}|\mathbf{y_{<t}})}{q_{\theta}(Y_{j}|\mathbf{y_{<t}})} \right)$$
	- One can also reformulate for RKL as below:
	- $$ \mathcal{J}_{RKL}=\sum_{t=1}^TRKL(p(y_{t}|\textbf{y}_{<t})) = \sum_{t=1}^T\sum_{j=1}^V q_{\theta}(Y_{j}|\mathbf{y_{<t}})\log\left( \frac{q_{\theta}(Y_{j}|\mathbf{y_{<t}})}{p(Y_{j}|\mathbf{y_{<t}})} \right)$$
- Recent work argues that RKL > FKL because FKL is mean-seeking and RKL is mode-seeking
	- ![[Screen Shot 2024-10-23 at 4.52.01 PM.png]]
- However, this assumption relies on the student distribution being unimodal+Gaussian
	- In LLM's with the knowledge distillation setting, this assumption does not hold
- For LLM's FKL and RKL both converge to desired result
	- ![[Screen Shot 2024-10-23 at 5.00.17 PM.png]]
### Difference b/t FKL and RKL for Knowledge Distillation
- The optimizing objective for both $FKL \text{ and } RKL$ is the same (i.e. $q_{\theta} = p$)
- The difference comes from the optimization process
- FKL prioritizes fitting with the head of the distribution
- RKL prioritizes fitting with the tail of the distribution
## Methodology
### Adaptive KL Divergence (AKL)
- adaptively allocates weights to combine FKL and RKL since FKL adapts to head better while RKL adapts to tail better
- Empirically shows the effectiveness of AKL

