# Spacetime Joint Filtration III: From Real to Complex

*Wayne Gao*

*I'm thankful to Claude, Gemini, and ChatGPT for discussing these ideas with me and helping me construct this essay.*

---

## 1. The elephant in the room

The previous two essays developed a dependence-first reconstruction of spacetime geometry. The primitive object was a finite causal-dependence network — a DAG with local observables, partially overlapping $\sigma$-fields, conditional spacelike factorization, and cone-supported weak dependence. In the population limit, the support of dependence recovered the conformal light-cone structure (Malament 1977), and the decay rate of dependence recovered metric scale. The reconstruction chain was:

$$
\text{finite DAG} + \text{local } \sigma\text{-fields}
\;\xrightarrow{n \to \infty}\;
\text{continuum net}
\;\xrightarrow{\alpha_C}\;
[g]
\;\xrightarrow{D_{\text{BL}}}\;
g.
$$

But this entire framework lived at the level of **real-valued probability**. The primitive objects were random variables $X_v \in \mathbb{R}$, $\sigma$-fields, conditional expectations, covariances, and mixing-type dependence coefficients. This is the right language for classical stochastic dependence. It is not yet the right language for quantum mechanics.

Quantum theory does not begin with probabilities. It begins with **complex amplitudes**. The wavefunction $\psi \in H$, where $H$ is a complex Hilbert space, is not itself an observable. It is a global amplitude object whose squared modulus produces observable probabilities through the Born rule: $P = |\psi|^2$. The previous essays reconstructed geometry from the **Born-rule shadow** of the quantum world — the real-valued probabilities that survive after the complex structure has already done its work — not from the full amplitude structure itself.

This essay confronts that gap. The goal is not yet a full theory of quantum gravity. It is more modest and more precise: to identify the algebraic lift that takes the dependence-first framework from real probability to complex amplitude, and to clarify how a **global complex sieve** coexists with **local information**.

---

## 2. Global sieve versus local information

A wavefunction is "everywhere" in a sense that a local random variable is not. It is naturally expanded in a basis:

$$
\psi = \sum_{k} \alpha_k \, b_k,
$$

where the $b_k$'s are global basis functions and the coefficients $\alpha_k$ are complex amplitudes. This is exactly a **sieve expansion** in the sense of Essay 1, except that the coefficients are complex and the basis functions are not probabilities but amplitude modes.

This structure should be familiar from econometrics and signal processing. When we represent a time series as

$$
X_t = \sum_k \alpha_k \, e^{i\omega_k t},
$$

the Fourier basis is global — it extends over all of time — but the actual data are still local-in-time realizations. No one thinks the global basis means the observer has global information at each instant. The basis is a **representational instrument**, not an epistemic state. What the observer knows at time $t$ is determined by the local filtration $\mathcal{F}_t$, not by the existence of a global Fourier decomposition.

An even more direct analogy comes from the **characteristic function** of a probability distribution. The density $f(x)$ is the real-valued, locally interpretable object — the thing we estimate from data. Its Fourier transform, the characteristic function

$$
\varphi(t) = \int e^{itx}\, f(x)\, dx,
$$

is complex-valued, globally defined over all frequencies, and encodes the entire distributional content of the DGP — all moments, all tail behavior, everything. Yet no one confuses $\varphi(t)$ with the data, or with the density itself. It is a **complex representational instrument** for the distribution, not the distribution. The density is recovered by inverse Fourier transform: $f(x) = (2\pi)^{-1} \int e^{-itx} \varphi(t)\, dt$ — a projection from the complex specification back to the real, locally interpretable object. The CLT is proved via characteristic functions precisely because the complex domain is where the key operation (multiplication of independent contributions) is algebraically natural; the real-valued limiting Gaussian density is the result, not the workspace.

The same distinction applies to the wavefunction. The quantum state $\psi$ is global in representation, but it is not global in information. It is better understood as a **global sieve specification of the latent process** — the DGP's amplitude-level description — whose Born-rule projections generate local informational content. The relationship $\psi \xrightarrow{\text{Born}} |\psi|^2$ is structurally the same as $\varphi(t) \xrightarrow{\text{inverse Fourier}} f(x)$: a complex global specification projected onto a real local object.

This suggests a three-layer hierarchy:

$$
\text{global complex amplitude}
\;\longrightarrow\;
\text{local probability law}
\;\longrightarrow\;
\text{local information (filtration)}.
$$

Or, in words:

- the global wavefunction is the amplitude-level sieve specification;
- the Born rule turns amplitude into local probability;
- the local filtration records realized, updated information.

This resolves an ambiguity in the earlier essays. The overlapping spacetime filtration $\{\mathcal{G}(v)\}$ is not the whole of quantum theory. It is the **informational shadow** — the real-valued, measurement-level residue — of a deeper global algebraic object. The filtration captures what has been observed and updated. The wavefunction captures what the DGP specifies as the full space of amplitudes, most of which no local observer ever sees.

**The wavefunction is global in representation, not global in information.**

---

## 3. The false conflation

Much of the apparent difficulty of quantum foundations may stem from a conflation of levels.

In classical probability, there is essentially one layer: a probability space $(\Omega, \mathscr{F}, \mathbb{P})$, random variables, $\sigma$-fields, and conditional expectations. Everything — specification, probability, information — lives in one real-valued framework. The specification *is* the probability law, and the probability law *is* what gets updated.

