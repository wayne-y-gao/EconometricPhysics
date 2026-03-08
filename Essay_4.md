# Spacetime as a Joint Filtration I: The Finite Causal-Dependence Network

*Wayne Gao*

*I'm thankful to Claude, Gemini, and ChatGPT for discussing these ideas with me and helping me construct this essay.*

---

## 1. From mixing conditions to micro-foundations

Essay 3 ended with an observation that deserves to be taken seriously: the speed of light is a mixing condition. It defines the support of the dependence kernel — the boundary between regions that can influence each other and regions that cannot. Two events separated by a spacelike interval are statistically independent conditional on their shared causal past; two events within each other's light cones are potentially dependent, with the dependence decaying as the separation grows.

In econometrics, we usually take the index set as given. Time is a line; a cross-section is a set of units; a panel is the product of the two; a network is a graph on nodes. The dependence structure — $\alpha$-mixing coefficients, covariance kernels, filtrations — is studied *on* this pre-existing index set. We never ask where the index set came from.

Physics does the same thing with spacetime. General relativity begins with a smooth four-dimensional manifold, equips it with a Lorentzian metric $g_{\mu\nu}$, and derives the causal structure — the light cones — from the metric. The logical order is: geometry first, causality second, dependence third.

This essay reverses that order. It asks: what if the dependence structure is the primitive object, and geometry is *induced from* it?

But there is a deeper reason to reverse the order, one that the series has been building toward from the start. Essay 1 established that quantum mechanics is the finite-sample DGP: the sieve approximation $\sum_k \alpha_k b_k(x) + \varepsilon$ with irreducible noise. Essay 2 established that general relativity is the population model: the smooth regression function $m(x)$ recovered in the limit $n \to \infty$. Essay 3 identified the GR/QM conflict as a DGP specification problem — the search for a finite-sample process whose population limit is smooth geometry.

If this analogy is taken seriously, then the *real* spacetime — the DGP — should be finite and discrete, not smooth and continuous. The smooth Lorentzian manifold of GR should be the population limit: what you would see with infinite data at infinite resolution. The actual universe, at the Planck scale, should look like a finite stochastic process with local observables and structured dependence — a finite causal-dependence network.

This is not merely a computational convenience. It changes the philosophical burden of the project. Instead of beginning with continuum geometry and asking how randomness enters it, we begin with finite local information, causal accessibility, and dependence, and ask how geometric regularity might emerge. The discrete model is not a numerical approximation to a prior manifold picture; it is the candidate micro-foundation. The manifold is the asymptotic approximation of the discrete reality, not the other way around. Just as CLT is the asymptotic approximation of the sampling distribution of the mean, not the other way around.

The reconstruction chain, stated in full, is:

$$\text{finite DAG + local } \sigma\text{-fields} \;\xrightarrow{\;n \to \infty\;}\; \text{continuum net} \;\Longrightarrow\; \text{dependence cones} \;\Longrightarrow\; [g] \;\Longrightarrow\; g$$

The first arrow is the population limit — the passage from finite DGP to smooth population model. The subsequent arrows are the geometric reconstruction — the recovery of spacetime from the continuum dependence structure. This essay — the first of two parts — develops the finite DGP: the causal graph, the overlapping filtration, and the axiom system. Essay 5 develops the population limit and the geometric reconstruction.

---

## 2. The primitive: a finite causal graph with local observables

The fundamental object is not a metric, not a manifold, not even a continuum causal order. It is a finite directed acyclic graph with stochastic content.

Let $G = (V, E)$ be a finite directed acyclic graph (DAG). The node set $V$ is a finite collection of localized spacetime events — not four-dimensional histories, but discrete spacetime atoms. The edge set $E$ encodes primitive causal links: a directed edge $u \to v$ means that $u$ lies in the immediate causal past of $v$, that direct influence from $u$ to $v$ is admissible in the microscopic specification.

The graph is acyclic because causal loops are excluded at the primitive level. The transitive closure of the edge relation induces a partial order:

$$u \preceq v \quad \Longleftrightarrow \quad \text{there exists a directed path from } u \text{ to } v.$$

This is the discrete precursor of causal order in spacetime geometry.

