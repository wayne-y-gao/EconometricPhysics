# An Econometric Reframing of the GR/QM Conflict

*Wayne Gao*

*I'm thankful to Gemini and Claude for discussing these ideas and composing this essay.*

---

## 1. The GR/QM conflict as model versus DGP

The first essay established a correspondence between quantum mechanics and semiparametric estimation. The second established a correspondence between general relativity and structural identification. This third essay addresses the obvious next question: if GR and QM map onto two complementary pillars of econometric analysis, can the econometric framework illuminate their incompatibility — and what reconciliation would require?

In econometrics, identification and estimation are different steps in the same workflow. An econometrician first asks whether a parameter is identified and then asks how to estimate it from data. The two steps use different tools, produce different theorems, but are fully compatible. There is no "conflict" between identification theory and estimation theory. They are two perspectives on the same underlying reality.

Physics, however, has a conflict. GR and QM are not merely different perspectives on the same reality — they are logically incompatible in several deep ways. The cleanest way to see this is through the inference hierarchy.

GR is all bias, no variance. It is a population-level structural model: it specifies the identifying restrictions — the Einstein field equations — that constrain the relationship between matter and geometry. The metric $g_{\mu\nu}$ is a deterministic function of the matter content. There are no fluctuations, no measurement disturbances, no epistemic uncertainty. Everything that can be identified *is* identified (up to the gauge and support issues discussed in Essay 2). GR answers the identification question: *what is in principle recoverable from perfect data?*

QM is irreducible variance at the Planck scale. It is the finite-sample DGP: it governs what actually happens when you try to measure the universe at any finite resolution. You cannot simultaneously pin down position and momentum (the Heisenberg constraint from Essay 1). Every measurement disturbs the system. The Planck constant $\hbar$, which plays the role of $1/n$, is the floor — the minimum "variance" that the universe permits. QM answers the estimation question: *what can you actually learn from finite, noisy data?*

In the language of nonparametric regression: GR is the population regression function $m(x)$ — smooth, deterministic, defined at infinite resolution. QM is the finite-sample DGP $\sum_k \alpha_k b_k(x) + \varepsilon$ — a sieve approximation with finitely many basis terms plus irreducible noise. The sieve coefficients $\alpha_k$ encode the quantum state; the basis functions $b_k$ are the modes of the Hilbert space; and the noise $\varepsilon$ is the irreducible quantum randomness governed by $\hbar$. The population limit $n \to \infty$ (equivalently $\hbar \to 0$) sends the sieve approximation to the truth: $\sum_k \alpha_k b_k \to m$.

The two theories describe *different levels of the inference hierarchy*. GR is the population truth that you would see with infinite data at infinite resolution. QM is the finite-sample reality that governs what you actually observe. The "conflict" between them is the bias-variance tradeoff operating at the level of the theory itself: GR wants zero variance (smooth geometry), but QM says variance cannot go below $\hbar$.

I should be direct about the limits of this reframing. The conflict between GR and QM is not *only* about resolution. There are deeper logical incompatibilities: GR treats spacetime as a smooth dynamical object while QM requires a fixed background time for its evolution equations; quantizing gravity naively produces non-renormalizable infinities that cannot be absorbed by any finite sieve; the measurement problem in QM — why does a definite outcome emerge from a superposition? — has no analog in classical GR. These are not mere "scale mismatches." They are structural incompatibilities in the mathematical foundations. The population-versus-DGP metaphor captures one important dimension — the scale mismatch — but does not dissolve the full problem.

Still, the reframing has teeth. It provides a precise vocabulary for stating what reconciliation *requires*, and it tells us immediately what *kind* of problem reconciliation is: a DGP specification problem.

---

## 2. Quantum gravity as a DGP specification problem

If you have ever written an econometric paper, you known the DGP specification problem becomes crucial when you need to write your simulation section, where you hope to show your proposed method works.

What physicists call "quantum gravity" is, in econometric language, the search for a DGP specification $P_\theta$ with the following properties:

**Finite-sample regime.** At the Planck scale, the DGP is discrete, stochastic, and subject to irreducible uncertainty (the Heisenberg constraint from Essay 1). The "sample size" is finite, and quantum fluctuations dominate.