But even within classical probability, the two-layer structure already exists — it is just rarely noticed because the two layers happen to share the same (real) number field. The characteristic function $\varphi(t)$ is the specification-layer object: complex-valued, globally defined, encoding the full DGP. The density $f(x)$ and its empirical counterpart are the information-layer objects: real-valued, locally estimable, updated with data. Nobody confuses the characteristic function with the histogram, or wonders why $\varphi(t)$ doesn't "collapse" when a data point is observed. The two-layer separation is natural and unproblematic — because the layers are not conflated.

Quantum mechanics makes the separation unavoidable:

1. A **specification layer**: the complex amplitude state $\psi \in H$, which encodes phase, interference, and conjugation in addition to probabilistic content.
2. An **information layer**: the local measurements, filtrations, and realized data — all real-valued — that record what has actually been observed.

When these two layers are forced into one language, paradoxes multiply. The "measurement problem" asks: when does the global wavefunction "collapse" into a local outcome? But this is partly a language problem, arising from the attempt to treat the global sieve specification as if it were a local information object that must abruptly change upon observation. If the wavefunction is understood as a representational specification — analogous to a population regression function or a Fourier expansion — then the fact that local estimation produces a specific value from a global specification is not paradoxical. It is simply what estimation does.

The same confusion appears in debates about entanglement. If the wavefunction is treated as a global information state, then the correlation between distant measurements seems to require instantaneous information transfer. But if the wavefunction is a global specification of the DGP — not itself information held by anyone — then the correlated outcomes at distant sites are simply the local-estimation consequences of a globally specified dependence structure. No information travels. The global sieve specifies; the local filtration estimates.

**The mistake is to collapse the specification layer and the information layer into one probabilistic language.** Much of what makes quantum mechanics seem strange may be the artifact of this false conflation.

---

## 4. The algebraic lift: complex numbers as structured real operators

How, then, should the dependence-first framework be lifted from real probability to complex amplitude?

A useful starting point is that complex numbers are not a mysterious addition to reality. Every complex number can be represented as a real $2 \times 2$ matrix:

$$
a + ib
\quad\longleftrightarrow\quad
\begin{pmatrix}
a & -b \\
b & a
\end{pmatrix}.
$$

Equivalently, a complex Hilbert space can be viewed as a real Hilbert space $H_{\mathbb{R}}$ together with a distinguished linear operator $J$ satisfying

$$
J^2 = -I.
$$

This $J$ acts like multiplication by $i$. It is the internal rotation operator. Exponentiating it gives the one-parameter rotation group:

$$
e^{\theta J}
=
\begin{pmatrix}
\cos\theta & -\sin\theta \\
\sin\theta & \cos\theta
\end{pmatrix},
$$

which is exactly $SO(2) \cong U(1)$ — the group of planar rotations, or equivalently, of phase shifts.

So the lifting problem becomes:

> **Equip the real information space with an internal rotation structure $J$.**

This is important because it means the essay does not need to abandon the real dependence framework. It can **enrich** it with an additional algebraic operator. At the real level, one has filtrations, $\sigma$-fields, conditional expectations, and real observables. At the lifted level, one gains a real linear space of amplitudes, a complex structure $J$, conjugation, Hermitian pairing, and the possibility of unitary evolution. The lift is:

$$
(\text{real local information}) + J
\quad\Longrightarrow\quad
\text{complex global amplitude formalism}.
$$

### Cumbersome honesty

There is a philosophical point here that fits the spirit of the entire series.

The complex notation $a + ib$ is beautiful. It compresses oscillation, phase, rotations, conjugation, spectral theory, and unitary evolution into a single algebraic system. But beauty can hide structure. The $2 \times 2$ matrix representation refuses to let the notation do metaphysical work. It forces you to see what $i$ really is: not a mysterious "imaginary substance," but a **concrete rotation-generating linear operator**.

$$
i
\quad\leftrightarrow\quad
\begin{pmatrix}
0 & -1 \\
1 & 0
\end{pmatrix}.
$$

The matrix says, with no ornament: this structure is a real two-dimensional transformation law with a distinguished quarter-turn.

One of my mathematics professors once said: *"Mathematics is not about being smart and fast. It is about being stupid and slow."* The fundamental mathematics gives you a way to do things step by step with cumbersome honesty, and that reveals what the essence is. 

In the same spirit: **the complex formalism may not be ontologically fundamental; the structure it compresses is fundamental.** What matters is not "imaginary arithmetic" but the existence of a distinguished internal rotation symmetry — the $SO(2)$ or $U(1)$ Lie structure generated by $J$. Complex notation is the poetry; $J^2 = -I$ is the prose.

---

## 5. The Born map: from global amplitude to local probability

Given the algebraic lift, the relationship between the global sieve and local information becomes precise.

The wavefunction $\psi \in H$ is the global complex specification. It lives in the amplitude layer — the sieve space of the DGP. A local observable, associated with a spacetime region $O$, is represented by a Hermitian operator $A_O$ or a local projector $P_O$. The Born rule provides the bridge:

$$
\mathbb{P}_\psi(O) = \langle \psi,\, P_O\, \psi \rangle.
$$