Now attach stochastic content. To each node $v \in V$, assign a local random variable $X_v$, defined on a common probability space $(\Omega, \mathscr{F}, \mathbb{P})$. The collection $\{X_v\}_{v \in V}$ is the primitive stochastic content of the model — the "data" generated at each spacetime event. This is the DGP: each node produces an observable, and the joint distribution of $\{X_v\}$ encodes the full stochastic law of the discrete universe.

An econometrician will recognize this immediately: it is a random field indexed by a partially ordered set. In panel econometrics, the index set is $\{1, \ldots, N\} \times \{1, \ldots, T\}$ — agents cross time. Here, the index set is a causal graph — events cross causality. The mathematical structure is the same; only the interpretation of the partial order changes.

---

## 3. The overlapping spacetime filtration

Two kinds of information live at each node, and they must be carefully distinguished.

The **local $\sigma$-field** at node $v$ is

$$\mathcal{F}(v) = \sigma(X_v),$$

the information generated by the observable at $v$ alone — the "private signal" produced at that event. This is what is *new* at $v$: the data generated locally, before any accumulation from the past.

The **past $\sigma$-field** at node $v$ is

$$\mathcal{G}(v) = \sigma(X_u : u \in \text{Past}(v)), \quad \text{where} \quad \text{Past}(v) = \{u \in V : u \preceq v\}.$$

This is the total information available at $v$: the $\sigma$-field generated by all observables in the causal past of $v$, including $v$ itself. It captures everything that an observer at $v$ could in principle know, given the causal structure.

The filtration property is immediate:

$$u \preceq v \quad \Longrightarrow \quad \mathcal{G}(u) \subseteq \mathcal{G}(v).$$

Information accumulates along causal chains. An observer further along a causal path knows everything that an earlier observer knows, plus whatever new information was generated in between.

The collection $\{\mathcal{G}(v) : v \in V\}$ is an **overlapping spacetime filtration** — a family of $\sigma$-fields indexed not by a linear time parameter but by the nodes of a causal graph. Unlike a standard time-series filtration $\mathcal{F}_0 \subseteq \mathcal{F}_1 \subseteq \cdots \subseteq \mathcal{F}_T$, which is totally ordered, the spacetime filtration is only partially ordered: two nodes may be causally incomparable, and their filtrations $\mathcal{G}(u)$ and $\mathcal{G}(v)$ are neither contained in each other nor identical.

The word "overlapping" is critical, and deserves emphasis. For any two nodes $u$ and $v$ in the graph, the causal pasts decompose into three pieces:

$$\text{Past}(u) \cap \text{Past}(v) \quad \text{(common past — shared ancestors)},$$
$$\text{Past}(u) \setminus \text{Past}(v) \quad \text{(private past of } u\text{)},$$
$$\text{Past}(v) \setminus \text{Past}(u) \quad \text{(private past of } v\text{)}.$$

The common past generates shared information — events that both $u$ and $v$ have "seen." The private pasts generate information that is unique to each node: the causal influences that reached $u$ but not $v$, and vice versa. This decomposition is the heart of the structure.

In network econometrics, this is exactly the situation studied in models of social learning and strategic interaction on networks: each agent has access to some common information (shared neighbors, public signals) and some private information (their own signal, neighbors unique to them). The correlation between agents' actions is mediated entirely by common information; conditional on the shared past, the private signals are independent. The topology of the network — who shares information with whom, and how much — determines the dependence structure and governs the efficiency of learning and coordination.

The spacetime filtration is the same structure, with a richer interpretation. The "agents" are spacetime events. The "network" is the causal graph. The common past of two events is their shared causal history — the set of events that influenced both. The private pasts are the causal influences unique to each. The dependence between observables at $u$ and $v$ is mediated by their common ancestors; conditional on the shared history, the local innovations at $u$ and $v$ are independent.

This partially overlapping structure is the central object of the essay. It is the discrete analog of the Cauchy-temporal filtration in GR, the time-series filtration in econometrics, and the Haag–Kastler net in algebraic quantum field theory — all at once. But it is richer than any of these, because the *pattern of overlap* between different nodes' information sets is itself the carrier of geometric information. Two nodes with nearly identical pasts are "close" — they share almost all their causal history. Two nodes with completely disjoint pasts are "far" — they have no shared information. The degree of overlap encodes distance, and the shape of the overlap encodes geometry. It is from this structure that spacetime will be induced.

