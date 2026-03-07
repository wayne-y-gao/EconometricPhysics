# General Relativity and Econometric Identification

*Wayne Gao*

*I'm thankful to Gemini and Claude for discussing these ideas and composing this essay.*

---

## 1. From estimation to identification

In the [first essay](essay_draft.md), I explored the parallels between quantum physics and semiparametric estimation. The shared mathematics was striking: the Fourier uncertainty principle, the bias-variance tradeoff as a Hamiltonian, metric entropy as the boundary of learnability, the Riesz representer as the mechanism for extracting finite-dimensional signals from infinite-dimensional noise. The punchline was that quantum mechanics and nonparametric statistics are both studying estimation under irreducible uncertainty — what I called the "finite-sample regime."

But modern physics has two pillars, and I had only touched one. The other is general relativity — Einstein's theory of gravity, spacetime curvature, and the large-scale geometry of the universe. And general relativity is nothing like quantum mechanics in one crucial respect: *it is deterministic*.

There is no noise in GR. No sampling variance. No Planck constant playing the role of $1/n$. The Einstein field equations, given a distribution of mass-energy and appropriate initial and boundary conditions, determine the geometry of spacetime. At the classical level, the theory is also time-reversible: you can run the equations forward or backward without losing information.

These features immediately remind me of an obvious econometric implication, one that I have personally written many papers on. If GR is deterministic and time-reversible, then the natural questions to ask about it are not questions of *estimation*. 

They are questions of *identification*.

---

## 2. General relativity as a structural model

In econometrics, a structural model specifies the causal mechanism that generates the data. The identification question asks: if we had access to the full population distribution — infinite data, no sampling noise — Could we uniquely recover the structural parameters? Or more generally: Are the models identified? Are the models overidentified? Are the structural parameters point or set identified? Are there counterfactual parameters that are point or set identified regardless of whether the structural parameters are?

General relativity is, in this precise sense, a structural model, for which we can ask all the identification-related questions above. The Einstein field equations

$$G_{\mu\nu} + \Lambda g_{\mu\nu} = \kappa T_{\mu\nu}$$

relate the stress-energy tensor $T_{\mu\nu}$ (the distribution of mass-energy in the universe) to the metric tensor $g_{\mu\nu}$ (the geometry of spacetime). The left-hand side encodes curvature; the right-hand side encodes matter. The equation says: given the matter content, the geometry is constrained.

In econometric terms, GR is a *parametric* structural model: the functional form $m(x;\theta)$ relating observables to structure is fully specified by the field equations. The metric $g_{\mu\nu}(x)$ is an infinite-dimensional object as a function of spacetime coordinates $x$, but within physically relevant solution families — Schwarzschild ($\theta = M$), Kerr-Newman ($\theta = (M, Q, J)$), FLRW cosmology ($\theta = (H_0, \Omega_m, \Omega_\Lambda, \ldots)$) — the solution space collapses to a *finite-dimensional* parameter $\theta$. The symmetry assumptions that produce these families (spherical symmetry, stationarity, homogeneity and isotropy) play the role of parametric restrictions in econometrics: they are what reduce an infinite-dimensional problem to a tractable finite-dimensional one.

But as every econometrician knows, the structural equation alone is never the full model. The "econometric model" includes every assumption needed to go from the equation to identification: regularity conditions, support restrictions, normalization conventions, equilibrium selection rules. GR is no different. The complete model specification consists of:

- The **structural equation**: the Einstein field equations themselves — the "functional form" of the model.
- The **normalization (gauge-fixing)**: the EFE has gauge freedom from diffeomorphism invariance — the same physical spacetime can be described in infinitely many coordinate systems. Fixing a gauge (harmonic coordinates, synchronous gauge, etc.) is exactly a normalization condition, analogous to fixing the scale of utility or the location of a distribution.
- The **initial and boundary conditions**: data on a Cauchy surface (a spacelike hypersurface from which the future and past are determined). Without these, the EFE is underdetermined, just as a structural equation without exclusion restrictions or initial conditions is underdetermined.
- The **regularity/shape restrictions (energy conditions)**: the weak energy condition (non-negative energy density), the strong energy condition (gravity is attractive), and the dominant energy condition (energy does not flow faster than light) constrain $T_{\mu\nu}$ to behave like physically reasonable matter. These are shape restrictions on the covariates, analogous to monotonicity, convexity, or boundedness assumptions in econometric models. They rule out pathological solutions that are mathematically valid but physically meaningless.
- The **equilibrium selection (cosmic censorship)**: Penrose's cosmic censorship conjecture asserts that singularities arising from gravitational collapse are always hidden behind event horizons — "naked singularities" do not form from generic initial conditions. (This remains a conjecture, not a theorem; counterexamples exist in special cases.) It functions as an equilibrium selection rule: among the many solutions to the EFE, it selects the "well-behaved" ones, just as equilibrium refinements in game theory (subgame perfection, trembling-hand perfection) rule out implausible Nash equilibria.
- The **support/topology assumptions**: global hyperbolicity, simple connectedness, orientability — these constrain the large-scale structure of the manifold, analogous to support conditions on the distribution of covariates.

With the full specification in place, the structural analogy is clean:

- The **structural parameter** is the metric $g_{\mu\nu}$ — the geometry of spacetime itself.
- The **covariates** are the stress-energy tensor $T_{\mu\nu}$ and the initial/boundary data — the matter distribution and the "initial conditions" of the universe.
- The **identifying restrictions** are the Einstein field equations together with gauge-fixing — the "laws of physics" plus normalization conventions that constrain the relationship between matter and geometry.
- The **reduced form** is geodesic motion — the observable paths of particles and light, which reveal the hidden geometry.

Determinism is not a bug here; it is a feature. Given $T_{\mu\nu}$, suitable initial data on a Cauchy surface, and a gauge choice, the metric $g_{\mu\nu}$ is (under reasonable regularity conditions) uniquely determined. This is *point identification*: the structural map is injective. At the classical level, time-reversibility follows naturally: the Cauchy problem for the EFE is well-posed both forward and backward, so you can recover the past from the present without information loss. (This reversibility breaks down once quantum effects — Hawking radiation, black hole thermodynamics — are introduced, but at the classical population level, it holds.) These are exactly the properties you expect of a well-identified structural model evaluated at the population level.

---

## 3. The equivalence principle: what cannot be identified locally

The first identification result in GR is negative, and it is one of the most famous results in all of physics.

Einstein's equivalence principle states that the effects of gravity are locally indistinguishable from acceleration. An observer in a sealed elevator cannot determine, from any local experiment, whether they are sitting in a gravitational field or accelerating through empty space. This is an *identification impossibility result*: the structural parameter "gravitational field" is not identified from local data.

The mathematics makes the non-identification precise. In GR, the gravitational "force" is encoded in the Christoffel symbols $\Gamma^\alpha_{\mu\nu}$, which are derived from the metric and determine how freely falling particles accelerate in a given coordinate system. Under a coordinate change $x^\mu \to x'^\mu$, the Christoffel symbols transform as