This is where the global sieve touches local information. The local observable does not directly "see" the full global wavefunction. It sees only a **Hermitian quadratic form** of it — the modulus-squared projection. All phase information is discarded. What survives is a real-valued probability, which then enters the local filtration as realized data.

So the dependence-first framework of Essays 4–5 lives **downstream** of the Born map:

$$
\psi \in H
\quad\xmapsto{\text{Born}}\quad
\{\mathbb{P}_\psi(O)\}_{O}
\quad\xmapsto{\text{realization}}\quad
\{\mathcal{F}(O)\}_{O}.
$$

The overlapping spacetime filtration, the conditional independence structure, the $\alpha$-mixing coefficients, the $D_{\text{BL}}$ decay — all of these are properties of the Born-rule shadow, not of the full amplitude state. They see the probability-level projection of the DGP, not the phase-level specification.

This is not a deficiency. It is a clarification of scope. The dependence-first framework reconstructs geometry from what is **observable and estimable** — which is, after all, the thesis of the series: epistemology is ontology. But the observable-and-estimable layer is the Born-rule output, not the amplitude input. The amplitude layer is the specification; the probability layer is what identification and estimation can access.

---

## 6. Why conditional independence belongs to data, not to basis functions

A central lesson of the previous essays was that spacelike separation is conditional independence (Axiom L1). This is a statement about **local information**: given the common causal past, the local observables at spacelike-separated nodes are independent.

A natural question arises: what is the complex analogue of conditional independence? What does conditional factorization look like at the amplitude level?

The answer may be that this is the wrong question.

Conditional independence is fundamentally about information, observability, prediction, and the factorization of measurable events. These belong to the **local information layer** — the filtration, the measurements, the real-valued data. They do not naturally belong to the global sieve layer.

Consider the analogy from time series. If I represent a time series in a Fourier basis,

$$
X_t = \sum_k \alpha_k \, e^{i\omega_k t},
$$

I do not ask whether the basis functions $e^{i\omega_k t}$ are conditionally independent of each other. That would be a category error. The basis is an instrument of representation — a coordinate system for the DGP specification. The dependence question belongs to the signal and the data, not to the basis. The same holds for characteristic functions: asking whether $\varphi_X(t)$ and $\varphi_Y(t)$ are "conditionally independent" is not the right question. The right question is whether the distributions $f_X$ and $f_Y$ — the real-valued, estimable objects — satisfy conditional independence. The characteristic function specifies; the density is where dependence is tested.

The same logic applies to quantum amplitudes. The wavefunction is a global sieve specification. Its basis components $\alpha_k b_k$ are representational coordinates. Asking for "complex conditional independence" among amplitude components may be forcing the global specification and the local information into the same language — which, as argued in Section 3, is precisely the false conflation that generates pseudo-paradoxes.

The cleaner architecture is:

- **Local information layer**: conditional independence, dependence, filtration, estimation. Real-valued. This is where Axioms L1 and L2 live.
- **Global specification layer**: wavefunction, amplitude, phase, complex structure. This is where the DGP is specified, not where data is generated or information is accessed.
- **The bridge**: the Born map, which is a projection/estimation operation — analogous to estimating a functional from a sieve approximation to an infinite-dimensional object.

**Trying to impose probabilistic factorization language directly on the global complex sieve may be an ill-posed question.** The result may appear "difficult" not because the answer is deep, but because the starting question belongs to the wrong layer.

---

## 7. Measurement as estimation, revisited

Essay 3 proposed that measurement is estimation. This essay can now make that idea precise within the layered framework.

If the wavefunction is a global complex sieve specification, then a measurement is not mystical collapse. It is the extraction of a local functional from a global specification — exactly what estimation does.

The formal analogy: the expectation value of a local observable $A$ in state $\psi$ is

$$
\langle A \rangle_\psi = \langle \psi,\, A\, \psi \rangle,
$$

which is a **quadratic functional** of the infinite-dimensional specification $\psi$, evaluated by projecting onto a local operator. This is structurally identical to estimating a functional $\theta(f)$ from a sieve approximation $\hat{f}_n = \sum_{k \leq K_n} \hat{\alpha}_k b_k$ to an infinite-dimensional nuisance parameter $f$ — the setup of Essay 1.

In sieve estimation:

- the population object is infinite-dimensional (the true function $f$);
- the sieve basis provides a finite-dimensional approximation;
- the functional of interest $\theta(f)$ is a specific summary;
- estimation projects the global specification onto this local target.

In quantum measurement:

- the specification is infinite-dimensional (the state $\psi \in H$);
- the observable is a specific Hermitian operator;
- the expectation value $\langle A \rangle_\psi$ is the specific summary;
- measurement projects the global amplitude onto this local functional.

So the "measurement problem" gets reframed:

> **How do local estimation procedures extract functionals from a global complex specification?**

That is a far better question than the usual collapse rhetoric. It does not ask "when does the wavefunction collapse?" — a question that presupposes the wavefunction is an information state that must change upon observation. It asks instead how local observers, with their filtration-indexed information, extract estimable quantities from a global specification that they never fully access. And the answer is: through the Born map, which is a projection operation.

The apparent randomness of quantum measurement is then the same phenomenon as sampling variability in finite-sample estimation: the global specification determines the distribution, but the individual realization is stochastic.