There is a philosophical observation that follows immediately from this structure, and it deserves to be stated explicitly: 

**What is global is the structure, not the information.** 

No single node $v$ has access to the full information of the universe. Its past $\sigma$-field $\mathcal{G}(v)$ captures only what has entered its causal past; everything outside its past cone is informationally inaccessible. Two nodes at spacelike separation have overlapping but distinct information horizons. There is no node — no "God's-eye observer" — whose past contains the entire graph.

What *is* global is the causal grammar: the graph $G = (V, E)$, the overlap pattern $\{\text{Past}(u) \cap \text{Past}(v)\}$, the compatibility relations among local filtrations. The DAG and its structure organize all the local information sets into a coherent whole. But the organization is not itself an information set. It is a law — a set of constraints on how local informations relate to one another.

This distinction — **globality belongs to law and structure; locality belongs to information** — is a natural consequence of the finite-first axioms, but it carries significant weight. It means the natural primitive of the theory is not a single global sample space $(\Omega, \mathscr{F}, \mathbb{P})$ from which local $\sigma$-fields are carved out. It is the family of local filtrations $\{\mathcal{G}(v)\}_{v \in V}$ itself, organized by the DAG's causal order and overlap structure. Any "global" probability space is secondary — a compatibility or gluing construction from the locals, not the starting ontology. In the language of algebraic topology, the natural object is closer to a presheaf of local information structures over a causal network than to a single flat probability space.

In relativity, this is already implicit: the absence of absolute simultaneity means there is no privileged global information frame. In quantum mechanics, it is the lesson of local measurement: no single observation accesses the full state. In econometrics, it is the everyday reality of network data with graph dependence: each unit's filtration is its own, and the "global" dataset is the structured union of overlapping local histories. 

The overlapping spacetime filtration makes this common theme precise and primitive.

---

## 4. Spacelike separation as conditional independence

The first structural distinction in the graph is between comparable and incomparable nodes. If neither $u \preceq v$ nor $v \preceq u$, then $u$ and $v$ are **causally incomparable** — the graph-theoretic analog of spacelike separation.

But causally incomparable does not mean unconditionally independent. This is a subtlety that the partially overlapping structure forces us to confront.

Consider three nodes $w, u, v$ where $w \preceq u$ and $w \preceq v$, but $u$ and $v$ are causally incomparable. The common ancestor $w$ is in the causal past of both — so the past $\sigma$-fields $\mathcal{G}(u)$ and $\mathcal{G}(v)$ both contain $X_w$. They cannot be independent: the shared ancestor induces correlation. Yet there is no direct causal link between $u$ and $v$ — the correlation is entirely mediated by the common past.

This is the same situation an econometrician encounters in causal inference: confounding by common causes. Two variables can be correlated without either causing the other, because both are caused by a third. The correlation is "spurious" in the Granger/Pearl sense — it disappears upon conditioning on the common cause.

The correct axiom, therefore, is not unconditional independence of past $\sigma$-fields, but **conditional independence of local $\sigma$-fields given the common past**. This is the global Markov property for DAGs — the foundational axiom of Bayesian networks and causal graphical models.

For causally incomparable nodes $u, v$, define their common past:

$$C(u,v) := \text{Past}(u) \cap \text{Past}(v).$$

Define the $\alpha$-mixing coefficient *conditional on the common past*:

$$\alpha_C(u, v) := \sup_{A \in \mathcal{F}(u),\, B \in \mathcal{F}(v)} \left| \mathbb{P}(A \cap B \mid \mathcal{G}(C(u,v))) - \mathbb{P}(A \mid \mathcal{G}(C(u,v)))\mathbb{P}(B \mid \mathcal{G}(C(u,v))) \right|,$$

where $\mathcal{F}(u) = \sigma(X_u)$ and $\mathcal{F}(v) = \sigma(X_v)$ are the *local* $\sigma$-fields, and $\mathcal{G}(C(u,v)) = \sigma(X_w : w \in C(u,v))$ is the $\sigma$-field of the common past.

The sharp locality axiom is:

