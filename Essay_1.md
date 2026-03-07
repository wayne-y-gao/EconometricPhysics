# Quantum Physics and Semiparametric Learning

*Wayne Gao*

*I'm thankful to a conversation with Gemini for helping me walk through these layers, and to Claude for drafting and polishing this article.*

---

## 1. A question about $i\equiv\sqrt{-1}$ and the HUP

Yesterday I was voice chatting with Gemini on my drive to work. And I was interested in the role of complex algebra in quantum physics and the Heisenberg Uncertainty Principle, which I mentioned in my undergrad intro statistics course as one of the "sources of uncertainty".

I knew that complex algebra is a clean way to handle rotation, but I was interested in how this rotation is fundamentally indispenssble in quantum physics (a field outside my academic expertise but intellectually fascinating to me), and what the essence of the Heisenberg Uncertainty Principle is.

Gemini's answer: complex numbers aren't just convenient in quantum mechanics — they are *necessary*, because quantum states evolve by rotation. The Fourier transform decomposes a function into oscillations, and oscillations are rotations in the complex plane. Euler's formula $e^{i\theta} = \cos\theta + i\sin\theta$ isn't a trick; it's telling you that the natural language of periodic structure is complex multiplication. When you multiply by $e^{i\theta}$, you rotate. When you rotate, you oscillate. When you oscillate, you have a wave.

And the Heisenberg Uncertainty Principle? It turns out to be a consequence of the same Fourier duality that econometricians use routinely — the tradeoff between a function's localization and the localization of its frequency representation. That's when something clicked for me. The Fourier tradeoff, the bias-variance tradeoff, sieve approximation, metric entropy, the Riesz representer — I started pushing the conversation toward my own territory, and the parallels kept getting sharper.

This essay is my attempt to lay out that chain of reasoning. It connects ideas that econometricians and statisticians use to the deep structure of quantum mechanics. The punchline isn't that physics is a metaphor for statistics. It's that the two disciplines are studying the *same mathematical object* from different directions.

---

## 2. The Fourier tradeoff and the uncertainty principle

The scaling property of the Fourier transform is one of those facts you learn as a graduate student and then forget to be amazed by. If $f(x)$ has Fourier transform $\hat{f}(\omega)$, then compressing $f$ in position — replacing $f(x)$ with $f(ax)$ for $a > 1$ — stretches out $\hat{f}$ in frequency. You cannot have a function that is simultaneously narrow in both domains.

This is not an approximation result. It is an exact identity, a consequence of the dilation property of the Fourier transform. The Heisenberg uncertainty principle

$$\Delta x \cdot \Delta p \geq \frac{\hbar}{2}$$

is an instance of this general Fourier-analytic fact, applied to quantum wavefunctions — though the precise quantitative bound $\hbar/2$ requires the additional structure of the canonical commutation relation $[\hat{x}, \hat{p}] = i\hbar$. A particle's position-space wavefunction $\psi(x)$ and its momentum-space wavefunction $\hat{\psi}(p)$ are Fourier duals. Localizing one necessarily delocalizes the other.

Now here is the observation that stopped me: *we have the exact same structure in nonparametric estimation.*

---

## 3. Bias-variance as a Hamiltonian

Consider estimating a density $f$ from $n$ i.i.d. observations using a kernel estimator $\hat{f}_h$ with bandwidth $h$. The mean integrated squared error decomposes as

$$\text{MISE}(h) = \underbrace{\frac{1}{nh} \int K^2}_{\text{Variance}} + \underbrace{\frac{h^4}{4}\left(\int (f'')^2\right)\left(\int u^2 K(u)\,du\right)^2}_{\text{Squared Bias}} + o\!\left(\frac{1}{nh} + h^4\right).$$

The variance term scales as $1/(nh)$ — as the bandwidth shrinks, the estimator oscillates more wildly to track each data point. The squared bias term scales as $h^4$ — as the bandwidth grows, the estimator is too smooth to capture local curvature.

Now relabel. Call the variance term "kinetic energy" $T$ and the squared bias "potential energy" $V$. The MISE is a Hamiltonian:

$$H(h) = T(h) + V(h).$$

This analogy is more than decorative. In quantum mechanics, the ground state of a particle in a potential well is the wavefunction that minimizes the total energy $H = T + V$, subject to the constraint that $T$ and $V$ cannot both be made small simultaneously (because of the Fourier tradeoff above). The optimal bandwidth $h^* \propto n^{-1/5}$ that minimizes the MISE plays the role of the *ground state* of this statistical Hamiltonian. (The disanalogy is that the MISE is a scalar function of $h$, while the quantum Hamiltonian is an operator on a Hilbert space. The structural resemblance is in the tradeoff, not in the full operator-theoretic machinery.)

