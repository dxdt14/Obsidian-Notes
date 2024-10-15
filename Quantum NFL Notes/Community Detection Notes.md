[Community Detection in Graphs](https://arxiv.org/abs/0906.0612)
- **Definition**: internal and external degree 
	$$
		\mathcal{C} \text{ a subgraph of } \mathcal{G}, |\mathcal{C}| = n_c, |\mathcal{G}|=n
	$$ We define the *internal* and *external* degree of $v \in \mathcal{C}$ as $k_v^{int}$ and $k_v^{ext}$ as the number of edges connecting $v$ to other vertices of $\mathcal{C}$ or to the rest of the graph respectively
	- If $k_v^{ext}=0$ then all edges are contained within $\mathcal{C}$ so $\mathcal{C}$ is likely a good cluster
- **Definition**: The *internal degree* $k_{int}^\mathcal{C} \text{ of } \mathcal{C}$ is $\sum_{v \in \mathcal{C}} k_{v}^{int}$.
- **Definition**: The *intra-cluster density* $\delta_{int}(C)=\frac{{\text{\# internal edges of }\mathcal{C}}}{\frac{n_{c}(n_{c}-1)}{2}}$ , the *inter-cluster density* $\delta_{ext}(\mathcal{C})=\frac{{\text{\# inter-cluster edges of }\mathcal{C}}}{n_{c}(n-n_{c})}$ 
- For $\mathcal{C}$ to be a community, $\delta_{int}(C)$ to be "appreciably" larger than the average link density $\delta(\mathcal{G})$ of $\mathcal{G}$ = ratio b/t number of edges in G and mansimum number of possible edges (i.e. $\frac{n(n-1)}{2}$). Conversely $\delta_{ext}(\mathcal{C})$ has to be much smaller than $\delta(G)$.