**Axiom L1 (Conditional spacelike factorization).** For causally incomparable nodes $u$ and $v$:

$$\alpha_C(u, v) = 0 \quad \text{a.s.}$$

Equivalently: $\mathcal{F}(u) \perp \mathcal{F}(v) \mid \mathcal{G}(C(u,v))$.

This says: once you condition on the common causal past — everything that influenced both $u$ and $v$ — the local observables at $u$ and $v$ are exactly independent. The correlation between spacelike-separated events is entirely explained by shared history. There is no "spooky action at a distance"; there is only common ancestry.

The unconditional $\alpha$-coefficient between the full past $\sigma$-fields,

$$\alpha(\mathcal{G}(u), \mathcal{G}(v)) := \sup_{A \in \mathcal{G}(u),\, B \in \mathcal{G}(v)} \left| \mathbb{P}(A \cap B) - \mathbb{P}(A)\mathbb{P}(B) \right|,$$

will generally be positive whenever $C(u,v)$ is nonempty — because the shared ancestors create marginal dependence. But this unconditional dependence is not causal. It is confounding by common past, and it vanishes upon conditioning. The causal structure is encoded not in the unconditional $\alpha$, but in the conditional $\alpha_C$.

In AQFT, the corresponding axiom is local commutativity: operators localized in spacelike-separated regions commute. Our Axiom L1 is the probabilistic analog: conditional independence of local $\sigma$-fields replaces operator commutativity. The conditioning on common past is the new element that the partially overlapping filtration structure demands — and it connects the framework directly to the causal inference literature (Pearl, 2009) and the theory of Bayesian networks on DAGs.

---

## 5. Cone-supported weak dependence

Conditional factorization outside the causal cone is only half of the story. Inside the cone — where $u \preceq v$, so that $u$ is in the causal past of $v$ — there is genuine causal dependence: the observable at $v$ may depend on what happened at $u$, through the chain of causal links connecting them. This within-cone dependence should not be arbitrary. It should decay with causal separation.

For a node $v$ and an ancestor $u \preceq v$, the local observable $X_v$ may depend on $X_u$ both directly (through the causal path) and indirectly (through intermediate nodes). To measure the strength of this dependence, define the conditional bounded-Lipschitz coefficient:

$$D_{\text{BL}}(u, v \mid C) := \sup_{f \in \text{BL}_1(u),\, g \in \text{BL}_1(v)} \left| \text{Cov}(f(X_u),\, g(X_v) \mid \mathcal{G}(C)) \right|,$$

where $C$ is an appropriate conditioning set (e.g., the intermediate nodes between $u$ and $v$, or the common past in the case of partially comparable nodes), $\text{BL}_1(u)$ is the class of bounded-Lipschitz functions of $X_u$ with $\|f\|_\infty + \text{Lip}(f) \leq 1$, and the covariance is conditional.

**Axiom L2 (Cone-supported weak dependence).** For causally related nodes $u \preceq v$:

$$D_{\text{BL}}(u, v) \leq C \cdot \Phi\!\big(\delta(u, v),\, \theta(u, v)\big),$$

where $\delta(u, v)$ is a graph-distance measure (e.g., the length of the shortest causal path, or the number of "layers" separating the two nodes), $\theta(u, v)$ encodes directional or structural position within the cone, and $\Phi$ is decreasing in $\delta$. Canonical decay profiles include exponential $\Phi(\delta) = e^{-\lambda \delta}$ and polynomial $\Phi(\delta) = (1 + \delta)^{-\eta}$.

The pair $(\alpha_C, D_{\text{BL}})$ implements a division of labor:

- $\alpha_C$ answers a qualitative question: *is there causal dependence, beyond what common ancestry explains?* Its zero set for incomparable nodes defines the spacelike boundary — the light cone.
- $D_{\text{BL}}$ answers a quantitative question: *for causally related nodes, how strong is the dependence, and how does it decay with separation?* Its rate of decay will define metric scale.

In econometric terms: $\alpha_C = 0$ is a conditional independence test that identifies the boundary of causal influence — the light cone. $D_{\text{BL}}$ is the estimated strength of within-cone dependence. The first tells you which events are causally connected; the second tells you how far apart they are.

---

## 6. Rooted past subgraphs, overlap, and local geometry