The sample size $n$ plays the role of $1/\hbar$. As $n \to \infty$, the "Planck constant" of our estimation problem vanishes, the uncertainty shrinks, and we recover the classical limit — consistent estimation of $f$. For finite $n$, we are stuck in a quantum regime where bias and variance are locked in an irreducible tradeoff.

---

## 4. Why anything is learnable: metric entropy

The bias-variance tradeoff tells you that estimation is hard. It does not tell you that estimation is *possible*. For that, you need a different concept: the complexity of the function class you're trying to learn.

In empirical process theory, the key quantity is **metric entropy** — the logarithm of the covering number $N(\varepsilon, \mathcal{F}, \|\cdot\|)$, which counts how many balls of radius $\varepsilon$ you need to cover a function class $\mathcal{F}$. The intuition is simple: $\varepsilon$ is the mesh size — the resolution at which you are trying to approximate functions in $\mathcal{F}$. As you make the mesh finer ($\varepsilon \to 0$), you need more balls to cover the class. For a typical smooth function class on $\mathbb{R}^d$, the covering number scales as

$$N(\varepsilon, \mathcal{F}, \|\cdot\|) \sim \left(\frac{1}{\varepsilon}\right)^d$$

so the metric entropy grows as $d \log(1/\varepsilon)$. The dimension $d$ controls how fast the complexity explodes as you demand finer resolution. If the metric entropy grows too fast as $\varepsilon \to 0$, the class is too rich: no amount of data can pin down which function generated the sample. The empirical process $\sqrt{n}(\mathbb{P}_n - P)$ fails to converge uniformly.

There are two thresholds here, and the distinction matters. The weaker one is the **Glivenko-Cantelli** condition: it guarantees that the empirical measure converges uniformly to the truth — the uniform law of large numbers. This tells you that patterns are *learnable*, that averages stabilize, but nothing about the rate or the shape of the fluctuations. The stronger one is the **Donsker** condition — that $\int_0^\infty \sqrt{\log N(\varepsilon, \mathcal{F}, L_2(P))}\, d\varepsilon < \infty$ — which guarantees that the empirical process converges to a Gaussian limit. This is what you need not just for estimation but for *inference*: confidence sets, efficiency bounds, the entire apparatus of the central limit theorem applied uniformly over the function class.

Here is the physical parallel, and it is striking. In the early 20th century, physicists confronted the **ultraviolet catastrophe**: classical electromagnetic theory predicted that a blackbody should radiate infinite energy at high frequencies. The resolution — Planck's quantization — was effectively an *entropy bound on the function class of allowable radiation modes*. By discretizing the energy levels, Planck imposed a finite covering number on the space of field configurations. The catastrophe was averted because the metric entropy of the physical system turned out to be bounded.

The analogy runs deeper. Quantum field theory requires **renormalization** precisely when the naive function class (all possible field configurations) has unbounded metric entropy. The UV divergences that plagued early QFT are, in the language of empirical processes, a failure of the Donsker condition. The renormalization program — imposing cutoffs, running coupling constants — shares a deep structural similarity with sieve approximation: both replace an intractable infinite-dimensional class with a sequence of finite-dimensional approximations whose complexity grows with a scale parameter (sample size in statistics, energy cutoff in QFT). The procedures are not identical — renormalization involves subtracting divergences and tracking how coupling constants "flow" with scale in ways that have no direct statistical analog — but the underlying logic of controlled finite-dimensional approximation is the same.

The reason atoms are stable, the reason matter doesn't dissolve into noise, is that the function class describing physical reality has *bounded metric entropy*. The universe is at least Glivenko-Cantelli — learnable, with patterns that stabilize. The richness of quantum mechanics — the fact that we can characterize not just the values but the *fluctuations* of physical observables — suggests it is Donsker: not just learnable, but learnable with Gaussian fluctuations that support precise inference.

---

## 5. Sieve approximation as the mechanism of existence

This brings us to sieves, and to the core of the essay.

In nonparametric estimation, a sieve is a sequence of finite-dimensional spaces $\mathcal{F}_J$ that grow with the sample size and eventually approximate the full infinite-dimensional parameter space $\mathcal{F}$. The sieve dimension $J = J(n)$ is the tuning parameter: too small and you underfit (high bias), too large and you overfit (high variance).

A quantum wavefunction, from this vantage point, lives in the same mathematical world as a sieve. A particle is not a point; it is a *smooth, finite-bandwidth object* — a wavepacket of some width $\Delta x$. Trying to compress that wavepacket (decrease $\Delta x$) requires pumping in energy (increasing momentum uncertainty). The stationary states of a quantum system are the wavefunctions that minimize the total energy for a given set of constraints — just as the optimal sieve estimator minimizes total risk for a given sample size.