**Population limit.** As the resolution increases ($n \to \infty$, equivalently $\hbar \to 0$), the sieve approximation converges to the population truth: $\sum_k \alpha_k b_k \to m$. The structural parameter $g_{\mu\nu}$ is recovered as the population object.

**Consistency at singularities.** In regions where GR predicts divergent curvature (black hole interiors, the Big Bang), the DGP remains well-defined — the sieve Riesz representer norms stay finite, the metric entropy stays bounded. The DGP does not "blow up" where the structural model does.

This has the flavor of a *sieve regularization* problem: the Planck-scale discretization is a mesh size $\varepsilon$ that prevents the divergences of infinite curvature; the requirement that smooth geometry emerges at macroscopic scales is the consistency condition that the sieve approximation converges to the target. Several active research programs — causal dynamical triangulations, loop quantum gravity, string theory — are, in different ways, attempting exactly this.

But I should not oversell the analogy. Quantum gravity is more than regularization of a known model. The challenge is not just controlling representer norms or tuning a sieve parameter. It requires finding a fundamentally new theory that reconciles QM's intrinsic indeterminacy with GR's dynamical spacetime — a theory where the "index set" (spacetime itself) may be an emergent outcome rather than a fixed domain. The sieve perspective is a useful conceptual lens, not a solution.

In econometric terms: we are looking for a specification that is *consistent* for the GR structural parameter in the population limit, *well-posed* at every finite resolution, and whose *identified functionals* match the physical observables at all scales. We will add further requirements to this specification sheet as the essay proceeds.

---

## 3. Wave-particle duality as basis choice

The first "weird" quantum phenomenon that the econometric lens clarifies is wave-particle duality — the fact that quantum objects behave as particles in some experiments and waves in others.

In the sieve framework, this is not mysterious at all. It is a choice of basis.

A "particle" is a quantum state expanded in a *local* basis — a basis of position eigenstates, each sharply localized at a point. This is like using a kernel basis or wavelets at fine scale in nonparametric estimation: each basis element has compact support, concentrated at a specific location.

A "wave" is the same quantum state expanded in a *global* basis — a basis of momentum eigenstates (plane waves), each spread out over all of space. This is like using a Fourier basis or polynomials in sieve estimation: each basis element has global support, oscillating across the entire domain.

The state itself does not change. Only the representation changes. A function $f$ is the same function whether you expand it in wavelets, in B-splines or in Fourier modes. The coefficients change; the function does not. "Wave-particle duality" is the statement that the Hilbert space of quantum states admits both local and global bases, and the same state looks different depending on which basis you use to describe it.

The "which-path" experiments in quantum mechanics make this concrete. In the double-slit experiment, if you measure which slit the particle goes through (local basis), you destroy the interference pattern (global basis). If you don't measure the path, the interference pattern appears. This is exactly the Fourier uncertainty principle from Essay 1: localizing in position (choosing the local basis) delocalizes in momentum (losing the global basis representation), and vice versa. You cannot have sharp coefficients in both bases simultaneously. The "mystery" of wave-particle duality is the Heisenberg uncertainty principle wearing a different hat.

For an econometrician, the lesson is familiar: the choice of sieve basis does not change the target function — it changes what features of the function are easy to read off. B-splines make local features transparent; Fourier modes make periodic structure transparent. Neither basis is "right." They are different coordinate systems on the same function space.

---

## 4. Quantum entanglement as a global sieve property

Entanglement is often presented as the most mysterious feature of quantum mechanics — Einstein's "spooky action at a distance." Two particles, once entangled, exhibit correlations that persist no matter how far apart they are separated. Measuring one particle instantaneously "determines" the state of the other, even across cosmological distances.

From the sieve perspective, the mathematical structure of entanglement — the global correlations it produces — is a natural consequence of using basis functions with global support. This clarifies the mathematics, even if the deeper physical question (why does the universe admit such a Hilbert space representation?) remains open.

Consider a joint quantum state of two particles A and B, separated by an arbitrary distance. If we expand this state in a product basis of local functions — one set for A, one set for B — then an entangled state is one that *cannot* be written as a product $\psi_A \otimes \psi_B$. It has cross-terms: basis elements that simultaneously involve both A and B.