Each node $v$ in the causal graph naturally determines a **rooted past subgraph**:

$$G_v := G[\text{Past}(v)], \quad \text{rooted at } v.$$

This is the graph induced by all nodes in the causal past of $v$, with $v$ as the root. It is the discrete spacetime "neighborhood" visible from $v$ — the complete causal history accessible to an observer at that event.

These rooted subgraphs are not merely bookkeeping devices. They are the microscopic carriers of local geometry — and the pattern of overlap between them encodes the geometry of spacetime.

### Overlap as distance

The partially overlapping structure of Section 3 gives a natural notion of proximity. For two nodes $u$ and $v$, the degree of overlap between their causal pasts measures how much shared history they have. A natural index is:

$$J(u, v) := \frac{|\text{Past}(u) \cap \text{Past}(v)|}{|\text{Past}(u) \cup \text{Past}(v)|},$$

a Jaccard-type similarity between causal pasts. When $J(u,v) \approx 1$, the two nodes share nearly identical histories — they are "close," in the sense that an observer at either one has access to almost the same information. When $J(u,v) \approx 0$, the two nodes have almost disjoint pasts — they are "far," with minimal shared information. When $J(u,v) = 0$ exactly — completely disjoint pasts — the two nodes are maximally separated, and by Axiom L1 their local observables are unconditionally independent (since there is no common past to condition on).

This overlap-based notion of distance is not an add-on to the dependence framework. It is the dependence framework, read at the set level. The $\alpha_C$ coefficient (Section 4) detects whether dependence exists beyond common ancestry; the $D_{\text{BL}}$ coefficient (Section 5) measures within-cone dependence strength; and the overlap index $J(u,v)$ captures the *structural source* of dependence — how much of the causal past is shared. Together, they give a multi-layered picture of spacetime proximity.

### The network economics parallel

In network economics and social learning theory, this overlap structure is precisely what determines the efficiency of information aggregation. Mossel, Sly, and Tamuz (2015, *Econometrica*) study strategic learning on social networks using the space of rooted graphs with the compact **local convergence topology** (Benjamini and Schramm, 2001), in which two rooted graphs are close if their neighborhoods up to radius $r$ are isomorphic for large $r$. Their key result is that the topology of the network — captured by the structure of rooted neighborhoods — governs whether agents can efficiently aggregate information. In their model, each agent has a private signal plus access to the actions of neighbors; the overlap between agents' information sets (shared neighbors, shared history of observations) determines the correlation structure and the learning outcome.

The parallel to our framework is structural, not metaphorical. In Mossel–Sly–Tamuz, the rooted neighborhood of each agent determines what that agent can learn. In our framework, the rooted past subgraph of each spacetime event determines what can be observed there. In both cases, the topology of rooted neighborhoods — how they overlap, how they differ, how they vary across the graph — is the fundamental object that governs the macroscopic behavior of the system.

### Rooted subgraphs as local geometry

In continuum differential geometry, local geometry is captured by the tangent space and the curvature tensor: you compare infinitesimal neighborhoods at different points via parallel transport and measure how they differ. In the finite model, the analog is the **shape** of rooted past subgraphs. Two nodes whose rooted subgraphs are isomorphic (as rooted graphs) inhabit "locally equivalent" spacetime regions — the discrete analog of a flat or homogeneous geometry. Two nodes whose rooted subgraphs differ structurally — different branching, different depth, different connectivity — inhabit "curved" or "distorted" regions.

Several discrete analogs of geometric notions emerge naturally:

- **Local equivalence**: isomorphism of rooted past subgraphs $G_v \cong G_w$ (the analog of flatness or homogeneity).
- **Curvature-like distortion**: measurable difference between rooted subgraphs at nearby nodes (the analog of Riemann curvature, which measures how parallel transport around a loop fails to return to its starting point).
- **Regularity of growth**: how the "volume" $|\text{Past}(v) \cap B_r(v)|$ — the number of nodes within graph-distance $r$ of $v$ — scales with $r$. Regular polynomial growth is the discrete precursor of a smooth manifold structure.
- **Directional asymmetry**: anisotropy in the dependence decay rate $D_{\text{BL}}$ within the cone, which encodes the analog of cone tilt — the local direction of the timelike axis.

