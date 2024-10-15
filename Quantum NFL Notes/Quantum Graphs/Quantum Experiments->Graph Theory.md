[Graph Theory -> Quantum States Paper](https://arxiv.org/abs/1812.09558)
builds off [[Original Quantum Experiments -> Graph Theory paper]]
## Abstract
- Exploits connections between graph theory and quantum experiments to give procedure for creation of plethora of entangled quantum states
- May help me draw connections between entangled "ground truth" state and community detection
	- My current formulation:
			$U: H^x \to H^y$
			$D: H^y \otimes H^R \to H^x \otimes H^R$
			$D\ket{\varphi}$= "generated graph with entangled ground truth"
			$\ket{\varphi}\in H^y\otimes H^R=$ "ground truth"$
			Want to learn $U$ s.t. $\ket{\tilde{\varphi}}\bra{\varphi}=1$, where $\ket{\tilde{\varphi}}=(U\otimes \mbb{I}_R)D\ket{\varphi}$ 
## General Notes
- [Another paper abt quantum->graphs](https://arxiv.org/abs/1705.06646) notes: [[Original Quantum Experiments -> Graph Theory paper]]
- Translate question about the construction of a quantum state into a question about existence of graph w/ certain properties
	- ![[Screen Shot 2024-10-14 at 10.49.17 PM.png]]

- Greenberger-Horne-Zeilinger (GHZ) states are essentially maximally entangled states in d dimensions
	- $$\ket{GHZ_n^d} = \frac{1}{\sqrt{d}}\sum_{i=0}^{d-1}\ket{i}^{\otimes n}$$
- Following the procedure laid out in the figure below, one can correspond the quantum state with a sum of the perfect matchings of the corresponding graph
	- ![[Screen Shot 2024-10-14 at 10.49.36 PM.png]]
## Conclusion
- Classifies a subset of entangled states with a graphical interpretation
- Could help as if I am able to restrict my problem to states that have this sort of graphical interpretation then I could possibly do community detection on the graph rather than on the entangled state.
$\newcommand{\op}[2]{|#1\rangle\langle #2|}\newcommand{\ip}[2]{\langle #1| #2\rangle}\newcommand{\mbb}{\mathbb}$