---

## 8. Unitarity, reversibility, and the arrow of time

A standard axiom of quantum mechanics is that time evolution is unitary:

$$
\psi(t) = U(t)\, \psi(0), \qquad U(t)^* U(t) = I.
$$

Unitarity preserves the norm of the amplitude vector, which means total probability is conserved. It also implies reversibility: if $U(t)$ evolves the state forward, $U(t)^{-1} = U(t)^*$ evolves it backward. Quantum evolution loses no information.

This seems to conflict with the arrow of time. Essay 5 discussed the Cauchy-temporal filtration:

$$
\mathcal{G}_{t_1} \subset \mathcal{G}_{t_2} \qquad (t_1 < t_2).
$$

This filtration grows monotonically. It does not shrink. The second law of thermodynamics — the empirical fact that entropy increases with time — is the macroscopic expression of this directional growth. How can the specification be reversible if the information is irreversible?

The layered architecture of this essay dissolves the tension. **Unitarity is a property of the specification layer. The arrow of time is a property of the information layer.** There is no contradiction, because the two layers are distinct.

The analogy with GR is exact. The Einstein field equations are time-reversible: given a solution, the time-reversed solution is also valid. GR, as a population structural model without noise, has no preferred arrow of time. But this does not prevent the physical universe — the realized, noisy, finite-sample world — from exhibiting a clear thermodynamic arrow. The reversibility of the structural equations and the irreversibility of realized information coexist without tension, because they operate at different levels: one describes the noiseless population model, the other describes what happens when local stochastic innovations $\varepsilon_v$ are realized.

The same holds for unitarity. The global amplitude specification — the wavefunction evolving under $U(t)$ — is the quantum analogue of the noiseless population structural model. It is perfectly natural for this specification to be time-reversible, just as it is perfectly natural for the Einstein equations to be time-reversible. The specification describes the DGP's structural law, not the realized data.

The arrow of time lives in the **local information layer**: in the filtration $\{\mathcal{G}(v)\}$ that records which stochastic innovations have been realized, in the local $\varepsilon_v$'s that generate new information at each node, and in the monotone growth of what has been observed. The second law is about these local epsilons and the randomness in local information. Once a stochastic innovation is realized and enters the filtration, it cannot be un-observed. The filtration grows. Entropy, as a measure of the information already accumulated, increases.

So the framework does not reject unitarity. It *locates* it: unitarity belongs to the global sieve specification, alongside the complex structure $J$, the amplitude expansion, and the Born map. The arrow of time belongs to the local information layer, alongside the filtrations, the conditional independence structure, and the dependence functionals. The apparent tension between them is an artifact of conflating the two layers — the same false conflation that Section 3 identified as the source of many quantum pseudo-paradoxes.

**Reversibility is a property of the specification. Irreversibility is a property of the information.** The population regression function is time-symmetric; the finite sample that estimates it is not. The Einstein equations are time-reversible; the thermodynamic universe that instantiates them is not. The unitary evolution of $\psi$ is time-reversible; the filtration that records local measurements is not. In each case, the resolution is the same: the specification describes the structural law; the information describes the stochastic realization. Both are real. Neither contradicts the other.

---

## 9. Crossing the boundary: phase, interference, and entanglement in the rotation framework

The previous sections identified the boundary between the real-valued dependence framework and the full quantum specification. The natural temptation is to stop at this boundary and say: phase, interference, and entanglement are "genuinely complex" phenomena beyond our reach. But this would betray the spirit of the entire essay. We have argued that the $2 \times 2$ rotation matrix is equivalent to the complex formalism and sufficient for everything the complex number does. The "cumbersome honesty" of the matrix is not a call to retreat — it is a call to advance with precision, carrying exactly the structural lifting that is needed and nothing more.

So this section does not stop at the boundary. It crosses it, working through each quantum phenomenon in the rotation framework, and identifies in each case the precise structural ingredient that the lifting provides. That ingredient is always and only the internal rotation operator $J$.

### Phase: the angular degree of freedom in $\mathbb{R}^2$

Consider the simplest possible case: a two-level quantum system (a qubit). Define two states:

$$
|\psi_1\rangle = \frac{1}{\sqrt{2}}\bigl(|0\rangle + |1\rangle\bigr), \qquad
|\psi_2\rangle = \frac{1}{\sqrt{2}}\bigl(|0\rangle + e^{i\theta}|1\rangle\bigr).
$$

In the computational basis $\{|0\rangle, |1\rangle\}$, both states produce the same measurement probabilities: $P(0) = P(1) = 1/2$. The Born-rule shadow in this basis is identical. A real-valued dependence framework, observing data generated by either state in this basis, would see the same distribution and the same dependence structure. The two states are **indistinguishable from their marginals in one basis**.

But they are not the same state. Measuring in a different basis — say $|\pm\rangle = (|0\rangle \pm |1\rangle)/\sqrt{2}$ — yields different probabilities. For $|\psi_1\rangle$: $P(+) = 1$, $P(-) = 0$. For $|\psi_2\rangle$ with, say, $\theta = \pi$: $P(+) = 0$, $P(-) = 1$. The states are perfectly distinguishable — but only through a measurement that accesses the relative phase.

