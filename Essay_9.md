# Fundamental Axiom of Economics: Existence of an Economic Agent
## As a Locally Rooted Information Structure in the Ambient Physical Universe

*Wayne Gao*

*I'm thankful to Claude, Gemini, and ChatGPT for discussing these ideas with me and helping me construct this essay.*

---

## 1. Why an economist wrote about physics

I owe the reader an explanation.

I am an econometrician. My daily work concerns identification, estimation, inference — the machinery by which economists extract structural knowledge from finite data, mostly about human strategic and stochastic interactions in an economic context. So why have I spent eight essays rewriting the foundations of physics in econometric language?

The honest answer is that a serious economist must confront two things: the economic agents, and the physical world they inhabit. Economic agents make decisions subject to physical constraints, adapt to physical regularities, and sometimes exploit them. Any rigorous foundation for economics therefore requires a coherent account of the physical environment — the ambient structure within which agents operate. If the best physics we have is internally contradictory (GR versus QM, reversibility versus the second law), then the foundation on which economics rests is unstable. An economist who cares about foundations cannot look away.

But physics alone is not enough. The physical world, however well-described, does not contain economics. A hydrogen atom does not demand, a photon does not bear risk, a causal graph does not set prices. What separates economics from physics is the existence of agents — self-optimizing, heterogeneous, behavioral entities that follow patterns of their own, patterns not pinned down by the laws governing their physical substrate. Demand curves, risk aversion, market equilibrium, asset prices — these are real regularities, but they are not derivable from the Standard Model or from general relativity.

The point of contact and disconnection between physics and economics is precisely here: the axiom that there exist economic agents with individually heterogeneous objectives and decision rules that cannot be determined by environmental variables alone. This is, at bottom, an axiom about the existence of something like free will — or more precisely, about locally rooted autonomous information processing.

This bothers me conceptually. It is partly the motivation for this entire series. If physics and economics share the same mathematical language — filtrations, $\sigma$-fields, conditional independence, identification, estimation — then perhaps the apparent gap between them is not a gap in reality but a gap in our framework. Perhaps both are instances of a single architecture, and the "free will" axiom is not an ad hoc addition but a structural consequence of how locally rooted information systems work.

This essay is the attempt to close that circle.

---

## 2. The series in one paragraph

Essay 1 showed that quantum mechanics and semiparametric statistics share the Hilbert-space geometry of efficient inference. Essay 2 showed that general relativity and structural econometrics share the logic of identification, gauge freedom, and observational equivalence. Essay 3 posed the GR/QM conflict as a DGP specification problem. Essays 4–5 built the dependence-first axiomatization: a finite causal DAG with overlapping $\sigma$-fields, whose population limit recovers spacetime geometry. Essays 6–7 performed the complex lift: an internal $\mathbb{R}^2$ with rotation operator $J$ at each node, generating interference, entanglement, and Bell violation. Essay 8 audited the specification sheet and dissolved the three-way tension among GR, QM, and the second law — naming the resolution the Econometric Trinity: the characteristic function (QM), the density (GR), and the innovation process (2nd law) as three aspects of a single layered DGP — showing that the apparent conflicts were category errors across layers.

Through all of this, the language was econometric. The question now: was it merely borrowed?

---

## 3. The axiom: existence of a local economic agent

I will state the foundational postulate with the same precision as the physics axioms of Essays 4 and 7.

**Axiom E.** An **economic agent** is a locally rooted node $v$ in a causal network carrying:

(a) An **accumulated filtration** $\mathcal{G}(v)$ — the agent's memory, experience, and current information. This is the same mathematical object as the past $\sigma$-field from Essay 4, now interpreted as the agent's epistemic state.

(b) An **internal objective architecture** $U_v$ — preferences, values, goals, risk attitudes. This is not necessarily a scalar utility function. It is a structured evaluation system, possibly context-dependent, possibly evolving, possibly inconsistent in the way real human preferences are inconsistent. What matters is that it exists and is heterogeneous: $U_v \neq U_w$ in general.