The rooted past subgraph $G_v$, together with the overlap pattern $\{J(v, w)\}_{w \in V}$ and the local dependence structure measured by $(\alpha_C, D_{\text{BL}})$, is the finite model's version of the tangent space plus curvature at a point. Local geometry is encoded in the shape of the causal past, the pattern of overlap with neighboring pasts, and the dependence structure carried by the filtration.

### The uniformity of the speed of light

This local-geometry picture gives a clean account of one of the most celebrated facts about spacetime: the invariance of the speed of light.

In continuum relativity, the statement is that every local inertial observer sees the same light-cone slope — the numerical constant $c$ is universal. This looks like a deep axiom imposed from above. 

But in the finite-first picture, it becomes almost *tautological*. The DAG is the whole specification. If the local causal grammar — the rule governing which edges are admissible, how many immediate successors each node has, and what the local branching structure looks like — is the same across the graph, then the dependence frontier that separates causally reachable from causally unreachable nodes is locally uniform. In the continuum limit, that uniform frontier appears as an invariant light-cone slope, and the asymptotic observer calls it the speed of light $c$.

The universality of $c$ is therefore not a mysterious postulate about the physical world. It is the continuum expression of a uniform local causal grammar in the underlying DAG. In a flat spacetime, this uniformity is exact: the rooted past subgraphs are isomorphic everywhere. In a curved spacetime, the local grammar remains uniform — every node obeys the same immediate reachability rule — but the large-scale arrangement of rooted neighborhoods varies from place to place, producing an emergent curved geometry. Local $c$-invariance and global gravitational distortion coexist naturally, exactly as in GR: the speed of light is locally invariant, but the global cone structure bends.

---

## 7. The full axiom system

Let me now collect the full axiom system. The primitive is a finite DAG $G = (V, E)$ with local observables $\{X_v\}_{v \in V}$ on $(\Omega, \mathscr{F}, \mathbb{P})$, the local $\sigma$-fields $\{\mathcal{F}(v)\}$, and the induced overlapping past filtration $\{\mathcal{G}(v)\}_{v \in V}$.

### Information structure

**Axiom F1 (Isotony).** If $u \preceq v$, then $\mathcal{G}(u) \subseteq \mathcal{G}(v)$.

Larger causal pasts contain more information. This is the natural monotonicity of the filtration.

**Axiom F2 (Local generation).** For each $v$, $\mathcal{F}(v) \subseteq \mathcal{G}(v)$.

Every observable localized at node $v$ is contained in the past $\sigma$-field at $v$. The local information is part of the accumulated information.

### Locality

**Axiom L1 (Conditional spacelike factorization).** For causally incomparable $u, v$:

$$\mathcal{F}(u) \perp \mathcal{F}(v) \mid \mathcal{G}(C(u,v)), \quad \text{where } C(u,v) = \text{Past}(u) \cap \text{Past}(v).$$

Local observables at spacelike-separated nodes are conditionally independent given their common causal past. Marginal dependence may exist (through shared ancestors), but it is entirely explained by the common past and vanishes upon conditioning.

**Axiom L2 (Cone-supported weak dependence).** For causally related $u \preceq v$: $D_{\text{BL}}(u, v) \leq C \cdot \Phi(\delta(u,v), \theta(u,v))$, with $\Phi$ decreasing in $\delta$.

Within-cone dependence decays with graph distance.

### Geometry

**Axiom G1 (Cone regularity).** For each $v$, the causal future $J^+(v) := \{w : v \preceq w\}$ has a well-defined boundary structure in the graph: $\partial J^+(v)$ forms a regular codimension-one structure.

**Axiom G2 (Smooth variation of cones).** The rooted past subgraphs $G_v$ and $G_w$ vary "smoothly" across the graph: for nearby nodes (small graph distance), the rooted subgraphs are nearly isomorphic in the local convergence topology.

**Axiom G3 (Global hyperbolicity).** The induced causal order admits a layering: there exists a partition of $V$ into "slices" $\Sigma_0, \Sigma_1, \ldots, \Sigma_T$ such that every maximal causal chain intersects each slice exactly once, and causal edges only go from earlier to later slices.