This has a precise econometric analogue. Consider two DGPs that produce the same marginal distributions but different joint distributions. From the marginals alone, the joint structure is not identified. Phase is exactly this: **the joint structure of the amplitude that the marginal (single-basis) Born-rule probabilities cannot see.** It is the off-diagonal content of the DGP specification — the part that lives in the rotation generated by $J$, invisible to any single projection but detectable through cross-basis comparisons.

Now here is the key point: in the lifted framework, phase is not mysterious. It is completely concrete. In the $2 \times 2$ matrix language, the state $|0\rangle + e^{i\theta}|1\rangle$ assigns to the second component the real 2-vector $(\cos\theta, \sin\theta)$, which is the image of $(1,0)$ under the rotation $e^{\theta J}$. Phase *is* angular position in the internal $\mathbb{R}^2$ plane at each node. Different phases correspond to different orientations. The Born map projects out the angular information by squaring the modulus: $\|(a,b)\|^2 = a^2 + b^2$. Phase is what the modulus-squaring discards — the rotational position in the internal $SO(2)$ fiber.

What structural lifting is required to handle phase? Exactly one thing: **replace the scalar $X_v \in \mathbb{R}$ at each node with a 2-vector $Y_v \in \mathbb{R}^2$, equipped with the rotation operator $J$.** That is the entire lifting. No "imaginary numbers" need enter the ontology. The internal $\mathbb{R}^2$ carries an angular degree of freedom, and that angular degree of freedom is phase. The Born map is the norm-squaring that forgets the angle. Phase becomes identifiable not from a single basis measurement but from **multiple projections** — exactly as the joint distribution becomes identifiable not from marginals alone but from cross-moments. This is a standard identification problem, not a metaphysical mystery.

### Interference: vector addition before norm-squaring

When two amplitude paths contribute to the same outcome, the composition rule in the lifted framework is: **2-vectors add, then take the squared norm.** Write each path's amplitude as a real 2-vector $\vec{\alpha}_k = (a_k, b_k)$. The probability is:

$$
P = \|\vec{\alpha}_1 + \vec{\alpha}_2\|^2 = \|\vec{\alpha}_1\|^2 + \|\vec{\alpha}_2\|^2 + 2(\vec{\alpha}_1 \cdot \vec{\alpha}_2),
$$

where $\vec{\alpha}_1 \cdot \vec{\alpha}_2 = a_1 a_2 + b_1 b_2$ is the standard Euclidean inner product in $\mathbb{R}^2$. In complex notation, this inner product is $\text{Re}(\alpha_1^* \alpha_2)$ — but the real expression makes the geometry transparent.

The cross-term $2(\vec{\alpha}_1 \cdot \vec{\alpha}_2)$ is the **interference term**. It can be positive or negative, depending on the relative angle between the two amplitude vectors in the internal plane. When they are aligned, interference is constructive; when anti-aligned, it is destructive. The double-slit experiment is the canonical demonstration: at certain positions on the detection screen, the two path-amplitude vectors point in nearly opposite directions, and the total probability is less than the sum of individual path probabilities.

No classical probability model can produce destructive interference. In classical probability, if an outcome can occur via two mutually exclusive routes, probabilities add: $P = P_1 + P_2 \geq 0$. There is no cross-term because classical paths carry scalar (non-negative) probabilities, not 2-vectors. The violation is not statistical; it is structural.

What structural lifting is required? The same one as for phase: **the amplitude at each path is a 2-vector in $\mathbb{R}^2$, and the composition rule is vector addition followed by norm-squaring.** This is the minimal departure from classical probability. A classical model assigns non-negative scalars to paths and adds them. The lifted model assigns 2-vectors to paths and adds them in $\mathbb{R}^2$ — gaining an internal angular degree of freedom — then projects to probabilities by squaring the norm.

The interference term $\vec{\alpha}_1 \cdot \vec{\alpha}_2$ measures the **alignment of two amplitude vectors in the $SO(2)$ fiber**. The classical limit is the case where all amplitude vectors are confined to the positive real axis — where $b_k = 0$ for every path — and the cross-term reduces to $a_1 a_2 \geq 0$, always constructive. Destructive interference requires the second dimension — the $J$-component. Every interference experiment that has ever been performed is, at bottom, an empirical confirmation that the internal state space is two-dimensional (not one-dimensional) and rotationally structured.

The complex notation compresses this beautifully into $|\alpha_1 + \alpha_2|^2$. But the $2 \times 2$ matrix notation shows what is actually happening: **addition of 2-vectors in an internal plane, followed by norm-squaring.** The former is elegant; the latter is honest about the mechanism.

The characteristic function analogy from Section 2 sharpens the point. For independent random variables, characteristic functions multiply: $\varphi_{X+Y}(t) = \varphi_X(t) \cdot \varphi_Y(t)$. In the complex plane, multiplication composes rotational structure — phases add, moduli multiply. The density of $X + Y$ is then recovered by inverse Fourier transform. Interference arises from exactly this logic: amplitudes compose at the specification layer — where the natural operation is multiplicative and rotational — and then project to probabilities via the Born map. The classical limit is the case where both routes — composing upstairs in the specification and then projecting, or composing downstairs in the probability layer directly — give the same answer. The quantum case is where they diverge: the cross-term in $\|\vec{\alpha}_1 + \vec{\alpha}_2\|^2$ is the specification-layer residue that has no counterpart in the information-layer addition $P_1 + P_2$.