(c) A **decision rule** $\delta_v : \mathcal{G}(v) \times U_v \times \varepsilon_v \to A_v$ — a mapping from local information, internal objectives, and local innovation to action. The innovation $\varepsilon_v \in \mathbb{R}^2$ is the same stochastic openness that entered the spacetime framework in Essay 7: genuinely new randomness at each node.

The axiom says: at each node of the causal graph, there exists a locally rooted stochastic inference system with internal objectives that transforms local information into action. This is the economic analog of "attach a random variable to each node of the DAG." The physics axioms (F1–F2, L1–L2) specified the dependence structure of the random field. The economic axiom specifies that some nodes carry additional internal structure — objectives and decision rules — that the physical axioms do not determine.

The key word is **locally rooted**. The agent's filtration $\mathcal{G}(v)$ is local: it contains only information from the agent's causal past, not the global state of the universe. The agent's objectives $U_v$ are internal: they are not functions of the global environment but of the agent's own accumulated history and constitution. The agent's action depends on $\mathcal{G}(v)$, $U_v$, and $\varepsilon_v$ — not on the full specification-layer state of the world.

The role of $\varepsilon_v$ deserves emphasis. In Essay 8, I argued that the local innovations are ontologically fundamental — genuinely new randomness at each node, not an epistemic placeholder for deterministic dynamics we have not yet uncovered. This commitment matters deeply for economics. If innovations are fundamental, then the local information flow at each node is not fully determined by environmental variables — not by the agent's genetic code, not by its social environment, not by the global state of the causal graph. 

Environmental variables can be important, even dominant: a person's genome, upbringing, culture, and material circumstances enter heavily through the filtration $\mathcal{G}(v)$ and shape the objective architecture $U_v$. No one denies this. 

But we reject the complete determinism of individual agents. The fundamental local innovation flow ultimately instills each agent with what one might call, without mysticism, a soul: the irreducible stochastic component that makes the agent a specific individual rather than a deterministic function of its environment. The heterogeneity of $U_v$ across agents, the idiosyncrasy of each agent's decision rule $\delta_v$, the fact that two people raised in identical environments nevertheless diverge — these are not anomalies to be explained away. They are consequences of the ontologically primitive $\varepsilon_v$ that has been present in the framework since Essay 4: 

The same innovation that gives spacetime its arrow of time gives economic agents their individuality.

---

## 4. What the axiom gives for free

From Axiom E and the causal-dependence structure of Essays 4–5, several foundational concepts of economics follow as consequences rather than additional postulates.

**Individuality.** No two agents share the same filtration. Even agents at neighboring nodes in the causal graph have different causal pasts, different accumulated experiences, different internal objective architectures. Individuality is not a sociological observation or a sentimental attachment — it is an ontological fact about locally rooted information structures. Each agent is a path-dependent, irreducible informational world. This is the economic counterpart of the uniqueness of each node's past $\sigma$-field in the spacetime DAG.

**Bounded rationality.** Agents have local filtrations, not global ones. An agent at node $v$ cannot condition on $\sigma$-fields outside its causal past. It cannot observe the full specification-layer state of the economy; it sees only its Born-projected local information. Bounded rationality is therefore not a deficiency or a deviation from an ideal — it is the definition of what it means to be a locally rooted system. A globally rational agent would require $\mathcal{G}(v) = \mathcal{F}$ (the entire $\sigma$-algebra of the universe), which contradicts the local rootedness that makes the agent an agent in the first place.

**Agency.** The decision rule $\delta_v$ maps local information to action through the agent's internal objectives. The environment conditions the action — it enters through $\mathcal{G}(v)$ — but does not determine it. The internal objectives $U_v$ and the innovation $\varepsilon_v$ ensure that two agents facing identical local information may act differently. This is not randomness (the innovation alone would be mere noise) and not determinism (the environment alone would leave no room for the agent). It is structured stochastic self-determination: the locally rooted transformation of information into action by a historically accumulated system with its own evaluative architecture.