But this is exactly what happens when you expand a joint distribution in a global sieve basis. Fourier modes on the full domain, polynomials on the full support, wavelets at coarse scales — all of these basis functions extend across the entire space. When you expand a bivariate function in such a basis, cross-terms between distant regions are *automatic*. They are not evidence of any mysterious communication between the regions. They are a feature of the basis.

The Bell inequality violations, which experimentally confirm that entanglement cannot be explained by "local hidden variables," reinforce this point. The correlations between entangled particles are *stronger* than any model built from purely local basis functions can produce. This is precisely because the quantum sieve basis is global — the basis functions were never local to begin with, so restricting to local bases (which is what a "local hidden variable" model does) necessarily loses information.

An econometric parallel: if you try to approximate a bivariate function $f(x, y)$ using only additive separable terms $g(x) + h(y)$ (a "local" basis in the sense that each term depends on only one variable), you will underfit whenever $f$ has genuine interaction terms. The Bell inequality is a test statistic that rejects the separable model.

---

## 5. Measurement as estimation

The measurement problem is perhaps the deepest puzzle in quantum mechanics. Before measurement, a quantum system exists in a superposition — a sum over all possible states, weighted by complex amplitudes. Upon measurement, the superposition "collapses" to a single definite outcome. How and why does this happen? What distinguishes measurement from any other physical interaction?

The econometric perspective offers a reframing — but one that requires care about which level of the hierarchy we are working at. Recall the framework from Section 1: GR is the population regression function $m(x)$, while QM is the DGP $\sum_k \alpha_k b_k(x) + \varepsilon$ — the finite-resolution sieve approximation plus irreducible noise. The quantum state $|\psi\rangle$ is not the population object. It is the *DGP specification*: it encodes the complete probability law governing all possible measurements. It tells you, for any observable you might measure, the distribution of outcomes. It is the analog of knowing the full DGP $P_\theta$ — the joint distribution — before drawing any data.

Measurement is estimation — but estimation operating on the DGP, not the population. In econometrics, computing an estimate combines three ingredients: a *functional* (the target parameter $\nu(P)$ — what you want to learn), an *estimator* (the procedure $\hat{\nu}_n$ — how you compute it from data), and a *realization* (the sample — the data you actually observe). Quantum measurement has exactly this three-part structure.

The *functional* is the observable you choose to measure: position, momentum, spin along the $z$-axis. This is the target parameter — the quantity you want to extract from the DGP. Different choices of observable correspond to different functionals of the same underlying DGP, just as different econometric questions (mean, quantile, treatment effect) target different functionals of the same data-generating process.

The *estimator* is the measurement apparatus: a detector, a Stern-Gerlach magnet, a photon counter. This is the procedure that implements the functional — the specific protocol that converts the quantum state into an outcome. The Riesz representer from Essay 1 plays its role here: the measurement operator — the position eigenstate $|x_0\rangle$, or more generally the eigenprojection of the observable — is the representer that extracts the target functional from the DGP. The inner product $\langle x_0 | \psi \rangle$ is the "influence" of the DGP on this particular functional.

The *realization* is the outcome: the click of the detector, the pointer reading, the eigenvalue you observe. This is a single data point drawn from the probability distribution $|\langle x | \psi \rangle|^2$ that the DGP specifies. The Born rule — which says the probability of outcome $x$ is $|\langle x | \psi \rangle|^2$ — is the sampling distribution of this DGP. It is a Pythagorean decomposition: the probability is the squared norm of the component of $|\psi\rangle$ in the direction of $|x\rangle$. This is the Pythagorean theorem in Hilbert space, the same geometry that governs the efficiency of semiparametric estimators — but here it functions as the sampling distribution of the DGP, not a property of the population.

"Collapse" is conditioning the DGP on the observed realization. Before measurement, $|\psi\rangle$ specifies a probability distribution over all possible outcomes. After the outcome $x_0$ is observed, the DGP updates: $|\psi\rangle \to |x_0\rangle$. Information is lost because the post-measurement DGP $|x_0\rangle$ retains only the information compatible with the observed outcome; the rest is discarded. This is why the process is irreversible — just as conditioning a joint distribution on one variable discards information about the marginal of the other.