### Conjugation, entanglement, and the Riesz pairing

The place where the rotational lifting matters most — and where it connects back most directly to Essay 1 — is entanglement.

A maximally entangled bipartite state takes the form

$$
|\Phi\rangle = \frac{1}{\sqrt{d}} \sum_{i=1}^{d} |i\rangle \otimes |i^*\rangle,
$$

where $|i^*\rangle$ denotes the basis of the second subsystem conjugate to the basis $|i\rangle$ of the first, under the Riesz isomorphism $H \to H^*$. In Essay 1, the Riesz representation theorem was the central bridge between quantum mechanics and semiparametric estimation: every continuous linear functional on a Hilbert space is representable as an inner product with a unique representer. Here, the same theorem provides the algebraic scaffolding of entanglement: **one entangled subsystem is the Riesz representer of the other.**

What does conjugation look like in the rotation framework? In the $2 \times 2$ matrix language, complex conjugation of $a + ib$ gives $a - ib$, which corresponds to:

$$
\begin{pmatrix} a \\ b \end{pmatrix}
\;\xmapsto{\text{conjugation}}\;
\begin{pmatrix} a \\ -b \end{pmatrix}.
$$

This is reflection across the real axis — or equivalently, the replacement $J \to -J$. The conjugate space is the **rotation-reversed** version of the original. Entanglement pairs a system with its rotation-reversed copy.

This is entirely concrete. At each node of the entangled pair, the internal state is a 2-vector in $\mathbb{R}^2$. The entanglement structure says: if the first node's internal vector is $(a, b)$, the second node's internal vector is $(a, -b)$ — the $J$-reflection. The pairing is the canonical bilinear form that combines the two:

$$
\langle u, v \rangle = (u_1 v_1 + u_2 v_2) + i(u_1 v_2 - u_2 v_1) = g(u,v) + i\,\omega(u,v),
$$

where $g$ is the symmetric (Euclidean) inner product — which gives the real part — and $\omega$ is the antisymmetric (symplectic) form — which gives the imaginary part. In the rotation framework, both $g$ and $\omega$ are real bilinear forms on $\mathbb{R}^2$. The full sesquilinear inner product is their combination, and the entangled state $|\Phi\rangle$ is the canonical tensor that realizes this pairing.

So entanglement is a **structured coupling through the $J$-reflection**, not just strong correlation. It requires exactly two things beyond classical dependence: the internal 2-vector structure (for each subsystem) and the $J$-reflection that pairs them. These are the same ingredients as for phase and interference — the $\mathbb{R}^2$ fiber and its rotation operator — plus one additional operation: the reflection $J \to -J$ that distinguishes a space from its dual.

Again the characteristic function provides a clean guide. The joint characteristic function of a bipartite system is $\varphi_{X,Y}(s,t) = \mathbb{E}[e^{i(sX + tY)}]$. Independence means factorization: $\varphi_{X,Y}(s,t) = \varphi_X(s) \cdot \varphi_Y(t)$. Entanglement is non-factorization of the joint specification — but of a very specific kind, structured by the $J$-reflection. Complex conjugation of a characteristic function corresponds to sign-reversal of the argument: $\varphi_X(-t) = \overline{\varphi_X(t)}$. So the conjugation $(a,b) \mapsto (a,-b)$ that pairs entangled subsystems is, in characteristic-function language, pairing each spectral component with its conjugate frequency. The Riesz inner product $\langle u, v \rangle = g(u,v) + i\,\omega(u,v)$ is the Plancherel pairing viewed from the specification side: $\int |f(x)|^2\,dx = \int \varphi(t)\overline{\varphi(t)}\,dt$. Entanglement is the structure that makes this pairing non-trivial across subsystems.

### The Bell inequality as identification boundary

The Bell inequalities make the structural content of the lifting empirically testable. Classical dependence — dependence that can be explained by a shared real-valued hidden variable — can produce correlations up to a certain bound (Bell 1964). Quantum entanglement violates this bound (Aspect et al. 1982).

In the rotation framework, the origin of the violation is transparent. A classical hidden-variable model assigns scalar (one-dimensional) states to each subsystem. The correlations achievable from scalar states are bounded by the Bell inequality. But if each subsystem carries an internal 2-vector — an $\mathbb{R}^2$ amplitude with an angular degree of freedom — then the correlations achievable through the $J$-structured pairing are strictly larger. The Bell bound is the **maximum correlation achievable from one-dimensional (scalar) internal states**. The quantum violation is what happens when the internal state space is two-dimensional and rotationally structured.

In the language of this series: the Bell inequality is the **identification boundary** of the scalar (real, one-dimensional) dependence framework. Within that boundary, all observed correlations are consistent with a classical DGP. Beyond it, the correlations require a lifted DGP — one where the internal state at each node is a 2-vector in $\mathbb{R}^2$ equipped with the rotation operator $J$. The empirical violation of Bell inequalities is therefore the empirical proof that the internal state space of the DGP is (at least) two-dimensional with rotational structure. It is the proof that $J$ is physically real.