This is what "free will" means in the framework: the action at node $v$ is not a function of environmental variables alone. It depends irreducibly on the agent's internal state $U_v$, which is heterogeneous across agents and not pinned down by the global causal grammar. The environment is a condition, not a complete author.

---

## 5. An illustration: from quantum randomness to economic agency

The axiom is abstract. Let me make it concrete with an illustration — a metaphorical but, I think, illuminating account of how the physical ontology of Essays 4–8 translates into individual agency.

Consider the neural network inside a human brain. At the microscopic level, quantum effects in ion channels, synaptic vesicle release, and molecular-scale processes generate genuinely stochastic fluctuations — the $\varepsilon_v$ of the spacetime framework, realized in biological hardware. These fluctuations propagate through the brain's large recurrent network, where they are amplified, filtered, and integrated by the network's architecture: billions of neurons with learned weights, stored memories, habitual patterns, and evaluative structures. The output — a thought, a decision, an action — is not the quantum fluctuation itself. It is what the structured network does with it. A single random ion channel opening is noise; a trillion such events, processed by a self-referential network with decades of accumulated experience, is cognition.

This is the decision rule $\delta_v$ in biological form. The filtration $\mathcal{G}(v)$ is everything the agent has experienced and stored. The objective architecture $U_v$ is the evaluative structure the network has built — preferences, values, risk attitudes, learned goals. The innovation $\varepsilon_v$ is the irreducible stochastic openness at the microscopic level. Agency is none of these alone. It is the structured transformation of local information by a historically accumulated system:

$$
A_v = \delta_v(\mathcal{G}(v), U_v, \varepsilon_v).
$$

The analogy with an artificial neural network — a large language model, say — is instructive precisely because of its limits. An AI model also stores structure (architecture, weights, training), receives local information (the prompt), and produces output through a conditional inference process. In this black-box sense, the template is the same. But a human agent differs in at least two structurally important ways. First, the human is **self-prompting**: a large fraction of the "local information" entering the decision rule is internally generated — memory recall, imagination, emotional states, endogenous attention shifts — not just externally supplied. The filtration $\mathcal{G}(v)$ is not a passive record of external events but an actively self-updating informational world. Second, the human is **embodied and persistent**: the agent's node $v$ is not a single inference call but an ongoing trajectory through the causal graph, accumulating filtration continuously, revising objectives, and generating actions that feed back into the environment and into the agent's own future information. The AI receives a prompt and produces a response; the human lives inside the causal graph, prompting itself at every moment.

These differences are not incidental. They are what makes the economic agent an economic agent: a persistent, self-prompting, locally rooted system with endogenous objectives — not a stateless function from input to output, but a historical entity whose next action depends on everything it has been.

---

## 6. The economic architecture: scarcity, markets, equilibrium, institutions

Axiom E together with the causal-dependence structure of Essays 4–5 generates the core concepts of economics as relatively straightforward consequences. I will survey them briefly, since the derivations are natural once the framework is in place.

**Scarcity** is limited local information. No agent has global information: each has a bounded filtration $\mathcal{G}(v)$, extending only into its own causal past, and must act before the data are complete — because the data are never complete. Limited goods are a downstream consequence; the root cause is informational. An economy of agents with global information would not exhibit scarcity in any economically meaningful sense, even if physical goods were finite. It is the local rootedness that creates the economic problem.

**Markets** are overlapping filtrations. When two agents at nodes $u$ and $v$ share some common causal past — $\mathcal{G}(u) \cap \mathcal{G}(v) \neq \emptyset$ — interaction becomes possible. This is the three-piece decomposition from Essay 4 (common past, private pasts) applied to agents rather than spacetime atoms. Prices are **summary statistics of the dependence structure** across the agent network, compressing high-dimensional overlapping filtrations into low-dimensional signals — analogous to the Riesz representer from Essay 1. The efficient market hypothesis becomes a statement about mixing: prices aggregate local information efficiently when private information decays sufficiently fast with network distance, in the sense of Axiom L2.