This does not solve the measurement problem — it does not explain why a definite outcome occurs, as opposed to the system remaining in superposition. But it clarifies the *mathematical structure*: the quantum state is the DGP, the observable is the functional, the apparatus is the estimator, the outcome is a realization, and collapse is conditioning. The "mystery" is not the mathematics. The mystery is why the universe insists on computing estimates — why nature commits to a definite outcome at each interaction, rather than leaving the DGP unrealized.

---

## 6. Speed of light as a mixing condition

In time series econometrics, we rely on mixing conditions to ensure that observations far apart in time become effectively independent. $\alpha$-mixing, $\beta$-mixing, and their variants guarantee that the dependence between $X_t$ and $X_{t+k}$ decays as $k$ grows. Without these conditions, the Law of Large Numbers and the Central Limit Theorem fail: the variance of sample averages does not shrink, and consistent estimation becomes impossible.

The speed of light $c$ is the physical mixing condition — and a remarkably strong one.

Unlike standard mixing conditions in econometrics, which assert *asymptotic decay* of dependence, $c$ enforces a hard cutoff: two events separated by a spacelike interval — a spatial distance $d > c \cdot \Delta t$ — are *exactly* causally independent. No signal, no force, no influence of any kind can connect them. This is not asymptotic decay but exact independence beyond the light cone.

If $c$ were infinite, every point in the universe would be instantaneously correlated with every other point. This would be a long-memory process with infinite metric entropy — the physical analog of a non-ergodic time series. In such a universe, local patterns could not stabilize, because every local region would be buffeted by influences from arbitrarily distant sources. The metric entropy of the local environment would be unbounded, and no finite sieve could approximate the state of any region to any useful accuracy. The universe would be "unlearnable."

Finite $c$ regularizes the dependence structure. It ensures that the local environment of any observer has bounded metric entropy — that the number of "effectively independent" degrees of freedom within a light cone is finite. This is what makes local physics *Donsker-stable*: the empirical process within a light cone converges to a well-defined limit, just as the empirical distribution of a mixing time series converges to the population distribution.

This observation suggests something deeper. In econometrics, we usually take the index set (time, or a cross-section) as given and study the dependence structure of random variables defined on it. In physics, the index set is spacetime — and the dependence structure is the light cone. But what if we reverse the logical order? What if the dependence structure is the primitive object, and geometry is *induced* from it? One could start with a net of local information sets — one for each spacetime region — and define "spacelike separation" as exact statistical independence, "causal connection" as nonzero dependence, and "distance" as a decay rate. The light cone would then be *reconstructed* from the support of the dependence kernel, not assumed. This is a program worth pursuing, and the next essay will take it up directly.

The key distinction, which resolves the entanglement "paradox," is between the *level* of the process and the *innovation* of the process. The quantum state (the "level") can be globally correlated — this is entanglement, a property of the sieve basis. But *new information* (the "innovation") propagates at most at speed $c$. When you measure one entangled particle, you learn something about the other — but you cannot *transmit* new information to the other faster than $c$. The measurement outcome at A is correlated with the outcome at B, but the correlation was baked into the global basis from the start. No new signal was sent.

---

## 7. Correlation is not causation: why entanglement doesn't violate *c*

This is the section that ties the argument together.

The "paradox" of entanglement is the appearance of instantaneous influence across space: measuring particle A seems to "cause" particle B to collapse into a definite state, regardless of the distance between them. This appears to violate the speed of light.

The resolution, in the sieve framework, is the distinction between two different things:

The **sieve basis** is global. The quantum state is expanded in basis functions that span the entire space. Cross-terms between distant regions are built into the expansion. When the state is prepared (when the entangled pair is created), these cross-terms are established. They are *correlations in the basis expansion*, not signals traveling through space.

The **innovation process** is local. New information — the outcome of a measurement, the result of an interaction — propagates at most at speed $c$. You cannot use entanglement to send a message faster than light. The no-communication theorem proves this rigorously: the reduced density matrix of particle B is unchanged by any measurement performed on particle A. The correlations only become *visible* when the outcomes at A and B are later compared — and that comparison requires a classical signal, which travels at most at $c$.

This is the physical incarnation of "correlation is not causation." Entangled particles are correlated — their measurement outcomes are statistically dependent. But no causal influence travels between them. The correlation is a property of the joint basis expansion, not evidence of a signal.