Axioms G1–G3 are regularity conditions ensuring the finite graph is well-behaved enough that, in the large-$n$ limit, smooth geometry can emerge. G1 says the causal boundary is a genuine surface. G2 says the local geometry changes slowly across the graph. G3 — global hyperbolicity — ensures a well-posed initial-value problem. Together, the seven axioms define a **finite causal-dependence network**: a finite DAG with local observables, conditional spacelike factorization given the common past, decaying within-cone dependence, and regular causal structure.

---

## 8. What the DAG structure implies

The axioms of the previous section define a finite causal-dependence network: a DAG with local observables and a conditional independence structure. Before passing to the continuum limit, it is worth pausing to draw out what this structure *already implies* — because the theory of Bayesian networks and causal DAGs has been developed in depth (Pearl, 2009; Spirtes, Glymour, and Scheines, 2000), and several of its central results acquire striking physical interpretations when applied to spacetime.

### Markov equivalence as gauge invariance

Two DAGs are **Markov equivalent** if they encode exactly the same set of conditional independences — that is, no observational data can distinguish them. Verma and Pearl (1990) proved a sharp characterization: two DAGs are Markov equivalent if and only if they have the same *skeleton* (the undirected graph obtained by dropping arrow directions) and the same *v-structures* (collider configurations $u \to w \leftarrow v$ where $u$ and $v$ are not adjacent).

In our spacetime framework, this has a direct physical interpretation: **Markov equivalence is a discrete gauge symmetry**. Two causal graphs that share the same skeleton and v-structures produce identical conditional independence structures — identical dependence patterns between all local observables. No experiment confined to measuring statistical dependence can tell them apart.

This is the discrete analog of the diffeomorphism invariance discussed in Essay 2. In GR, the metric is defined only up to diffeomorphism: different coordinate representations of the same geometry are physically indistinguishable. Here, the causal graph is determined only up to Markov equivalence: different arrow orientations producing the same conditional independences are observationally indistinguishable. The "gauge orbit" is the Markov equivalence class. The "gauge-invariant" content is the skeleton plus v-structures — the part of the causal graph that can be identified from dependence data.

This connects to a deep question: when we say "geometry is induced from dependence," what exactly is recovered? The answer, at the discrete level, is: the Markov equivalence class of the causal graph — not the graph itself. Some causal arrows are identified (those participating in v-structures); others are not (those whose reversal preserves all conditional independences). This is partial identification in the sense of Essay 2, now appearing at the discrete level.

### The faithfulness condition and the Hauptvermutung

The axiom system requires a regularity condition that is implicit in the framework but deserves explicit statement: **faithfulness**. A distribution on the DAG is faithful if the *only* conditional independences it satisfies are those implied by the graph structure (via d-separation). There are no "accidental" independences from fine-tuned cancellations in the probability parameters.

Faithfulness is the condition that ensures the dependence structure faithfully encodes the causal structure. Without it, the support of the conditional $\alpha_C$ might fail to detect a causal connection that the graph contains — two causally related events could appear independent due to an unlikely cancellation in the DGP parameters.

This condition has a remarkable parallel in causal set theory. The **Hauptvermutung** (fundamental conjecture) of the causal set program (Bombelli, Lee, Meyer, and Sorkin, 1987) asserts that a causal set can be faithfully embedded in at most one spacetime, up to similarity. In other words, the discrete causal order determines the continuum geometry uniquely — no two distinct spacetimes produce the same causal set.

Faithfulness (in DAGs) and the Hauptvermutung (in causal sets) are not literally equivalent — they operate in different mathematical settings — but they express a common conceptual commitment: **the causal/order structure determines the geometry, with no accidental degeneracies.** Our framework sits between the two. It has the partial order of causal sets plus the stochastic content of Bayesian networks. Faithfulness is the condition ensuring that the probabilistic layer (the dependence structure) does not introduce degeneracies that the order-theoretic layer (the causal graph) does not warrant. It is a genericity condition on the DGP — the universe does not fine-tune its probability law to hide its causal structure.