A wavefunction is not literally a sieve approximation in the econometric sense: it is not a member of a growing sequence $\mathcal{F}_J$ designed to approximate a target. But both objects are governed by the same functional-analytic tradeoff. Both live in $L_2$ spaces. Both involve minimizing a quadratic functional (the risk, the energy) subject to a smoothness-complexity tradeoff governed by the scaling properties of basis expansions. The Fourier basis, wavelets, Hermite polynomials — these appear in both literatures because they are the eigenfunctions of the same classes of operators.

---

## 6. From functions to functionals: the semiparametric turn

Everything so far has been about estimating an entire function — a density, a regression surface, a wavefunction. But in both statistics and physics, what we ultimately care about is usually not the full function but a *functional* of it: a scalar summary that aggregates the infinite-dimensional object into something finite and interpretable.

In econometrics: the average treatment effect $\theta = E[m_1(X) - m_0(X)]$, the average marginal effect, the welfare functional. In physics: the energy of a state, the expected value of an observable, the scattering cross-section.

This is where semiparametric theory enters, and where the parallel between statistics and quantum mechanics becomes most precise.

The key theorem is the **Riesz representation theorem**: every continuous linear functional $\nu$ on a Hilbert space $\mathcal{H}$ can be written as an inner product,

$$\nu(m) = \langle \alpha, m \rangle$$

for a unique element $\alpha \in \mathcal{H}$, called the Riesz representer.

In semiparametric statistics, $\alpha$ is the object that "extracts" the finite-dimensional parameter $\theta$ from the infinite-dimensional nuisance $m$. In quantum mechanics, this is **Dirac's bra-ket notation**: the "bra" $\langle \alpha |$ acts on the "ket" $|\psi\rangle$ to produce a scalar $\langle \alpha | \psi \rangle$, which is the expected value of the observable represented by $\alpha$.

This is not a metaphor. Dirac's bra-ket notation is a direct implementation of the Riesz representation theorem. The "bra" $\langle \alpha |$ *is* the continuous linear functional induced by the Riesz representer $\alpha$. The inner product is the same inner product. The Hilbert space is the same Hilbert space.

---

## 7. The influence function as propagator

When the Riesz representer has finite norm — the "regular" case — semiparametric theory delivers a powerful result. The efficient influence function (EIF) is the central object. For a functional $\nu(P)$ of the data-generating distribution $P$, the EIF $\psi(z; P)$ satisfies

$$\sqrt{n}\left(\hat{\theta} - \theta\right) = \frac{1}{\sqrt{n}} \sum_{i=1}^n \psi(Z_i; P) + o_P(1)$$

for any efficient estimator $\hat{\theta}$. It captures exactly how much a single observation "influences" the estimate. The variance of the EIF is the semiparametric efficiency bound — the Cramér-Rao lower bound for the semiparametric model.

In quantum field theory, the analog is the **Green's function** (propagator). The Green's function $G(x, y)$ tells you how a perturbation at point $y$ influences the field at point $x$. It is the "response function" of the system — the kernel that converts a local source into a global effect.

The structural analogies are suggestive:

| Semiparametric statistics | Quantum field theory |
|---|---|
| Influence function $\psi(z)$ | Green's function $G(x,y)$ |
| "How one observation shifts the estimate" | "How one source shifts the field" |
| Mean zero: $E[\psi] = 0$ | Conservation: $\int G = $ boundary terms |
| Variance $= $ efficiency bound | Spectral weight $= $ physical mass |
| Pathwise derivative $\partial_t \nu(P_t)$ | Functional derivative $\delta S / \delta \phi$ |

The Cramér-Rao bound and the Heisenberg uncertainty principle are, at this level of abstraction, the same theorem. Both say: there is a minimum variance (energy) required to extract a signal (observable) from a noisy (quantum) background, and that minimum is determined by the geometry of the Hilbert space.

But the EIF story assumes finite representer norm — the $\sqrt{n}$ world. What happens when that assumption fails?

---

## 8. The sieve Riesz representer and the difficulty of measurement

The sieve Riesz representer framework lifts the theory to a higher level of generality. The key insight: the **norm** of the Riesz representer $\|\alpha\|$ governs the difficulty of estimation, and the sieve approach handles both the finite-norm and divergent-norm cases in a unified way.

If $\|\alpha\| < \infty$, the functional $\nu(m)$ can be estimated at the $\sqrt{n}$ rate — the parametric rate — even though $m$ itself converges at a slower, nonparametric rate. The infinite-dimensional nuisance can be "projected away." This is the semiparametric miracle described in the previous section: the EIF exists, the Cramér-Rao bound is finite, and the representer has finite energy.