An econometric analogy: two time series $X_t$ and $Y_t$ can be correlated (they share common factors, or were initialized from the same source) without either causing the other. Observing $X_t$ gives you information about $Y_t$ — but only because of the shared structure, not because $X_t$ transmitted a signal to $Y_t$. The "spookiness" of entanglement is exactly the confusion between correlation and causation, played out in the physical universe.

A brief speculative remark: the Maldacena-Susskind ER=EPR conjecture (2013) proposes that, in certain holographic theories, quantum entanglement between spatially separated systems (EPR correlations) is dual to a geometric wormhole (Einstein-Rosen bridge) in a higher-dimensional bulk spacetime. This does not mean entangled particles are literally connected by wormholes in our spacetime; rather, it suggests a deep duality between entanglement structure and geometric connectivity in the space of theories. If something like this holds more broadly, the "disconnected support" of spacelike-separated regions may be an artifact of a low-dimensional description. This remains a conjecture within the AdS/CFT framework, but it is suggestive of how the geometry of identification may be richer than it appears.

---

## 8. The information paradox: does the DGP preserve identifiability?

The deepest test case for the GR/QM conflict is the black hole information paradox — and it directly challenges the conclusion of Essay 2.

In Essay 2, I argued that "fundamentally unidentifiable means nonexistent": if the no-hair theorem is correct, the detailed initial configuration of a collapsed star is unidentifiable from the exterior, and therefore empirically vacuous. But that argument was made entirely within GR — the structural model. What happens when we bring in the DGP?

Hawking's 1974 calculation showed that black holes radiate. The radiation has a thermal spectrum — it looks like blackbody radiation characterized solely by the black hole's temperature, which depends only on its mass. If Hawking radiation is truly thermal, then it carries no information about the initial state: the radiation is the same regardless of what fell in. In this scenario, the DGP itself suffers identification failure — information is genuinely destroyed, and the quantum state of the universe is no longer unitarily evolving.

This would be catastrophic for quantum mechanics. Unitarity — the requirement that quantum evolution preserves the inner product, and hence preserves distinguishability of states — is the QM analog of point-identifiability. If unitarity is violated, the DGP loses the ability to distinguish between different initial states. The finite-sample process itself would suffer the same identification failure as the population structural model.

Most physicists believe information is not destroyed, based on consistency arguments with unitarity and results from string theory (the AdS/CFT correspondence). The conjecture is that Hawking radiation is *subtly non-thermal*: it carries extremely finely encoded information about the initial state, so delicate that it looks thermal to any practical measurement. If this is correct, then in principle the full quantum state is recoverable — unitarity is preserved, and the DGP maintains point-identifiability. However, the mechanism by which information escapes remains unresolved. This is the information paradox, one of the deepest open problems in quantum gravity.

In econometric language: the true DGP always preserves the ability to distinguish between different structural specifications — even in regimes where the structural model (GR) predicts identification failure. The "nonexistence" of black hole hair, argued in Essay 2, turns out to be an artifact of GR's breakdown as a structural model near the horizon, not a feature of the underlying DGP.

This is the deepest tension between the structural model and the DGP, and it cuts directly to the reconciliation problem. A consistent specification of quantum gravity must produce a DGP in which:

- Black holes form and evaporate as GR predicts (structural model consistency).
- Information is preserved throughout the process (DGP identifiability / unitarity).
- The exterior observer sees thermal-looking radiation (apparent identification failure at the structural model level).
- But the full quantum state encodes everything (no true identification failure at the DGP level).

The specification must reconcile *apparent* identification failure (structural) with *actual* identifiability preservation (DGP). This is the information paradox, stated in econometric terms.