The connection to causal set theory is worth emphasizing. Bombelli–Lee–Meyer–Sorkin start from a locally finite poset and aim to recover continuum spacetime via the slogan "order + number = geometry": the partial order gives the conformal class, and the counting measure (number of elements in a causal interval $\propto$ spacetime volume) gives the conformal factor. Our framework extends this by replacing the counting measure with a richer probabilistic structure: the stochastic content $\{X_v\}$ and the dependence coefficients $(\alpha_C, D_{\text{BL}})$. The counting measure is a special case — it corresponds to i.i.d. local observables, where the only structure is the graph itself. Our axioms allow for non-trivial local correlations, which is necessary once quantum effects are present.

### The Markov blanket as causal horizon

A node $v$'s **Markov blanket** consists of its parents, its children, and the co-parents of its children (other nodes that share a child with $v$). The defining property is: conditional on the Markov blanket, $v$ is independent of every other node in the graph. The blanket is the minimal set of nodes that completely screens $v$ from the rest of the universe.

In the spacetime DAG, the Markov blanket of an event $v$ is its **causal horizon** — the minimal set of events that forms a complete information screen around $v$. An observer who knows the Markov blanket of $v$ can predict $X_v$ as well as an observer who knows the entire universe; everything outside the blanket is redundant.

This gives a discrete version of the **domain of dependence** in GR: the region of spacetime that is completely determined by data on a given surface. In our framework, the Markov blanket is that surface. For a black hole, the Markov blanket of events inside the horizon is the horizon surface itself (plus co-parent structure). The **information paradox** from Essay 3 can be restated: can information about a node escape its Markov blanket? In the standard DAG framework, the answer is no — by definition, the blanket screens completely. But if the graph structure *evolves* (as it does when a black hole evaporates and the causal structure changes), the Markov blanket of the interior can shift, potentially allowing information to leak out. This is the graph-theoretic version of the question that Hawking raised: does black hole evaporation change the causal structure enough to restore unitarity?

---

## 9. What comes next

This essay has defined the primitive object of the program: a finite directed acyclic graph with local random observables, an overlapping spacetime filtration, and a system of axioms — conditional spacelike factorization (L1), cone-supported weak dependence (L2), and regularity conditions (G1–G3) — that encode the causal and geometric structure of spacetime at the discrete level. The DAG-theoretic consequences of this structure are already substantial: Markov equivalence provides a discrete gauge symmetry, faithfulness connects to the Hauptvermutung of causal set theory, and the Markov blanket gives a graph-theoretic causal horizon.

But the finite graph is only the DGP. The smooth Lorentzian manifold — the object that general relativity describes — is the population limit. Essay 5 will take that step: it will show how a sequence of finite causal-dependence networks, growing large and regular, converges to a continuum net of local $\sigma$-fields; how the support of the dependence functional $\alpha$ recovers the conformal class $[g]$ (via Malament's theorem); how the decay rate of $D_{\text{BL}}$ fixes the metric scale $\Omega^2 g$; how the Cauchy-temporal filtration reorganizes the overlapping structure into a one-parameter family that encodes the arrow of time; and how the dynamics of innovation flux may connect, speculatively, to the Einstein field equation.

The passage from finite graph to smooth geometry is the passage from DGP to population model — from the actual stochastic process to its asymptotic description. That is the subject of Part II.

---

### References

- Benjamini, I., and Schramm, O. (2001). Recurrence of distributional limits of finite planar graphs. *Electronic Journal of Probability*, 6, 1–13.
- Bombelli, L., Lee, J., Meyer, D., and Sorkin, R. D. (1987). Space-time as a causal set. *Physical Review Letters*, 59, 521–524.
- Bradley, R. C. (2005). Basic properties of strong mixing conditions: A survey and some open questions. *Probability Surveys*, 2, 107–144.
- Mossel, E., Sly, A., and Tamuz, O. (2015). Strategic learning and the topology of social networks. *Econometrica*, 83, 1755–1794.
- Pearl, J. (2009). *Causality: Models, Reasoning, and Inference*. 2nd edition. Cambridge University Press.
- Spirtes, P., Glymour, C., and Scheines, R. (2000). *Causation, Prediction, and Search*. 2nd edition. MIT Press.
- Verma, T. S., and Pearl, J. (1990). Equivalence and synthesis of causal models. *Proceedings of the 6th Conference on Uncertainty in Artificial Intelligence*, 220–227.
