[Complex Quantum Networks: A topical review](https://iopscience.iop.org/article/10.1088/1751-8121/ad41a6/meta)

## Introduction
- nothing much important

## Basics of Quantum Mechanics
- A bunch of basic quantum stuff
- If a system is in a state $\ket{\psi(t)}$ at time $t \in \mathbb{R}$ and its Hamiltonian is $H$ then $i \frac{\partial}{\partial t}\ket{\psi(t)} = H\ket{\psi(t)}$ $\implies$ $\ket{\psi(t)}=e^{-iHt}\ket{\psi(0)}$ 
- Hamiltonian is also hermitian
	- So eigenvalues are real and eigenvectors corresponding to diff eigenvectors are orthogonal
- $\braket{ \psi | \varphi_{i} }\braket{ \varphi | \psi } = p_{\lambda_{i}}$ can be interpreted as outcome probabilities where $\lambda_{i}$ corresponds to possible energies of the system
	- smallest eigenvector corresponds to ground state
- 

## Basics of Network Theory
- Continuous time quantum walks (CTQW) often use an adjacency matrix as their Hamiltonian
- Laplacian matrix $L = D-A$ wher $D$ is the diagonal matrix where diagonal elements are the degrees of the nodes, $A$ is the adjacency matrix is also often used as the Hamiltonian for CTQW
- Definition for the Laplacian for the classical random walk is $\hat{L}=\mathbb{I}-D^{-1}A$ or sometimes $\tilde{L}=D^{-1/2}LD^{-1/2}$ 
- Random Graphs: draw each possible edge of the graph with probability $p$.
### Complex Networks
- Complex Networks live between regular square lattices and completely random networks where each pair of nodes is connected with the same probability
- *Scale-free Networks*: networks with degree distribution $P(k) \simeq Ck^{-\gamma}$, $\gamma \in (2,3]$, $k\gg 1$, $C$ constant
	- In these networks second moment of the degree distribution diverges as size $\to \infty$ but average degree remains constant $\implies$ major variations in node degrees
- Scale-free networks largely classified in two classes of models: non-equilibrium growing models, and maximum entropy models
- Ubiquitous property of real complex networks is their modular structure (i.e. it can be decomposed into communities of nodes more densely connected among themselves than with the rest of the network)
- The Erdos-Renyi (ER) model is often used as a *null* model to compare your comm. detection results to because it is a random graph where every possible edge is assigned equal probability
	- Degree distribution of ER approaches Poisson
## Quantum Dynamics in networks
- A multipartite quantum system can be dependent from a graph $G$ describing their physical (pairwise) interactions when the Hamiltonian $H$ is determined by $G$ and possible some additional parameters (i.e. $H = H(G, \dots)$)
- Provides a lot of applications (doesn't seem strictly relevant to my research)
## Network representation of quantum systems
### Networks for taming quantum complexity
- Assumes that a quantum system can be represented as a network of the form $G = G(\mathbf{M}, \mathbf{H}, \mathbf{t}, \mathbf{\rho_{0}})$ where $\mathbf{M}$ can indicate a set of measurements, $\mathbf{H}$ a set of relavant Hamiltonians, $\mathbf{t}$ a set of relevant interaction times and $\rho_{0}$ a set of initial states.
### Applications and examples
#### Network description of states
- Networks can be used as a way to describe a quantum state
- Encode pairwise correlations in the weights of the links
- Example of such a networks
	- $$ \mathcal{I}_{ij} = \frac{1}{2}(S_{i}+S_{j}-S_{ij})=\frac{1}{2}(-\text{Tr}(\rho_{i}\log \rho_{i})-\text{Tr}(\rho_{j}\log \rho_{j})+\text{Tr}(\rho_{ij}\log \rho_{ij})) $$
	- where $\mathcal{I}_{ij}$ is the link weight between qubits $\ket{i}$ and $\ket{j}$ and $S_{i},S_{j}S_{ij}$ are the marginal von Neumann entropies
- Clustering in these mutual information networks can give insights into interesting quantum phenomena
## Quantum algorithms for network inference
### Quantum inference of networks
- There has been a lot of attention on probing network topology using quantum random ralks
- [[Community Detection in Quantum Complex Networks]] defines a community detection algorithm where similarity between nodes are based on quantum transport probability and state fidelity
- Alternative approach is to use embeddings generated from the eigenvectors of the magnetic Laplacian
	- Magnetic Laplacian is a complex valued Hermitian variant of the Laplacian that captures non-trivial mesoscale networks structures
	- Can capture community structure in directed networks and detect cyclic patterns of connections
	- Read [[Magnetic eigenmaps for community detection in directed networks]], [[Discrete magnetic Laplacian]], [[Directed networks Laplacians and random graph models]], [[Characterization and comparison of large directed networks through spectra of the magnetic Laplacian]]