There is a deeper tension lurking here, which goes beyond GR versus QM. The **second law of thermodynamics** insists that entropy increases — that time has a direction (the **Arrow of Time**), and that information, once scrambled, becomes practically irrecoverable. Neither GR's field equations nor QM's unitary evolution contain this arrow: both are time-reversible at the level of their fundamental dynamics. The information paradox is really asking which wins at the most fundamental level: unitarity (information is preserved, the arrow of time is an artifact of coarse-graining) or the second law (information is genuinely lost, and time's direction is built into the DGP itself). 

This three-way tension — between GR, QM, and thermodynamics — deserves its own treatment, and the spacetime filtration framework developed in the next essay will provide a natural language for it: a filtration is inherently directional, and the question becomes whether the growth of the filtration reflects genuine information creation or merely the redistribution of information already present.

---

## 9. What reconciliation requires

The three essays have built a layered picture.

Essay 1 established the estimation perspective: quantum mechanics and nonparametric statistics share the same mathematics — Fourier uncertainty, bias-variance tradeoffs, sieve approximation, the Riesz representer. What exists is what can be *estimated*: resolved from noise at the resolution you can afford.

Essay 2 established the identification perspective: general relativity and structural econometrics share the same mathematics — structural models, gauge freedom, partial identification, the no-hair theorem. What exists is what can be *identified*: recovered from the structural model, even with infinite data.

This essay has reframed the conflict between the two using our econometric framework and language, and in doing so, has assembled a specification sheet for what reconciliation would look like. A consistent theory of quantum gravity — in econometric terms, a consistent DGP specification — must satisfy:

**Consistency.** The DGP must recover the GR structural model in the population limit ($n \to \infty$, $\hbar \to 0$). The identified functionals of GR must be the population limits of the DGP's estimable functionals.

**Well-posedness.** The DGP must be well-defined at every finite resolution. The sieve Riesz representer norms must stay finite everywhere, including at singularities where GR diverges. The Planck scale provides the mesh size $\varepsilon$ that regularizes the divergences.

**Global sieve structure.** The DGP must accommodate quantum states expanded in a global basis — entanglement, superposition, and wave-particle duality must all emerge naturally from the basis structure of the Hilbert space.

**Causality / mixing.** The innovation process of the DGP must respect $c$ as a mixing condition. No new information propagates faster than light, even though the sieve basis is global.

**Unitarity / identifiability preservation.** The DGP must preserve point-identifiability of the quantum state at all times — including through black hole formation and evaporation. Information is never truly destroyed; "identification failure" at the structural level is always apparent, never fundamental.

**Directionality.** The DGP must account for the arrow of time — the empirical fact that entropy increases and macroscopic processes are irreversible — even though both GR and QM are time-reversible at the level of their fundamental equations. As discussed in Section 8, this is a third tension that sits alongside the GR/QM conflict. In filtration language, the DGP must explain why the filtration $\mathcal{G}_t \subseteq \mathcal{G}_{t+1}$ grows in one direction: whether the arrow reflects genuine innovation (new randomness entering the system) or coarse-grained redistribution of information already present. The specification must be compatible with both unitarity (fine-grained information preservation) and the second law (coarse-grained entropy increase).

These six requirements are not new to physics. Consistency is what any "classical limit" must deliver. Well-posedness is what singularity resolution requires. Unitarity is what the information paradox demands. Causality is what special relativity enforces. Directionality is what thermodynamics insists on. What the econometric framework adds is not the requirements themselves, but the *language* in which they are stated — a language that makes precise the relationships between population and sample, structure and data, identification and estimation.

The econometric reframing suggests that the GR/QM conflict can be viewed as a specification problem — perhaps the deepest one in science. It asks: does there exist a DGP that is simultaneously a consistent estimator for the GR structural model and a well-posed stochastic process at every finite resolution? The semiparametric toolkit — sieve spaces, representer norms, identified functionals, mixing conditions — provides a vocabulary for this question that is precise, operational, and connects two theoretical frameworks that have, until now, been studied in isolation.

Whether this vocabulary leads to new physics or remains a clarifying metaphor, I cannot say. But I believe the reframing is worth something: it identifies what reconciliation *requires*, in terms that an econometrician can verify and a physicist can operationalize. And the identification of requirements is itself a step toward the solution.

One requirement in particular points toward a concrete program. The causality/mixing condition — that the speed of light defines the support of the dependence kernel — suggests that geometry itself might be *derived from* stochastic dependence rather than assumed as a background structure. In econometrics, we routinely study dependence structures indexed by time or space: $\alpha$-mixing coefficients, covariance kernels, filtrations. What if we apply the same machinery to spacetime itself? Assign a local $\sigma$-field to each region, define causal order from the support of the dependence between regions, and reconstruct the Lorentzian metric from the rate at which dependence decays. This would be a dependence-first axiomatization of spacetime geometry — and it is the subject of the next essay.

*What exists is what admits a consistent DGP whose population limit is the structural truth.*

**Epistemology is ontology — in every regime.**

---