Note what the violation does *not* prove: it does not prove that reality is "made of imaginary numbers." It proves that the DGP specification requires an internal rotation structure. The complex number $i$ is one way to write this. The $2 \times 2$ matrix $J$ is another. The Bell violation discriminates between one-dimensional and two-dimensional internal structure. It is agnostic about notation.

In characteristic-function language: the Bell bound is the maximum correlation achievable when the joint specification factors through a shared one-dimensional (scalar) latent characteristic function. The quantum violation says the joint specification requires a two-dimensional, rotationally structured characteristic function — one whose internal $SO(2)$ degree of freedom generates cross-term correlations that no scalar representation can reproduce.

### What the lifting requires: an inventory

Let me collect what is needed. The classical (scalar) dependence framework of Essays 4–5 assigns to each node $v$ a real-valued random variable $X_v \in \mathbb{R}$ and constructs the dependence structure from the resulting $\sigma$-fields. To handle the genuinely quantum phenomena — phase, interference, and entanglement — the lifting requires exactly the following:

1. **Internal dimension**: Replace the scalar $X_v \in \mathbb{R}$ with a 2-vector $Y_v = (X_v^{(1)}, X_v^{(2)}) \in \mathbb{R}^2$ at each node. This is the minimal extension that supports an angular degree of freedom.

2. **Rotation operator**: Equip each internal $\mathbb{R}^2$ with the operator $J$ satisfying $J^2 = -I$. This generates the $SO(2)$ symmetry that is the structural content of phase.

3. **Composition rule**: Amplitudes (2-vectors) add in $\mathbb{R}^2$ before norm-squaring to produce probabilities. This is the source of interference.

4. **Conjugation**: The $J$-reflection $(a, b) \mapsto (a, -b)$ defines the dual pairing. This is the structural content of entanglement: one subsystem is paired with the $J$-reflected copy of the other.

5. **Born map**: Probabilities are obtained by squaring the $\mathbb{R}^2$ norm: $P = \|Y\|^2 = (X^{(1)})^2 + (X^{(2)})^2$. This is the projection from the specification layer to the information layer.

That is the complete inventory. Items 1–5 are equivalent to "use complex Hilbert space." But stating them in the rotation language makes visible what is structurally necessary and what is notational convenience. The necessary content is: **a two-dimensional internal state space with a distinguished rotation**. The notational convenience is: writing this as $a + ib$ rather than as a 2-vector with $J$. The convenience is real — complex notation compresses beautifully — but it is not the ontology.

Nothing in items 1–5 requires "imaginary substance." Nothing requires abandoning the real-valued information layer: the filtrations $\mathcal{F}(v)$ and $\mathcal{G}(v)$ of Essays 4–5 remain real-valued, generated by the Born-projected observables. What changes is the specification layer — the DGP — which gains an internal rotational structure. The information layer sees the shadow of this structure through the Born map. The geometry is still reconstructed from the shadow. But now we can say precisely what the shadow is a shadow *of*: a rotationally structured, two-dimensional amplitude field on the causal graph.

---

## 10. The layered ontology

Let me collect the architecture that has emerged across the three essays.

### Layer 1: Global structural grammar

The causal graph (finite) or manifold (continuum limit) that organizes locality and overlap. This is the DAG of Essay 4, or the globally hyperbolic spacetime of Essay 5. It provides the causal grammar — the rules governing who can influence whom and which information sets overlap.

### Layer 2: Global complex sieve specification

A state $\psi$ in a complex Hilbert space $H$, expanded in a global basis. This is the DGP specification at the amplitude level. It carries phase, interference, and conjugation. It is global in representation — like a Fourier expansion — but it is not global in information. No local observer has access to the full state. It is the latent specification, not the realized data.

### Layer 3: Local Born probabilities

For each spacetime region $O$, the state $\psi$ induces local measurement probabilities through region-localized projectors: $\mathbb{P}_\psi(O) = \langle \psi, P_O \psi \rangle$. This is the Born map — the projection from global amplitude to local probability. Phase information is discarded. What survives is real-valued.

### Layer 4: Local information and filtration

Actual realized observations generate the local $\sigma$-fields $\mathcal{F}(v)$ and accumulated past filtrations $\mathcal{G}(v)$ of Essays 4–5. Conditional independence, dependence decay, geometric reconstruction — all the results of the previous essays — live here. This is the epistemological layer: what can be identified and estimated.

In short:

$$
\text{causal structure} + \text{global complex amplitude}
\;\xrightarrow{\text{Born}}\;
\text{local probabilities}
\;\xrightarrow{\text{realization}}\;
\text{local information}.
$$

This preserves the earlier principle: **what is global is the structure, not the information.** But it adds a refinement: there is also a global amplitude object (the wavefunction). Yet even that amplitude object is not "global information" in the strong sense. It is a global representation — a latent sieve — not a globally accessible information set.

The distinction is essential. A Fourier expansion is global in representation but tells you nothing about what a local observer knows at a particular time. The wavefunction is global in representation but tells you nothing about what a local detector registers at a particular event. Global representation and global information are different things. Conflating them is the source of much confusion.

---

## 11. What geometry owes to amplitude

The previous essays showed that spacetime geometry is reconstructed from the real-valued dependence structure — the Born-rule shadow of the quantum state. This essay has argued that the full quantum specification lives upstream, in the complex amplitude layer.