**Equilibrium** is a compatibility condition. Each agent's action $A_{v_i} = \delta_{v_i}(\mathcal{G}(v_i), U_{v_i}, \varepsilon_{v_i})$ depends on its local filtration, which incorporates the actions of agents in its causal past. Equilibrium is the fixed point: each agent's action is optimal given its local information, which already reflects other agents' optimal actions. This is the economic analog of the global Markov property (Axiom L1) — a local compatibility condition that propagates to global consistency. Nash equilibrium, competitive equilibrium, rational expectations equilibrium are all special cases, obtained by specifying $U_v$, $\delta_v$, and the information topology.

**Institutions** are structural constraints on the economic DAG. They determine which agents' filtrations can overlap, how information propagates, and what actions are feasible. Institutions are to the economic network what light-cone structure is to the spacetime DAG: the causal grammar that determines which interactions are possible. Changing an institution is changing the graph — a disclosure regulation expands filtration overlaps; a communication ban contracts them. The economic DGP is specified by three components together: Axiom E (agents with objectives), the filtration axioms (causal structure, conditional independence, dependence decay), and institutional constraints (graph topology).

---

## 7. The two layers in economics

The specification/information layer separation from Essays 6–7 has a direct economic counterpart.

The **specification layer** of the economy is the complete description of all agents' internal states: their full filtrations, their objective architectures, their decision rules, their current specification-layer amplitude states. This is the "true DGP" of the economy — the complete microscopic description.

The **information layer** is what is publicly observable: choices, revealed preferences, prices, traded quantities, published data, disclosed actions. It is the Born projection of the economic specification: a coarsening that discards the private, internal, heterogeneous content and retains only the measurable shadow.

Asymmetric information — the central theme of modern microeconomics — is precisely the gap between these two layers. A seller knows the specification-layer quality of the good; a buyer observes only the information-layer price and public signals. Adverse selection, moral hazard, signaling — the canonical problems of information economics — are all instances of the specification-information gap.

Mechanism design becomes the art of designing institutions (graph constraints) that make the information layer maximally informative about the specification layer. The revelation principle says: under certain conditions, agents can be induced to reveal their specification-layer types through appropriately designed information-layer mechanisms. This is the economic analog of the identification problem from Essay 2: when can specification-layer parameters be recovered from information-layer observables?

The answer, as in physics, depends on the structure of the DGP. Some economic specifications are identified from market data; others are not. The no-hair theorem has an economic counterpart: a market that compresses the rich internal heterogeneity of agents into a single price is performing the same operation as the Markov blanket that compresses the black hole interior into $(M, Q, J_{\text{BH}})$. The internal details — the specification-layer diversity — are lost in the projection. What survives is what the information layer can support.

---

## 8. The point of contact: why the axiom is irreducible

Let me return to the conceptual tension that motivated this series.

Physics, in the framework of Essays 4–8, is fully specified by the causal grammar (the DAG), the amplitude field $\{Y_v, J\}$, and the propagation/innovation structure. The economic axiom (Axiom E) adds three things that the physics does not contain: accumulated filtration interpreted as memory, internal objectives $U_v$, and a decision rule $\delta_v$ that maps information and objectives to action.

Are these three things derivable from the physics? Can one, starting from the lifted finite framework of Essay 7, derive the existence of agents with heterogeneous objectives?

No. And this is the point.

The physical framework specifies the causal structure and the amplitude dynamics. It determines which interactions are possible, how information propagates, what the dependence structure looks like. But it does not determine what an agent wants, how an agent evaluates outcomes, or what an agent chooses to do with its local information. The internal objective architecture $U_v$ is not a function of the physical specification-layer state — it is an additional structural fact about the node, one that the physical axioms leave open. The heterogeneity of $U_v$ across agents — the fact that different people want different things, evaluate outcomes differently, and respond to the same information differently — is an irreducible feature of the economic world, not derivable from the physical substrate.

