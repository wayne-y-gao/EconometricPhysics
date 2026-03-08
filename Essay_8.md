# The Reconciliation: GR, QM, and the Arrow of Time

*Wayne Gao*

*I'm thankful to Claude, Gemini, and ChatGPT for discussing these ideas with me and helping me construct this essay.*

---

## 1. Returning to the specification sheet

Essay 3 posed the GR/QM conflict as a DGP specification problem and assembled a specification sheet: six requirements that any consistent theory of quantum gravity — any consistent DGP — must satisfy. They were:

1. **Consistency.** The DGP must recover the GR structural model in the population limit.
2. **Well-posedness.** The DGP must be well-defined at every finite resolution, including where GR diverges.
3. **Global sieve structure.** The DGP must accommodate quantum states in a global basis — entanglement, superposition, interference.
4. **Causality / mixing.** The innovation process must respect $c$ as a mixing condition.
5. **Unitarity / identifiability preservation.** The DGP must preserve distinguishability of quantum states at all times.
6. **Directionality.** The DGP must account for the arrow of time — entropy increase, irreversibility — even though the fundamental equations of both GR and QM are time-reversible.

At the time, the specification sheet was a wish list. The econometric language gave it clarity, but the tools to address it were not yet available.

Four essays later, the tools exist. Essay 4 built the finite causal-dependence network: a DAG with local observables, overlapping $\sigma$-fields, conditional spacelike factorization, and cone-supported weak dependence. Essay 5 took it to the population limit: Benjamini–Schramm convergence to a continuum net, recovery of conformal geometry from dependence support (Malament 1977), recovery of metric scale from dependence decay rates. Essay 6 identified the complex gap and proposed the layered architecture: global complex sieve specification, Born projection, local real-valued information. Essay 7 carried out the formal lifting: internal $\mathbb{R}^2$ with rotation operator $J$ at each node, two layers of $\sigma$-fields, lifted axiom system, interference, entanglement, and Bell violation as consequences.

This essay returns to the specification sheet and audits each requirement against this machinery. But it does more than audit. The specification sheet had six items; it was missing a seventh — the item that Essay 3 flagged in Section 8 but did not develop: the second law of thermodynamics. The real reconciliation is not between two theories (GR and QM) but among three: GR, QM, and the second law. The three-way tension is what this essay resolves — or rather, dissolves, by showing it was a category error all along.

---

## 2. Consistency: the population limit

The first requirement was that the DGP recover GR in the population limit. This is the econometric analog of consistency: the estimator converges to the true parameter as $n \to \infty$.

Essay 5 delivered this. The finite causal-dependence network of Essay 4, under Benjamini–Schramm convergence, produces a continuum net of local $\sigma$-fields — a structure analogous to a Haag–Kastler algebraic quantum field theory. The support of the dependence functional $\alpha_C$ recovers the conformal class $[g]$ via Malament's theorem: the causal order determines the conformal geometry. The decay rate of $D_{\text{BL}}$ provides the additional metric information needed to pin down the full metric $\Omega^2 g$.

The reconstruction chain is:

$$
\text{finite DAG} + \text{local } \sigma\text{-fields}
\;\xrightarrow{n \to \infty}\;
\text{continuum net}
\;\xrightarrow{\alpha_C}\;
[g]
\;\xrightarrow{D_{\text{BL}}}\;
g.
$$

The lifted framework of Essay 7 preserves this chain entirely. The lifting adds the specification layer (internal $\mathbb{R}^2$ with $J$) above the information layer, but the information-layer $\sigma$-fields — from which geometry is reconstructed — are undisturbed. The Born projection ensures that everything downstream of the projection proceeds exactly as in the scalar framework. The GR structural model is the population limit of the Born-projected dependence structure.

