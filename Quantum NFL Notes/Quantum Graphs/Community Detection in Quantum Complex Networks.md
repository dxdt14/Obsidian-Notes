[Community Detection in Quantum Complex Networks](https://arxiv.org/abs/1310.6638)
[[Quantum Random Networks]]
[[Symmetries in Quantum Networks]]

## Abstract
- Extension of classical community detection to quantum complex networks
- Define closeness measures b/t nodes and then maximize modularity with hierarchical clutering
	- closeness based on quantum transport probability and state fidelity
## Introduction
- Quantum system simulations rely heavily on partitioning of system into appropriate communities due to complexity in simulating complex systems (i.e. community detection)
- Aim to generate a hierarchical community structure by defining inter-node and inter-community closeness
	- optimum level in the hierarchy is determined by a modularity-based measure
		- Quantifies how good a choice of communities is for the quantum network vs. randomized version of the network
- Backbone of quantum comm. detection similar to classical methods but closeness and modularity functions are very unique to quantum properties
	- Coherent transport between communities
	- Change in the states of individual communities during coherent evolution
## Community Detection
- Community detection: partitioning of a set $\mathcal{N}$ into *non-overlapping* and *non-empty* subsets $\mathcal{A}, \mathcal{B}, \mathcal{C},\dots \subset \mathcal{N}$ called communities that cover $\mathcal{N}$ 
- They define optimality in terms of the quantum equivalent of stochastic random walks (i.e. quantum walks)
	- A measure used to quantify the quality of a community partitioning choise is modularity $Q:= \frac{1}{2m}\text{tr}\{ C^TBC \}$, $m=\frac{1}{2}\sum_{i}k_{i}$ is the total weight of connections, $B$ is the modularity matrix with elements $B_{ij}=A_{ij}-\frac{k_{i}k_{j}}{2m}$, $C$ is the community adjacency matrix
- For quantum networks there is not natural adjacency matrix so for modularity we use $A_{ij}=c(i,j), i\neq j$.
- NMI (normalized mutual information) often used to measure mutual dependence of 2 community partitionings
## Quantum Community Detection
- The state of a quantum system is described in terms of Hilbert Space $\mathcal{H}$ spanned by complete orthonormal set of basis states $\{ \ket{i} \}_{i\in \mathcal{N}}$ . 
	- Each basis state $\ket{i}$ can be associated with a node $i$ in a network
- Thus, partitioning of nodes into communities $\iff$ partitioning $\mathcal{H}=\bigoplus_{A\in X}\mathcal{V}_{A}$ into mutually orthogonal subspaces $\mathcal{V}_{A}=\text{span}_{i\in A}\{ \ket{i} \}$ 
- Possible optimality objectives
	- identify a partioning into subspaces in which inter-subspace transport is small
	- state of the system remains relatively unchanged within each subspace
- They focus analysis on isolated quantum system governed by Hamiltonian $H$.
	- $$H=\sum_{ij}H_{ij}\ket{i} \bra{j} $$
- $H_{ii}$ denotes energy of state $\ket{i}$ 
- If $\ket{i}$ corresponds to a particle localized at a spatially distinct node $i$, the Hamiltonian describes a spinless single-particle walk
	- Energy landscape give by the diagonal elements
	- transition amplitudes by off-diagonal elements
- Any quantum evolution can be viewed in this picture $\implies$ scenario is general
### Inter-community transport
- In classical networks, community detection is often based on flow of probability thorugh network during classical random walk
	- Try to minimize probability flow/transport between communities
- Natural approach to quantum comm. detection is to consider flow of probability during a continuous-time quantum walk and see *change* in the probability of observing walker w/in each comm
	- $$ T_{x}(t) = \sum_{A\in X}T_{A}(t)=\sum_{A\in X} \frac{1}{2}|p_{A}\{ \rho(t) \} - p_{A}\{ \rho(0) \}| $$
		- $\rho(t)=e^{-iHt}\rho(0)e^{iHt}$ 
		- $p_{A}\{ \rho \}=\text{tr} \left\{  \prod_{A}\rho  \right\}$
		- $\prod_{A}=\sum_{i\in A}\ket{i}\bra{i}$ is the projector onto the $A$ subspace
- Can then define a closeness function based on $T_{X}(t)$.
### Intra-Community fidelity
- Can also define a closeness measure based on the change in projection of the quantum state in the community subspaces using squared fidelity.