One could argue that physical laws, in principle, determine all physical activity — including everything that happens inside a human brain. In some reductionist sense this is true. But the generality of physical laws is precisely what makes them unable to answer the questions that economics asks. A universal law — elegant, foundational, applying to every particle in the universe — is by its very universality too simple to say anything specific about demand curves, risk preferences, or market equilibrium. The more universal a law is, the less it says about any particular regime of organized complexity. This is not a deficiency of either discipline. It is a two-perspective view of the same reality: physics sees the causal grammar with maximal generality and minimal specificity about what the actors do; economics sees the actors with maximal specificity about behavior and minimal concern for the substrate. The two are complementary. The point of contact is the shared mathematical skeleton — filtrations, conditional independence, dependence, identification. The point of disconnection is that $U_v$ and $\delta_v$ are not in the physicist's vocabulary, and no amount of physical generality will put them there.

There is a deeper way to state this disconnection, and it connects back to the population-versus-sample distinction that has run through the entire series. Physical laws — whether GR at the population level, QM at the specification level, or the second law at the information level — are all statements about the **regularities of the DGP**: the stable structural features that hold across all realizations. But a human agent is not a regularity of the DGP. A human agent is a **conditioned event** — a single realized trajectory through the causal graph, shaped at every step by the accumulated randomness of biological evolution, civilizational history, and individual experience. The configured state of a person's agency — preferences, cognitive habits, emotional architecture — depends on a realized history of innovations buried deeply in biological and social conditioning. No two realizations are the same, and none can be rewound.

There may well be a forward-looking DGP for the agent — the decision rule $\delta_v$ generates future actions stochastically, and the regularities of that process are legitimate objects of economic study. But the starting point is fixed: the agent begins from a specific realized filtration $\mathcal{G}(v)$, a specific objective architecture $U_v$, shaped by a specific history. The specificity of this starting point is real, meaningful, and absolutely important for economics. It is what makes demand estimation different from estimating a physical constant. The gravitational constant $G$ is a parameter of the DGP, the same in every realization. An agent's risk aversion is a parameter of a conditioned process: it depends on who the agent is, which depends on the particular path of realized innovations that produced them.

Humanity itself is a local information event: one particular trajectory of a biological and civilizational process on one planet, conditioned on billions of years of realized $\varepsilon_v$'s. An individual person is an even more local event within that trajectory. Physics describes the regularities of the DGP that govern all possible trajectories. Economics conditions on the trajectory that actually happened — on the specific agents that actually exist, with the specific filtrations they have actually accumulated, holding the specific objectives they actually hold. This conditioning is deliberate, not a limitation. Economics is the science of what locally rooted agents do, given everything they have been.

---

## 9. Two instantiations of one architecture

The parallel is not metaphorical. Let me state it as a table.

| Component | Physics (Essays 4–8) | Economics (This essay) |
|-----------|---------------------|----------------------|
| Local information structure | Observable $X_v$ / amplitude $Y_v$ at node $v$ | Agent with filtration $\mathcal{G}(v)$ at node $v$ |
| Structural constraints | Causal grammar (DAG), light-cone support | Institutions, legal/organizational structure |
| Propagation rule | Dependence decay (Axiom L2), propagator $T_{u \to v}$ | Information propagation, price signals |
| Compatibility condition | Conditional independence (Axiom L1), Markov property | Equilibrium: local optimality → global consistency |
| Specification layer | Full amplitude state $\{Y_v, J\}$ | Full agent states $\{(\mathcal{G}(v), U_v, \delta_v)\}$ |
| Information layer | Born-projected observables $\|Y_v\|^2$ | Publicly observable prices, quantities, actions |
| Identification problem | Recover $[g]$ from $\alpha_C$ (Malament) | Recover structural parameters from market data |
| Innovation | $\varepsilon_v$ (new physical randomness) | $\varepsilon_v$ (stochastic openness of the agent) |

The mathematical language — filtrations, $\sigma$-fields, conditional independence, dependence, identification, estimation — is the same in both columns because the structure is the same. Physics and economics are two instantiations of structured information dynamics: the study of how locally rooted information systems interact within a shared causal grammar.