Consistency is satisfied — not as an assumption, but as a consequence of the reconstruction program. The DGP (the lifted finite graph) converges to the structural model (the Lorentzian manifold with Einstein's equations) through a well-defined limiting procedure. The analogy is precise: the characteristic function $\varphi(t)$ — the complex, globally defined specification of a distribution — determines the density $f(x)$ via inverse Fourier transform; the lifted amplitude field $\{Y_v, J\}$ determines the information-layer dependence structure via Born projection; and the population limit of that dependence structure recovers the smooth geometry. At every stage, the complex specification is global, the real-valued projection is local, and the population object emerges from the finite DGP as $n \to \infty$.

---

## 3. Well-posedness: the finite-first resolution

The second requirement was that the DGP remain well-defined where GR diverges. In GR, singularities — black hole interiors, the Big Bang — are points where the curvature becomes infinite and the structural model breaks down. The Penrose singularity theorems guarantee that such pathologies exist under generic conditions.

In the finite-first framework, this requirement is satisfied by construction. The primitive object is a finite DAG — a discrete, finite structure with no infinities of any kind. There are no divergent curvatures because there is no continuum. There are finitely many nodes, finitely many edges, finitely many local observables. The Riesz representer norms are trivially bounded because everything is finite-dimensional.

The "singularity" arises only in the population limit. When the finite graph grows large and the Benjamini–Schramm limit is taken, the continuum geometry can develop regions of divergent curvature. But these are artifacts of the limiting procedure, not features of the DGP. The finite graph at any finite stage is perfectly well-behaved.

This is the sieve regularization perspective from Essay 3, now made concrete. The Planck-scale discretization is the mesh size $\varepsilon$ that prevents the divergences of the population model. The DGP is well-posed at every finite resolution. The population model's singularities are the infinite-resolution extrapolation of a process that is always finite in practice.

An econometric analogy: a nonparametric regression estimator with a kernel of bandwidth $h > 0$ is always well-defined, even if the true regression function has a discontinuity or a cusp. The pathology belongs to the population object, not to the finite-sample estimator. The bandwidth $h$ (the Planck length) regularizes the divergence. Sending $h \to 0$ (taking the continuum limit) recovers the singularity — but the estimator at any finite $h$ is smooth.

---

## 4. Global sieve structure: the lifted amplitude field

The third requirement was that the DGP accommodate quantum states expanded in a global basis: superposition, entanglement, interference. The scalar framework of Essays 4–5, with real-valued observables and real-valued $\sigma$-fields, could not do this. The complex gap was the subject of Essay 6, and the formal construction of Essay 7.

The lifted framework delivers the global sieve structure through five ingredients (the inventory from Essay 6, Section 9):

- An internal $\mathbb{R}^2$ at each node, replacing the scalar $X_v$ with a 2-vector $Y_v$.
- The rotation operator $J$ with $J^2 = -I$, generating the $SO(2) \cong U(1)$ phase symmetry.
- The composition rule: amplitudes (2-vectors) add before norm-squaring.
- Conjugation: $J$-reflection $(a, b) \mapsto (a, -b)$.
- The Born map: $P = \|Y\|^2$, projecting from specification to information.

These five items are equivalent to "use complex Hilbert space," but stated in a way that separates the structurally necessary from the notationally convenient. The wavefunction is a global sieve specification of the amplitude field $\{Y_v\}$ on the DAG. Its Born projection generates the local information layer. The Bell violation (Essay 7, Section 8) confirms empirically that the internal state space is at least two-dimensional with rotational structure — this is not a hidden-variable model in disguise.

The global sieve structure is therefore realized, and the Bell inequality provides the empirical test that distinguishes the lifted framework from any classical substitute. In the language of Essay 3: the DGP's basis functions are global — like Fourier modes extending over all of time, or like the characteristic function that specifies a distribution globally in the complex frequency domain while the density itself is the real, locally estimable object. The cross-terms between distant regions are built into the expansion. Entanglement is a feature of the global specification, not evidence of faster-than-light signaling.

---

## 5. Causality and mixing: dependence support as light cone

The fourth requirement was that the innovation process respect $c$ as a mixing condition: no new information propagates faster than light.

This is delivered by Axiom L2 (cone-supported weak dependence) from Essay 4, together with the level/innovation distinction sharpened in Essay 6.

At the information layer, Axiom L1 (conditional spacelike factorization) states that local observables at spacelike-separated nodes are conditionally independent given their common causal past. This is the $c$-enforced mixing condition: beyond the light cone, conditional independence is exact, not merely asymptotic. It is a stronger condition than any mixing condition in time series econometrics — $\alpha$-mixing, $\beta$-mixing, or any of their variants. Those guarantee asymptotic decay. The light cone enforces a hard cutoff.

Within the cone, Axiom L2 ensures that dependence decays with graph distance. The dependence structure is not only bounded in support (by the light cone) but also decaying in strength (within the cone). This double regularity — hard support boundary plus smooth internal decay — is what makes local physics Donsker-stable: the empirical process within a light cone converges to a well-defined limit.

The crucial subtlety is the distinction between the **specification layer** and the **information layer**. At the specification layer, the amplitude 2-vectors $Y_u$ and $Y_v$ at spacelike-separated nodes may be correlated through a common ancestor — this is entanglement. The specification-layer covariance $T_1 \text{Var}(Y_s) T_2^T$ can have non-trivial rotational (antisymmetric) structure. But this correlation does not violate causality because it carries no new information: it was established when the entangled state was prepared (at the common ancestor), not transmitted after the fact.

The **innovation** $\varepsilon_v$ — the genuinely new randomness at each node — propagates only along causal edges. The no-communication theorem, in this framework, is the statement that the information-layer reduced $\sigma$-field of one node is unaffected by any action at a spacelike-separated node. The correlations become visible only when outcomes at both nodes are later compared — and that comparison requires a classical signal, which propagates at most at $c$.

The econometric parallel from Essay 3 remains apt: entanglement is correlation, not causation. Two time series can be correlated through common factors without either causing the other. Observing one gives information about the other, but only because of shared structure in the DGP — not because a signal was transmitted. The "spookiness" of entanglement is the confusion of correlation with causation, played out in the physical universe.

---

## 6. The Markov blanket as event horizon

Essay 4, Section 8, introduced the Markov blanket of a node in the spacetime DAG and noted its physical interpretation as a causal horizon. This section develops that observation fully, because it is the bridge to the information paradox.

Recall the definition: the **Markov blanket** of a node $v$ in a DAG consists of its parents, its children, and the co-parents of its children (other nodes sharing a child with $v$). The defining property is that $v$ is conditionally independent of every other node in the graph, given its Markov blanket:

$$
X_v \perp X_w \mid X_{\text{MB}(v)}, \qquad \forall \, w \notin \text{MB}(v) \cup \{v\}.
$$

The Markov blanket is the minimal information screen: knowing everything about the blanket makes the rest of the universe redundant for predicting $v$.

In the spacetime DAG, this acquires a direct physical meaning. Consider a region $R$ of the graph — a set of nodes modeling the interior of a black hole. The **Markov blanket of $R$** is the minimal set of nodes that screens $R$ from the exterior:

$$
X_R \perp X_{\text{ext}} \mid X_{\text{MB}(R)}.
$$

This is the graph-theoretic event horizon. The black hole's interior is conditionally independent of the exterior, given the horizon surface. An exterior observer who knows everything on the Markov blanket can predict the interior as well as an observer who knows the entire universe; everything outside the blanket is redundant.

The **no-hair theorem** acquires a clean reformulation. In GR, the no-hair theorem states that a stationary black hole is completely characterized by three parameters: mass $M$, charge $Q$, and angular momentum $J_{\text{BH}}$. In filtration language: the Markov blanket of the black hole interior **compresses** the specification-layer state of the interior to finitely many information-layer parameters. The full internal configuration — whatever fell in — is specification-layer information that the Born-projected information layer on the blanket reduces to $(M, Q, J_{\text{BH}})$. The rest is discarded by the projection.

This is identification failure at the information layer, exactly as discussed in Essay 2. The internal details of the collapse are **not identified** from exterior information-layer observations. Different initial configurations — a star made of hydrogen versus one made of iron — lead to the same $(M, Q, J_{\text{BH}})$ on the blanket. From the exterior observer's information layer, the star's composition is unidentifiable. In Essay 2's terms: "fundamentally unidentifiable means nonexistent" — *at the information layer.*

But the specification layer carries more. The interior's amplitude state $\{Y_v : v \in R\}$ encodes the full 2-vector structure, including phase and rotational correlations that the Born map projects away. The Markov blanket screens at the information layer; it says nothing about the specification layer. This is not a gap or a puzzle — it is the layer separation working exactly as it should.

---

## 7. The information paradox in filtration language

The information paradox arises from ignoring this layer separation.

Hawking (1974, 1975) showed that a black hole radiates. The radiation has an approximately thermal spectrum, characterized by the Hawking temperature $T_H = \hbar c^3 / 8\pi G M k_B$. If the radiation is exactly thermal, it carries no information about the interior state beyond the temperature (which encodes only the mass). Hawking's conclusion: information is destroyed. The interior's state is irretrievably lost when the black hole evaporates.

But this conclusion is an information-layer calculation applied to a specification-layer question. The Hawking computation works entirely at the level of Born-projected observables — it computes the spectrum of the radiation as seen by the information layer. Finding that this spectrum is thermal is no more surprising than finding that the Born projection of a rich specification-layer state looks simple: that is what projections do. The question is whether this information-layer thermal appearance means the specification-layer state has been destroyed. In our framework, it cannot, because the Markov blanket operates at the information layer, and the specification layer is global.

The Markov blanket screens at the level of Born-projected observables: $X_R \perp X_{\text{ext}} \mid X_{\text{MB}(R)}$, where all variables are information-layer (real-valued, norm-squared). The specification-layer $\sigma$-fields are richer: $\mathcal{F}^{\text{spec}} \supset \mathcal{F}^{\text{info}}$. The specification-layer amplitudes $\{Y_v : v \in R\}$ are correlated with the exterior amplitudes $\{Y_w : w \in \text{ext}\}$ through the propagators and $J$-structure of the graph. These specification-layer correlations — the antisymmetric (symplectic) part of the covariance, the entanglement signature from Essay 7 — are global, because the specification layer is global. They do not "leak through" the Markov blanket, because they were never confined by it in the first place. The Markov blanket is a boundary at the information layer; the specification layer, being global, simply does not see it as a boundary.

This is the same logic as "entanglement does not violate $c$" from Section 5, now applied to black holes. Entanglement correlations between interior and exterior are specification-layer facts — global structural features of the amplitude field, established when the state was prepared. The Markov blanket screens the *information layer* perfectly, just as spacelike separation enforces conditional independence at the information layer. But the specification layer's global correlations persist across both, because that is what "global" means.

The information paradox is therefore a **category error**: demanding information-layer answers to a specification-layer question. The specification layer preserves the full amplitude state throughout — unitarity is never violated there. The apparent information loss is the Born projection doing what it always does: compressing a richer specification into a coarser observable. The thermal spectrum that Hawking computed is the information-layer shadow of a unitary specification-layer process — just as the no-hair theorem is the information-layer shadow of a richer interior state. Both are instances of identification failure at the information layer, not destruction at the specification layer.

The **Page curve** (Page, 1993) fits naturally into this picture. The entanglement entropy — the von Neumann entropy of the reduced specification-layer state on the exterior — tracks how much specification-layer information the exterior has accumulated. Early in the evaporation, the Markov blanket is thick (many nodes on the horizon), the information-layer screening is effective, and the exterior's specification-layer entropy increases: the exterior is entangled with a large, inaccessible interior. At the **Page time** — roughly when half the initial entropy has been radiated — the blanket begins to thin. As the black hole shrinks, the exterior's share of the total specification-layer state grows, and the entropy decreases: the exterior progressively contains more of the original specification-layer information. At complete evaporation, the blanket is gone, and the full specification-layer state is encoded (in principle) in the exterior radiation. Unitarity is preserved throughout at the specification layer. The information-layer observer, who sees only Born-projected observables, perceives an apparent paradox only because the Born projection discards the phase and rotational structure that encodes the interior state.

This is not a proof — it does not provide the dynamical mechanism by which the specification-layer information becomes accessible. But it is a diagnosis: the information paradox arises from conflating the information layer with the specification layer, which is the same conflation that generates the measurement problem, the entanglement "paradox," and the QM/2nd-law "tension." In each case, the resolution is the same: distinguish the layers.

---

## 8. Unitarity, the second law, and the arrow of time

The fifth and sixth requirements on the specification sheet — unitarity and directionality — are where the three-way tension becomes sharpest. I will state it clearly, then dissolve it.

**The tension.** GR's Einstein field equations are time-reversible: for every solution, the time-reversed solution is also valid. QM's Schrödinger equation is unitary: evolution preserves the inner product, and the process is reversible. Yet the second law of thermodynamics insists that entropy increases, that time has a direction, that macroscopic processes are irreversible. All three — GR, QM, and the second law — are empirically confirmed. How can the fundamental equations be reversible if the world is not?

**The dissolution.** The three statements describe three different layers of the framework, and there is no contradiction because the layers are distinct.

**(a) Unitarity: the specification layer is time-symmetric.**

The specification-layer propagators $T_{u \to v}$ of Essay 7 preserve the norm of the amplitude 2-vector: $\|T Y\| = \|Y\|$ when $T$ is orthogonal. The total specification-layer $\sigma$-field carries the full amplitude information, and unitary evolution preserves it. Given the full specification-layer state at any time, the state at any other time (past or future) can be reconstructed. No information is lost at this layer. This is the quantum analog of the Einstein equations' time-reversibility: the structural law is symmetric in time.

**(b) The second law: the information layer is irreversible.**

The information-layer filtration $\{\mathcal{G}^{\text{info}}(v)\}$ grows monotonically along causal chains. As time advances, more nodes are added to the causal past, more innovations $\varepsilon_v$ are realized, and the filtration accumulates more information. The Born projection discards the phase (angular) component of the amplitude — the part of the specification that the information layer cannot see. This discarding is irreversible: once the 2-vector $(a, b)$ is projected to $a^2 + b^2$, the angle $\theta = \arctan(b/a)$ is lost.

Entropy, in this framework, is a measure of what the information layer has accumulated but cannot invert. The second law is the statement that the Born-projected entropy increases: the information layer, which sees only $\|Y\|^2$ at each node, accumulates more and more data points, each one the shadow of a richer specification-layer state. The shadow is a many-to-one map (many amplitude vectors share the same norm), so the information layer's uncertainty about the specification layer increases even as its store of Born-projected data grows. This is the origin of entropy increase: the growing gap between what the information layer has observed and what the specification layer contains.

**(c) The arrow of time: innovations are the source.**

The local innovations $\varepsilon_v \in \mathbb{R}^2$ at each node of the DAG — the genuinely new randomness entering the system — are the microscopic source of irreversibility. Each innovation is a fresh draw from the local stochastic environment. Once realized, it enters the filtration and cannot be un-observed. The arrow of time is not imposed from above; it is the cumulative effect of innovations: new randomness entering the information layer at every node, advancing the filtration in one direction.

In an econometric time series, the innovations $\varepsilon_t$ are the source of the process's irreversibility. The structural model (the ARMA coefficients, the regression function) is time-symmetric; the realized sample path is not, because the innovations are realized sequentially and the filtration $\mathcal{F}_t$ grows. The same logic applies to spacetime: the specification-layer law is time-symmetric (unitarity); the information-layer realization is not (arrow of time), because innovations are realized along the causal order and the filtration grows monotonically.

Are the innovations $\varepsilon_v$ ontologically fundamental — irreducible new randomness — or are they effective, arising from coarse-graining a deeper deterministic or unitary layer? The framework does not derive the answer from first principles. But the spacetime filtration model from Essay 4 onward has a clear stance: the innovations are primitive. The filtration grows because genuinely new information enters at each node, not because pre-existing information is revealed by a finer decomposition. 

This is the same commitment that econometrics makes when it writes down a stochastic DGP: the $\varepsilon(x)$ is a real stochastic process, not an epistemic placeholder for deterministic dynamics we have not yet uncovered. The model could be wrong — but a framework that delivers internal coherence and coherence with empirical data is, in econometrics, the only thing we have and the only thing we need. Epistemology is ontology: if the innovations are what the filtration requires to be well-defined and what the data are consistent with, then they are real.

**The three are compatible because they live at different levels.**

| Layer | Property | Time symmetry |
|-------|----------|---------------|
| Population structural model (GR) | Einstein field equations | Reversible |
| Specification layer (QM) | Unitary amplitude propagation | Reversible |
| Information layer (2nd law) | Filtration growth, Born projection | Irreversible |

The "conflict" was a category error: treating a property of one layer (irreversibility at the information layer) as if it contradicted a property of another layer (reversibility at the specification layer). There is no more contradiction between unitarity and the second law than there is between the time-reversibility of Newton's laws and the irreversibility of a shuffled deck of cards. The laws are symmetric; the realizations, viewed through a coarsening map, are not.

---

## 9. What reconciliation means

Let me now revisit the specification sheet with the audit complete.

| Requirement | Status | Delivered by |
|-------------|--------|-------------|
| Consistency | ✓ | Essay 5: Benjamini–Schramm limit recovers continuum geometry |
| Well-posedness | ✓ | Essay 4: finite DAG, no infinities by construction |
| Global sieve structure | ✓ | Essays 6–7: lifted amplitude field with $J$, Bell violation |
| Causality / mixing | ✓ | Essay 4: Axioms L1–L2; Essay 6: level/innovation distinction |
| Unitarity | ✓ | Essay 7: specification-layer norm preservation; Section 8 above |
| Directionality | ✓ | Section 8 above: innovations + Born projection + filtration growth |

I should be explicit about what "✓" means. It does not mean "proven from first principles." It means: the framework provides a consistent architecture in which the requirement is naturally satisfied, stated in precise mathematical language, and connected to the other requirements through a common structure.

What the framework does *not* do:

- It does not derive the axioms from something deeper. The lifted axioms (F1$'$–F2$'$, L1$'$–L2$'$, Axiom J, G1$'$–G3$'$) are postulated, not proven. The Born map is postulated (Axiom F2$'$), not derived.
- It does not solve the measurement problem in the foundational sense. Why the specification layer projects onto the information layer through norm-squaring (rather than some other map) remains open.
- It does not complete the continuum limit of the lifted framework. Essay 5 took the scalar framework to its Benjamini–Schramm limit. The analogous step for the lifted framework — recovering continuum quantum field theory from a lifted finite graph — is substantially harder and is not attempted here.
- The Page curve argument in Section 7 is heuristic. A rigorous derivation would require a dynamical theory of the graph evolution (how the DAG changes as the black hole evaporates), which the current framework does not provide.

What the framework *does* do is provide a **common language** in which all six requirements can be stated, connected, and checked for mutual consistency. The language is econometric — filtrations, $\sigma$-fields, conditional independence, dependence decay, identification, estimation — and the architecture is layered: structural grammar (DAG), specification (amplitude + $J$), projection (Born map), information (filtration). Each layer has its own symmetries and its own properties, and the "conflicts" between GR, QM, and the second law are resolved by assigning them to different layers.

The reconciliation, then, is not a single equation that unifies gravity and quantum mechanics. It is a **structural diagnosis**: the three pillars of fundamental physics describe three aspects of a layered information architecture, and the apparent conflicts between them arise from conflating the layers. The GR/QM conflict is the conflation of population and sample (or structural model and DGP). The QM/2nd-law conflict is the conflation of specification and information. The GR/2nd-law conflict is the conflation of the deterministic structural model with the stochastic realization.

Once the layers are distinguished, the conflicts dissolve. What remains are genuine open problems — the Born map derivation, the measurement problem, the continuum limit — but these are well-posed technical questions within a coherent framework, not paradoxes arising from incommensurable worldviews.

---

## 10. Closing: what exists is what admits this layered structure

This series has built, essay by essay, toward a single thesis: **epistemology is ontology.** What exists is what can be identified from the structural model and estimated from finite data.

Essay 1 established the estimation side: quantum mechanics and semiparametric statistics share the Hilbert-space geometry of efficient inference. What exists at the quantum level is what can be resolved from noise — what can be estimated.

Essay 2 established the identification side: general relativity and structural econometrics share the logic of gauge freedom, partial identification, and the no-hair theorem. What exists at the gravitational level is what can be recovered from the structural model — what can be identified.

Essay 3 posed the conflict: if identification and estimation are two sides of the same inference problem, why do the theories they correspond to (GR and QM) conflict? The answer: they describe different levels of the inference hierarchy — population and sample — and the conflict is a DGP specification problem.

Essays 4–5 built the dependence-first axiomatization: a finite causal DAG with overlapping $\sigma$-fields, conditional independence, dependence decay, and a population limit that recovers geometry. The manifold is the population model; the DAG is the DGP.

Essays 6–7 performed the complex lift: the internal $\mathbb{R}^2$ with rotation operator $J$, the two-layer $\sigma$-field structure, interference and entanglement as consequences of rotational structure, the Bell inequality as dimensional test.

This essay has audited the specification sheet and dissolved the three-way tension. The reconciliation is layered:

$$
\text{DAG (grammar)}
\;\to\;
\text{amplitude field } \{Y_v, J\} \text{ (specification)}
\;\xrightarrow{\text{Born}}\;
\text{dependence (information)}
\;\xrightarrow{n \to \infty}\;
\text{geometry (population)}.
$$

Each layer has its own logic: the grammar provides causal structure, the specification provides reversible amplitude dynamics, the Born map provides irreversible projection, the information layer provides observable dependence, and the population limit provides smooth geometry. GR lives at the right end. QM lives in the middle. The second law lives at the junction of innovations and Born projection — new specification-layer randomness arriving at each node, compressed into information-layer observables along the causal order. They are not competing descriptions of the same thing. They are descriptions of different layers of a single architecture.

The thesis, fully stated: **what exists is what admits a consistent layered DGP — a specification whose population limit is the structural truth and whose information-layer realization is the observable, estimable, irreversible world.**

The next and final essay will show that this architecture is not specific to physics. The same layered structure — local information, structural constraints, overlapping filtrations, specification and projection — naturally axiomatizes economics from the existence of a local economic agent. The econometric vocabulary was not borrowed from statistics and applied to physics. It was not borrowed at all. It is the shared mathematical language of structured information dynamics — a language that physics and economics both speak, because they are both about what locally rooted information structures can identify and estimate from the data available to them.

*What exists is what can be identified and estimated — in every regime, at every scale, in every domain where locally rooted observers interact with structured information.*

**Epistemology is ontology.**

---

### References

- Bekenstein, J. D. (1973). Black holes and entropy. *Physical Review D*, 7, 2333–2346.
- Bombelli, L., Lee, J., Meyer, D., and Sorkin, R. D. (1987). Space-time as a causal set. *Physical Review Letters*, 59, 521–524.
- Hawking, S. W. (1974). Black hole explosions? *Nature*, 248, 30–31.
- Hawking, S. W. (1975). Particle creation by black holes. *Communications in Mathematical Physics*, 43, 199–220.
- Jacobson, T. (1995). Thermodynamics of spacetime: The Einstein equation of state. *Physical Review Letters*, 75, 1260–1263.
- Malament, D. B. (1977). The class of continuous timelike curves determines the topology of spacetime. *Journal of Mathematical Physics*, 18, 1399–1404.
- Page, D. N. (1993). Information in black hole radiation. *Physical Review Letters*, 71, 3743–3746.
- Pearl, J. (2009). *Causality: Models, Reasoning, and Inference*. 2nd edition. Cambridge University Press.
- Penrose, R. (1965). Gravitational collapse and space-time singularities. *Physical Review Letters*, 14, 57–59.
- Susskind, L. (1995). The world as a hologram. *Journal of Mathematical Physics*, 36, 6377–6396.
- 't Hooft, G. (1993). Dimensional reduction in quantum gravity. arXiv:gr-qc/9310026.