$$\Gamma'^\alpha_{\mu\nu} = \frac{\partial x'^\alpha}{\partial x^\sigma}\frac{\partial x^\rho}{\partial x'^\mu}\frac{\partial x^\lambda}{\partial x'^\nu}\Gamma^\sigma_{\rho\lambda} \;+\; \frac{\partial x'^\alpha}{\partial x^\sigma}\frac{\partial^2 x^\sigma}{\partial x'^\mu \partial x'^\nu}.$$

The key is the second term — the inhomogeneous piece involving second derivatives of the coordinate transformation. Because of this term, $\Gamma$ is *not* a tensor: its value depends on the coordinate system. And the inhomogeneous term has enough freedom that, at any single point $p$, one can always choose coordinates (Riemann normal coordinates) such that

$$g_{\mu\nu}(p) = \eta_{\mu\nu}, \qquad \Gamma^\alpha_{\mu\nu}(p) = 0,$$

where $\eta_{\mu\nu}$ is the flat Minkowski metric. These conditions hold exactly at $p$; the first derivatives of $\Gamma$ (which encode curvature) cannot all be made to vanish. In words: at any point, you can always find a "free-fall frame" in which gravity vanishes — but tidal effects, encoded in the derivatives, persist.

For an econometrician, this has a clean translation. Let $\mathcal{O}_p$ denote the set of all physical observables measurable in an infinitesimal neighborhood of a point $p$ — local particle trajectories, force measurements, light propagation. The equivalence principle says

$$\mathcal{O}_p\big(\text{gravitational field } g_{\mu\nu}\big) = \mathcal{O}_p\big(\text{flat spacetime } \eta_{\mu\nu} + \text{acceleration}\big).$$

The map from "gravitational field versus acceleration" to local observables is many-to-one. The identified set at $p$ is an entire equivalence class under coordinate transformations. The Christoffel symbols are *not identified* from local data, just as the level of a utility function is not identified from choice data — only objects invariant to the normalization (monotone transformations of utility, coordinate transformations of the metric) are identified. 

[As a self-advertisement, the relationship between identification, quotient space induced by equivalence, normalization, and sharp identification in econometric models has been formally treated and discussed in Appendix B of my research paper *Nonparametric Identification in Index Models of Link Formation*, available on arXiv  https://arxiv.org/abs/1710.11230. This paper was later published in the *Journal of Econometrics*, but this appendix on the general treatment of normalization was not presented in the journal article version.] 

So what *is* identified? The **Riemann curvature tensor** $R^\alpha{}_{\beta\gamma\delta}$. Unlike $\Gamma$, the curvature tensor is a genuine tensor — it transforms homogeneously under coordinate changes, so if $R = 0$ in one frame, it vanishes in all frames. You cannot make curvature disappear by a clever choice of coordinates.

The physical observable that identifies curvature is **geodesic deviation** — the relative acceleration of nearby freely falling particles. Two particles with separation vector $\xi^\alpha$ satisfy

$$\frac{D^2 \xi^\mu}{d\tau^2} = R^\mu{}_{\nu\rho\sigma}\, u^\nu\, u^\sigma\, \xi^\rho,$$

where $u$ is the tangent to the geodesic (4-velocity), $\xi$ is the separation vector, and $D/d\tau$ is the covariant derivative along the worldline. (The sign depends on the Riemann tensor convention; I follow Carroll's.) This equation involves only $R$ (identified) and measurable quantities ($\xi$, $u$). It is the "moment condition" that identifies curvature from data. Geodesic deviation is the tidal force — the stretching and squeezing that distinguishes a gravitational field from uniform acceleration. You cannot detect gravity at a point, but you *can* detect it by comparing nearby points: curvature is identified from *variation across the support*, not from a single observation.

The identification structure of GR is therefore layered:

| Object | Identified? | Econometric analog |
|---|---|---|
| Christoffel symbols $\Gamma^\alpha_{\mu\nu}$ | No (gauge-dependent) | Level of utility function |
| Riemann curvature $R^\alpha{}_{\beta\gamma\delta}$ | Yes (tensor) | Marginal rate of substitution |
| Geodesic deviation equation | Moment condition | Revealed preference condition |

This is, in my view, the cleanest example of the identification perspective at work in GR. The equivalence principle is not a vague philosophical statement about the "nature of gravity." It is a sharp, mathematically precise non-identification result: certain components of the structural model are gauge-dependent and cannot be pinned down from any local data. Only the gauge-invariant objects — the curvature, and the functionals derived from it — are identified. In econometrics, especially discrete choice models, we deal with the embodiments of exactly the same (non)identification results all the time.

---

## 4. The Riesz representer as a population object

Here is a point that connects the two essays, and that I think is worth emphasizing: the Riesz representer is a *population* object. It does not require randomness. It does not require a sample. It is defined purely by the geometry of the Hilbert space and the continuity of the functional.

In the first essay, I used the Riesz representer in the context of estimation — extracting a $\sqrt{n}$-estimable functional from an infinite-dimensional nuisance. But the representer is equally meaningful in the context of identification. Given a functional $\nu(m) = \langle \alpha, m \rangle$ on a Hilbert space, the representer $\alpha$ tells you *how* the functional depends on the underlying function $m$. It tells you which directions in function space matter for the quantity of interest, and which are "nuisance."

In GR, the spacetime manifold $(\mathcal{M}, g)$ serves as the domain on which fields are defined. The metric $g_{\mu\nu}$ determines the inner product on the relevant $L_2$ space:

$$\langle m_1, m_2 \rangle_g = \int_{\mathcal{M}} m_1(x) \, m_2(x) \sqrt{|g|} \, d^4x.$$

For perturbations around a fixed background metric, the Riesz representer for a physical observable — say, the total energy in a region, or the deflection angle of a light ray — is the Green's function of the linearized Einstein equations. It tells you how a small perturbation in the matter distribution shifts the observable. This is exactly the pathwise derivative, the population influence function — and it is well-defined without any randomness at all. (The caveat: this linearized picture is valid for small perturbations. For large-amplitude phenomena like black hole mergers, the full nonlinear equations are needed. That said, in econometrics there is also work that deals with highly nonlinear systems with structural changes and singularities.)

The physics literature calls this the "propagator" or "response function." The econometrics literature calls it the influence function or the Riesz representer. They are the same object, living in the same Hilbert space, doing the same work: extracting a finite-dimensional signal from an infinite-dimensional background.

---

## 5. Gravitational lensing: identification in practice

The previous sections laid out the abstract framework. Here is a concrete application — one that hit close to home when I had a "Dining-across-divisions" lunch on February 25 with Gary Bernstein, an astrophysicist at Penn who works on exactly this problem. 

Mass curves spacetime, and curved spacetime bends light. A massive galaxy cluster sitting between us and a distant background galaxy acts as a gravitational lens: the background galaxy's image is distorted — stretched, magnified, sometimes split into multiple copies. The distorted image is the *reduced form*. The mass distribution of the cluster is the *structural parameter*. The question of gravitational lensing is: can we recover the mass distribution from the distorted images?

In weak lensing — the regime where distortions are small — the answer involves exactly the tools of this essay. The lensing convergence $\kappa(\boldsymbol{\theta})$, which is proportional to the projected surface mass density $\Sigma$ along the line of sight, relates to the lensing shear $\gamma(\boldsymbol{\theta})$ (the measurable tidal distortion of galaxy shapes) through a known integral operator. The Green's function of this operator — the lensing kernel — is the Riesz representer for the convergence functional. It tells you how a point mass at one location on the sky contributes to the shear at another location. Inverting this operator to recover $\kappa$ from the observed $\gamma$ is a textbook inverse problem — the structural-to-reduced-form inversion that identification theory is built for.

But here is where the identification story gets interesting. The key observable in weak lensing is not the shear $\gamma$ itself (which requires knowing the intrinsic shapes of galaxies), but the *reduced shear*

$$g = \frac{\gamma}{1 - \kappa}.$$

And the reduced shear is invariant under the **mass-sheet degeneracy**: the transformation

$$\kappa(\boldsymbol{\theta}) \;\to\; \lambda\,\kappa(\boldsymbol{\theta}) + (1 - \lambda), \qquad \gamma(\boldsymbol{\theta}) \;\to\; \lambda\,\gamma(\boldsymbol{\theta})$$

leaves $g$ unchanged for any scalar $\lambda \neq 0$. This means: from shear observations alone, the convergence $\kappa$ is **not point-identified**. The identified set is a one-parameter family $\{\kappa_\lambda : \lambda \in \mathbb{R} \setminus \{0\}\}$ — infinitely many mass distributions, all producing the same lensing signal.

This is partial identification. The structural model (GR lensing equations) plus the available data (galaxy shapes) do not uniquely pin down the mass distribution. Additional information is needed to break the degeneracy: magnification measurements, source number counts, or combining lensing with other probes (X-ray, Sunyaev–Zel'dovich effect). Each additional data source is an extra moment condition that shrinks the identified set — the same logic as adding instruments or exclusion restrictions in econometrics.

What I find striking is that the astrophysicists working on weak lensing have, independently, developed exactly the identification reasoning that econometricians use: they distinguish between what the data can and cannot pin down, they characterize the equivalence classes of observationally indistinguishable models, and they design observation strategies specifically to break degeneracies. The language is different — they say "degeneracy" where we say "partial identification," "complementary probes" where we say "additional moment conditions" — but the mathematical structure is the same.

---

## 6. Black holes as identification failure

If GR is a structural model and the metric is the structural parameter, then a black hole is the most dramatic identification failure in nature.

The event horizon prevents causal signals from the interior from reaching an external observer. In econometric language, this is a **causal support truncation**: for any observer outside the horizon, the field values, particle trajectories, and light signals from the interior are permanently unobservable. The domain $\mathcal{M}$ splits into two causally disconnected components: the exterior (observable) and the interior (hidden). No influence function can propagate from the interior to the exterior. The information inside is excluded from any likelihood, any moment condition, any functional that an external observer can evaluate.

This is not merely a disconnected support problem. Disconnected supports are fine if you can sample from both components. The issue here is deeper: the interior is not just observationally incomplete — it is **causally inaccessible**. No instrument, no additional moment condition from the exterior can bridge the gap. The missing data is not missing at random — it is missing by the causal structure of spacetime itself. This is a loss of **ergodicity**, one of the most profound concept in time series econometrics and even the whole statistics.

At the singularity, the situation is worse. The curvature diverges, the metric degenerates, and the Riesz representer for any functional that "reaches into" the singularity has infinite norm. In the language of the first essay, this is the ill-posed inverse problem pushed to its limit: the sieve Riesz representer $\alpha_J$ cannot approximate a target that has left the Hilbert space entirely.

---

## 7. The no-hair theorem is sharp identification

The **no-hair theorem** states that a stationary black hole in GR is completely characterized by three numbers: its mass $M$, charge $Q$, and angular momentum $J$. No matter how complex the star that collapsed to form the black hole — its chemical composition, its internal structure, its magnetic field configuration — all of that information is lost behind the horizon. The exterior geometry depends only on $(M, Q, J)$.

To an econometrician, this is immediately recognizable: it is **partial identification**; moreover, the theorem asserts **sharp identification**. The map from the initial matter configuration $\theta$ (an infinite-dimensional object) to the exterior observable $(M, Q, J)$ (a three-dimensional summary) is many-to-one. The identified set $\Theta_I$ consists of all initial configurations consistent with the observed $(M, Q, J)$. We know the black hole came from *some* element of $\Theta_I$, but we cannot point-identify which one.

This is why there are multiple competing theories of black hole interiors — fuzzballs, firewalls, remnants, and others. They are all members of the same identified set: different structural specifications that produce identical exterior observables. From the econometric perspective, this is not a crisis. It is just what partial identification looks like.

Three further observations:

**Ergodicity again.** The identification failure is driven not by a lack of data, but by a permanent support constraint. No additional "moment conditions" from the exterior can shrink the identified set, because no signal from the interior can reach us. This is selection into a disconnected component of the support, with no instrument to bridge the gap.

**Sharp identification.** In econometrics, overidentification means the DGP could produce a falsifiable empirical distribution of data. In GR, the no-hair theorem imposes a sharp, verifiable restriction on the exterior geometry: it *must* be characterized by exactly $(M, Q, J)$, no more. If we observed a stationary black hole with a "fourth hair" — a fourth independent parameter characterizing its exterior field — that would be a rejection of GR. The no-hair theorem is, in this sense, both a partial identification result and a falsifiable prediction.

**Functional/counterfactual identification.** The modern econometric insight is that point-identifying the full DGP $\theta$ is rarely the goal. What matters is whether the *functional* of interest, or often called a counterfactual parameter, $\nu(\theta)$ is identified. Applied to black holes: we may never point-identify the interior configuration, but specific functionals — the total Hawking radiation spectrum, the entropy, the scattering matrix — may still be point-identified from exterior data. This logic is reminiscent of the holographic principle (as formalized in AdS/CFT): boundary data may point-identify certain bulk observables even when bulk microstates are set-identified — though making this connection rigorous for black hole hair remains an open research question.

---

## 8. Fundamentally unidentifiable means nonexistent

This leads to what I think is the sharpest philosophical consequence of the identification perspective.

If a parameter is fundamentally unidentified — if no functional of the observables can distinguish one value from another — then any specification within the identified set is equally consistent with reality. You can "choose" a value, but that choice has no testable implication. It shifts no observable. It changes no functional.

In econometrics, we would say such a parameter has no testable implications. It is a gauge choice — a labeling convention, not a feature of the world.

Applied to black hole "hairs": if the no-hair theorem is correct, then the detailed initial configuration of the collapsing star is fundamentally unidentified from the exterior. Any configuration in $\Theta_I$ is equally "real." But if you cannot distinguish between them — if no influence function of any exterior observable is affected by the choice — then the "refined ontological existence" of a specific hair is vacuous. To specify it is to engage in metaphysics, not physics.

This is the identification-theoretic version of "epistemology is ontology." In the first essay, the claim was about estimation: what exists is what can be resolved from noise at the resolution you can afford. Here the claim is about identification: what exists — *operationally*, for the purpose of physics as an empirical science — is what can be *identified* from the structural model. If the identifying map cannot reach it, it makes no empirical difference. Whether one wants to grant such parameters full "ontological" status is a philosophical question; but from the perspective of testable science, they are inert. (This is an operational stance, not a claim about metaphysics. The interior of a black hole is well-defined within the mathematical model of GR. But its detailed structure beyond $(M, Q, J)$ cannot be inferred from any exterior observation, and in that sense it is empirically vacuous.)

The hierarchy is:

| Identification status | Econometric meaning | Physical meaning |
|---|---|---|
| Point identified | Uniquely recoverable parameter | Observable: particle, field value, measurable quantity |
| Partially identified | Identified set, bounds | Macrostate: characterized by aggregate observables $(M, Q, J)$ |
| Unidentified | No testable implication | Nonexistent: arbitrary specification with no physical consequence |

---

## 9. What the identification perspective adds

The first essay ended with "epistemology is ontology" — the claim that what exists is what can be resolved from noise. This second essay adds a complementary layer: what exists is what can be *identified* from structure.

Estimation asks: given finite, noisy data, what can we learn? Identification asks: given the structural model, what is *in principle* recoverable, even with infinite data? The two questions are distinct, and the answers can differ. A parameter can be identified but hard to estimate (irregular functionals with divergent representer norms). A parameter can be easy to estimate but not identified (if the structural model is misspecified or under-specified).

The Riesz representer governs the cost in both regimes. In the first essay, the cost was statistical: the representer norm determines the variance of the estimator. Here, the cost is structural: the representer norm determines whether the identifying map can reach the functional at all. Black holes are the limiting case — the representer norm diverges, the causal support is truncated, and the identifying map breaks down. The no-hair theorem tells us exactly what survives: a three-dimensional identified set, all that remains of an infinite-dimensional structural parameter.

The arc of the essay traced the full identification spectrum. The equivalence principle showed what *cannot* be identified locally: the Christoffel symbols are gauge artifacts, and only curvature — the tidal signature visible across an extended support — is a genuine structural feature. Gravitational lensing showed identification *in practice*: the mass-sheet degeneracy is a textbook partial identification problem, broken only by additional moment conditions from complementary data. Black holes showed identification *failure*: causal support truncation that no instrument can overcome. And the no-hair theorem showed what *survives* failure: a sharp, finite-dimensional identified set.

This is a clean story about GR on its own terms — about what deterministic structure can and cannot deliver. But it immediately raises a deeper question.

GR is a population-level structural model: deterministic, time-reversible, operating at infinite resolution. Quantum mechanics is the empirical process that actually generates our data: stochastic, irreversible, operating at finite resolution with the Planck constant playing the role of $1/n$. In the first essay, I showed that QM and nonparametric estimation share the same mathematics. In this essay, I've shown that GR and structural identification share the same mathematics. But the two theories — GR and QM — are famously, notoriously incompatible with each other.

However, econometricians carry out both identification analysis and empirical estimation all the time, and understand that they investigate different conceptual objects, produce different theorems, but can be fully reconciled with each other. After all, they are just two complementary perspectives or steps in the full econometric analysis workflow.

This observation from an econometrician's perspective then begs the following question: If GR is the structural model and QM is the DGP, then the deepest open problem in physics — the search for quantum gravity — is simultaneously a *DGP specification problem* and a *consistent estimation problem*: finding a DGP whose population limit recovers the structural identifying restrictions; and constructing a consistent estimator that implements the identification result. And the toolkit of semiparametric estimation and identification, which bridges the finite-sample and population levels, may offer more than analogy.

That is the subject of the next essay.

**Epistemology is ontology — twice over.**

---