The difference is what populates the nodes. In physics, the nodes carry amplitude vectors with rotational structure; in economics, they carry agents with objectives. The amplitude vector has no preferences; the agent has no phase. But both are locally rooted, both generate dependence through causal propagation, both are observed through a coarsening projection, and both admit identification and estimation as the fundamental epistemic operations.

---

## 10. Closing: epistemology is ontology, from the Planck scale to the market

This series began with a mathematical observation: the econometrician's Hilbert space is the physicist's Hilbert space. It ends with a structural claim: the physicist's causal graph is the economist's market.

The claim is not that physics and economics are the same subject. They are not. Physics concerns the amplitude dynamics of a causal network; economics concerns the decision dynamics of agents embedded in that network. Physics is about structure and information; economics is about structure, information, and objectives. The economic axiom — the existence of locally rooted agents with heterogeneous internal objectives — is irreducible. It cannot be derived from the physical framework, just as the physical framework cannot be derived from economics. They are siblings, not parent and child.

But they share the same mathematical skeleton. They share filtrations, conditional independence, dependence decay, the specification/information gap, the identification problem, the estimation problem. They share the principle that what exists is what can be identified from the structural model and estimated from finite data. They share the layered architecture:

$$
\text{causal grammar}
\;\to\;
\text{specification}
\;\xrightarrow{\text{projection}}\;
\text{local information}
\;\xrightarrow{\text{aggregation}}\;
\text{global structure}.
$$

In physics, the chain is: DAG → amplitude field → Born projection → dependence → geometry. In economics, it is: institutional graph → agent states → market projection → prices → equilibrium. The mathematics is the same because the logic is the same: locally rooted systems, interacting through overlapping information, observed through a coarsening map, identified and estimated from finite data.

The econometric vocabulary was not borrowed from statistics and applied to physics. It was not borrowed at all. It is the shared language of structured information dynamics — a language that physics and economics both speak, because they are both about what locally rooted information structures can identify and estimate from the data available to them.

This is the thesis, fully stated: **what exists is what admits a consistent layered DGP — a specification whose population limit is the structural truth and whose information-layer realization is the observable, estimable, irreversible world.** This holds whether the "observer" is a photon detector or an economic agent, whether the "data" are particle trajectories or market transactions, whether the "structural model" is Einstein's field equation or the equilibrium of a competitive market.

**Epistemology is ontology — from the Planck scale to the market.**

---

### References

- Arrow, K. J. (1951). Social choice and individual values. *Cowles Foundation Monograph* 12.
- Arrow, K. J., and Debreu, G. (1954). Existence of an equilibrium for a competitive economy. *Econometrica*, 22, 265–290.
- Blackwell, D. (1951). Comparison of experiments. *Proceedings of the Second Berkeley Symposium on Mathematical Statistics and Probability*, 93–102.
- Blackwell, D. (1953). Equivalent comparisons of experiments. *Annals of Mathematical Statistics*, 24, 265–272.
- Hayek, F. A. (1945). The use of knowledge in society. *American Economic Review*, 35, 519–530.
- Lucas, R. E. (1972). Expectations and the neutrality of money. *Journal of Economic Theory*, 4, 103–124.
- Mas-Colell, A., Whinston, M. D., and Green, J. R. (1995). *Microeconomic Theory*. Oxford University Press.
- Muth, J. F. (1961). Rational expectations and the theory of price movements. *Econometrica*, 29, 315–335.
- Pearl, J. (2009). *Causality: Models, Reasoning, and Inference*. 2nd edition. Cambridge University Press.
- Radner, R. (1968). Competitive equilibrium under uncertainty. *Econometrica*, 36, 31–58.
- Radner, R. (1979). Rational expectations equilibrium with generic existence and the information revealed by prices. *Econometrica*, 47, 655–678.
- Simon, H. A. (1955). A behavioral model of rational choice. *Quarterly Journal of Economics*, 69, 99–118.
- Stiglitz, J. E. (1981). The allocation role of the stock market. *Journal of Finance*, 36, 235–251.
