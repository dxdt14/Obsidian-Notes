[Symmetries in Quantum Networks lead to no-go theorems](https://www.nature.com/articles/s41467-022-28006-3?fromPaywallRec=false)
[[Quantum Random Networks]]
[[Community Detection in Quantum Complex Networks]]
## Abstract
- Symmetries can be powerful in analyzing quantum networks

## Introduction
- A quantum network consists of quantum systems as nodes on specific locations, smoe nodes are connected via links
	- Links correspond to quantum channels 
- The approach in this paper towards characterizing quantum correlations in arbitrary network topologies is based on symmetries
	- e.g. permutation symmetries or invariance under certain local unitary transformations
## Results
### Network Entanglement
- Types of correlations that can be prepared in a network
	- Alice, Bob, Charlie aim to prepare a tripartite quantum state using 3 bipartite source states $q_a,q_{b},q_{c}$ . Parties belonging to a asme source state are sent to different parties of the network i.e. A,B,C s.t. the global state is $\rho_{ABC}=\rho_{c}\otimes \rho_{b}\otimes \rho_{a}$. 
		- Order reversed from other side of equation
	- After receiving the states each party may still apply a local operation $\mathcal{E}_{X}, X\in \{ A,B,C \}$. 
- We get a global state $$ \rho=\sum_{\lambda}p_{\lambda}\mathcal{E}_{A}^\lambda \otimes\mathcal{E}_{B}^\lambda \otimes\mathcal{E}_{C}^\lambda[q_{ABC}] $$
- This formulation can be easily generalized to more parties
- uses local operations and shared randomness (LOSR)
### Symmetries
- $\rho \mapsto U\rho U^{\dagger}=\rho$ for $U \in$ Unitary Symmetric Group
- If $\rho=\ket{\psi} \bra{\psi}$ then $U\ket{\psi}=e^{i\phi}\ket{\psi}$ and $\ket{\psi}$ is an eigenstate of the operator
- For pure states, one can identify directly a certain subspace of the entire Hilbert space that is equipped with a certain symmetry
	- Let $\Pi\ket{\psi}=\ket{\psi}$ denote the projector onto this subspace
	- For mixed states, $\rho=\Pi\rho\Pi$
- Mainly consider 2 types of symmetries
	- symmetry operations of an Abelian group of tensor products of Paulis
	- Permutational symmetry
- Pure states which obey the first symmetry are called stabilizer states (bc states where this pure states is applied stay the same)
- One can observe the properties of the links between nodes in the graph to determine if states are separable or not or determine if the original state can be prepared in a graph.