If $\|\alpha\| = \infty$, you're in trouble — but not hopeless. The functional is "irregular" — it is trying to resolve features of $m$ that are too fine for the available data at the $\sqrt{n}$ scale. The estimation rate slows, sometimes dramatically. But the sieve Riesz representer $\alpha_J$, defined on the finite-dimensional sieve space $\mathcal{F}_J$, always has finite norm. The question becomes: how fast does $\|\alpha_J\|$ grow with $J$?

In quantum mechanics, the same dichotomy appears. An observable with a bounded operator (finite norm) produces finite, stable measurements. An observable whose operator is unbounded — like trying to simultaneously measure position and momentum with arbitrary precision — produces divergent expectations. The measurement "blows up" because you're asking the Hilbert space for more information than it contains at the given energy scale.

In quantum field theory, a related phenomenon to an infinite Riesz representer norm is an **ultraviolet divergence**: the observable, naively defined, yields infinity. The renormalization program is the physicist's way of replacing the divergent representer with a sequence of *sieve Riesz representers* $\alpha_J$ whose norms are finite, and carefully controlling the approximation error $\|\alpha_J - \alpha\|$ as $J \to \infty$.

This is precisely the structure studied in the sieve semiparametrics literature — by Xiaohong Chen and collaborators (e.g. Ai, Christensen, Liao, Pouzo, Sun), as well as Newey and others — when analyzing convergence rates for functionals in ill-posed inverse problems. This also shows in my own recent paper with Xiaohong on the minimax semiparametric learning of integral functionals on submanifolds. The rate depends on how fast $\|\alpha_J\|$ grows with $J$. The faster the growth, the harder the problem; the functional is trying to resolve features of $m$ at a scale where the "noise" dominates. In QFT, the analogous question is how fast the UV cutoff must be sent to infinity — and whether the resulting divergences can be absorbed into a finite number of renormalized parameters.

---

## 9. What the parallel means

I am not claiming that the universe "is" a statistics problem in any reductive sense. What I am claiming is narrower and, I think, more interesting: the mathematical structures that govern *what can be learned from data* and the mathematical structures that govern *what can physically exist* share, in important cases, not just a family resemblance but a common formal foundation.

The Riesz representation theorem doesn't care whether you're computing an average treatment effect or an expected energy. The Fourier uncertainty principle doesn't care whether your function is a kernel density estimator or an electron wavefunction. Metric entropy doesn't care whether it's bounding the complexity of a Donsker class or preventing an ultraviolet catastrophe. These are literal identities — the same theorems, applied in different domains.

This shouldn't be entirely surprising. Both disciplines are, at bottom, studying the geometry of $L_2$ spaces and the behavior of projections in infinite-dimensional Hilbert spaces. Where the parallels become structural analogies rather than identities — the MISE-as-Hamiltonian, renormalization-as-sieve — they remain illuminating precisely because the underlying functional analysis is shared. But I think econometricians — myself included — have been slow to recognize how deep the shared foundation goes, and what it might teach us.

For the physicist, the message might be: the semiparametric theory built on the sieve Riesz representer offers a mature, rigorous framework for understanding *why* certain observables are "easy" (finite representer norm, $\sqrt{n}$ rate) and others are "hard" (divergent norm, slower rate, need for renormalization) — and for handling both cases in a unified way. The sieve literature has tools for this that the physics literature has written about under different names.

For the econometrician, the message might be: the bias-variance tradeoff is not a nuisance to be managed. It is a fundamental constraint on information, as basic as the uncertainty principle. And the semiparametric program — extracting estimable functionals from infinite-dimensional nuisance parameters, whether at the $\sqrt{n}$ rate or slower — is, mathematically, the same act as extracting physical observables from the quantum vacuum.

John Wheeler's phrase "it from bit" — the idea that physical existence is fundamentally informational — has been debated by philosophers and physicists for decades. The semiparametric perspective offers, if not a proof, then at least a sharp formalization. Functionals with finite Riesz representer norm are the "easy" signals — they converge at the $\sqrt{n}$ rate, cleanly separable from the infinite-dimensional background. But they are not the only things that exist. Irregular functionals, whose representer norms diverge, are harder to learn — they converge more slowly, demand more data, and require careful sieve-based inference — but they are not beyond reach. They are the faint signals: real, but costly to resolve.

What the norm of the representer governs is not *whether* something exists, but *how much it costs to know it*. The $\sqrt{n}$-estimable functionals are cheap knowledge. The irregular ones are expensive knowledge. And the infinite-dimensional nuisance — the full nonparametric function itself — is the background hum that you can never fully resolve, only approximate through ever-finer sieves.

The universe, on this view, is not divided into "real" and "nuisance." It is a spectrum of estimability — from the sharp and cheap to the faint and dear. 

*What we call existence is whatever signal survives the noise at the resolution we can afford.*

**Epistemology is ontology.**

---