This raises a natural question: does the geometry depend on the full complex specification, or only on its real-valued projection?

The answer, within this framework, is nuanced. The **conformal class** $[g]$ depends on the support of dependence — on which pairs of regions are dependent or independent — and this is determined by the Born-rule probabilities, which are real-valued. The **metric scale** $\Omega^2$ depends on the rate of dependence decay, which is again a property of the real-valued layer. So **geometry is reconstructed from the Born-rule shadow**, not from the full amplitude state.

But the amplitude layer determines *which* Born-rule shadow is produced. Different amplitude states $\psi$ and $\psi'$ may generate different dependence structures and therefore different geometries. The complex specification is the DGP; the real-valued dependence is its observable projection; the geometry is the sufficient statistic of that projection.

So the hierarchy is:

$$
\text{complex specification} \;\to\; \text{real dependence} \;\to\; \text{geometry}.
$$

Geometry is epistemology — it summarizes what can be known. But what can be known is determined by a deeper specification that carries more structure than what is knowable. The gap between specification and knowledge is precisely the gap between complex amplitude and real probability. It is the gap between the DGP and the estimable functionals — the same gap that semiparametric estimation theory, in Essay 1, taught us to navigate.

---

## 12. Closing

This essay has argued for a clean separation between two layers that quantum foundations has historically conflated: the **global complex sieve specification** and the **local real-valued information structure**.

The wavefunction is not local information. It is a global representational object — a sieve expansion in complex amplitude — that specifies the DGP at a level richer than what any local observer can access. Local information remains filtration-indexed, real-valued, and causal, arising only through measurement, which is best understood as estimation of local functionals from the global specification. The algebraic lift from real to complex is not the introduction of a mysterious imaginary substance; it is the enrichment of a real linear structure with an internal rotation operator $J$ satisfying $J^2 = -I$, whose deeper identity is the $SO(2)$ or $U(1)$ Lie symmetry of phase rotation. The complex notation is elegant syntax; the real-linear structure with internal rotation is the semantic core.

The dependence-first framework of the previous essays lives downstream of the Born map, in the epistemological layer — the layer of observable, estimable, real-valued dependence. This is where geometry is reconstructed. The complex amplitude layer lives upstream, in the specification layer — the layer of the DGP itself, with its full phase and interference structure. The bridge between them is the Born map: a projection from global amplitude to local probability, analogous to estimating a functional from a sieve approximation.

This series began with the thesis that **epistemology is ontology**: what exists is what can be identified and estimated. This essay adds that the DGP itself may carry more structure than what is epistemically accessible — that the complex specification is richer than its real-valued shadow. But the geometry, the dependence, and the information structure are all reconstructed from the shadow. The upstream specification shapes the downstream epistemology, but it is the epistemology — what can be identified from the dependence structure of a finite causal network — that constitutes the observable, learnable, estimable reality.

The next essay carries out the formal construction. It builds the lifted framework on the finite causal graph of Essay 4 — equipping each node with an internal $\mathbb{R}^2$ and rotation operator $J$, defining the lifted axiom system, and showing how interference, entanglement, and the Bell violation emerge as natural consequences of the rotational structure. It then demonstrates that the dependence framework of Essays 4–5 is recovered exactly as the Born projection of the lifted framework: the real-valued dependence structure is the shadow of a rotationally structured specification, and geometry is reconstructed from that shadow as before.

**Epistemology is ontology — and the specification of what lies beyond it is the algebraic lift from real to complex, from dependence to amplitude, from the Born-rule shadow to the full quantum sieve.**

---

### References

- Aspect, A., Dalibard, J., and Roger, G. (1982). Experimental realization of Einstein-Podolsky-Rosen-Bohm Gedankenexperiment: A new violation of Bell's inequalities. *Physical Review Letters*, 49, 1804–1807.
- Bell, J. S. (1964). On the Einstein Podolsky Rosen paradox. *Physics Physique Физика*, 1, 195–200.
- Benjamini, I., and Schramm, O. (2001). Recurrence of distributional limits of finite planar graphs. *Electronic Journal of Probability*, 6, 1–13.
- Bombelli, L., Lee, J., Meyer, D., and Sorkin, R. D. (1987). Space-time as a causal set. *Physical Review Letters*, 59, 521–524.
- Born, M. (1926). Zur Quantenmechanik der Stoßvorgänge. *Zeitschrift für Physik*, 37, 863–867.
- Bradley, R. C. (2005). Basic properties of strong mixing conditions: A survey and some open questions. *Probability Surveys*, 2, 107–144.
- Haag, R., and Kastler, D. (1964). An algebraic approach to quantum field theory. *Journal of Mathematical Physics*, 5, 848–861.
- Jacobson, T. (1995). Thermodynamics of spacetime: The Einstein equation of state. *Physical Review Letters*, 75, 1260–1263.
- Malament, D. B. (1977). The class of continuous timelike curves determines the topology of spacetime. *Journal of Mathematical Physics*, 18, 1399–1404.
- Pearl, J. (2009). *Causality: Models, Reasoning, and Inference*. 2nd edition. Cambridge University Press.
- Riesz, F. (1907). Sur une espèce de géométrie analytique des systèmes de fonctions sommables. *Comptes rendus de l'Académie des Sciences*, 144, 1409–1411.
