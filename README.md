# Neurosymbolic Learning and Reasoning

## Integration targets and historical foundations

- **[Neural–symbolic integration](https://arxiv.org/abs/2105.05330)** — 2021. Combines learned representations with symbolic knowledge or computation. Sarker et al. organize integration approaches; injecting a rule into training differs from executing a symbolic program at inference.
- **[KBANN](https://ftp.cs.wisc.edu/machine-learning/shavlik-group/towell.aij94.pdf)** — 1994. Towell and Shavlik translate propositional domain theories into a neural network, then refine it by backpropagation. Rules initialize the architecture; subsequent training need not preserve them as hard constraints.
- **[Abductive learning](https://papers.neurips.cc/paper_files/paper/2019/hash/9c19a2aa1d84e04b0bd4bc888792bd1e-Abstract.html)** — 2019. Alternates learned perception with logical corrections of perceived facts. Dai et al. jointly learn digit recognition and mathematical operations from handwritten equations; logical consistency supplies training feedback for perception.

## Logical objectives and differentiable reasoning

- **[Logic Tensor Networks](https://arxiv.org/abs/2012.13635)** — 2020. Represent first-order knowledge in a many-valued differentiable logic and optimize satisfaction alongside learning. Truth degrees depend on the chosen logical operators; they are not automatically calibrated probabilities.
- **[Logical Neural Networks](https://arxiv.org/abs/2006.13155)** — 2020. Associate neurons with components of logical formulas and propagate bounds on truth values. Contradiction-aware learning and an open-world treatment support incomplete knowledge within the proposed logic.
- **[Semantic loss](https://proceedings.mlr.press/v80/xu18h.html)** — 2018. Penalizes probability mass assigned to outputs that violate a propositional constraint. Xu et al. connect neural predictions to weighted model counting; a finite soft penalty differs from enforcing validity at decoding.
- **[SATNet](https://proceedings.mlr.press/v97/wang19e.html)** — 2019. Differentiates through a semidefinite relaxation of MAXSAT to integrate constraint solving with neural perception. Wang et al. test parity and Sudoku; the relaxed solver is not a general exact SAT oracle.
- **[NeuroSAT](https://arxiv.org/abs/1802.03685)** — 2018. A message-passing network learns from SAT/UNSAT labels; satisfying assignments can emerge in its activations. More iterations solve harder tested instances, but the authors report lower reliability than conventional SAT solvers.

## Compiled symbolic representations

- **[Knowledge compilation](https://arxiv.org/abs/1106.1819)** — 2002. Darwiche and Marquis compare logical representations by succinctness and tractable queries or transformations. Compiling a theory can make repeated reasoning cheap while enlarging the representation; tractability is query- and language-specific.

## Probabilistic and answer-set programs

- **[DeepProbLog](https://arxiv.org/abs/1805.10872)** — 2018. Adds neural predicates to probabilistic logic programs and trains neural and symbolic components jointly from examples. Program structure supplies explicit reasoning; perceptual uncertainty enters through neural probabilities.
- **[DeepStochLog](https://arxiv.org/abs/2106.12574)** — 2021. Neural grammar rules define probabilities over derivations in stochastic logic programs. DeepProbLog instead uses possible-world semantics; the choice changes what a probability represents and how inference is computed.
- **[DeepProofLog](https://arxiv.org/abs/2511.08581)** — 2025; AAAI 2026. Learns neural guidance for derivation steps in stochastic logic programs. A mapping from resolution to Markov decision processes connects proof search with dynamic programming and reinforcement learning.
- **[NeurASP](https://arxiv.org/abs/2009.10256)** — 2020. Treats neural outputs as distributions over atomic facts in answer-set programs. Rules can constrain perception and training; the paper reports substantial symbolic-reasoning overhead relative to neural training alone.
- **[Scallop](https://arxiv.org/abs/2304.04812)** — 2023. Combines Datalog-style rules, recursion, aggregation and negation with differentiable provenance-based reasoning. It offers a programming interface for integrating neural inputs with structured computations.

## Learning rules and programs

- **[Differentiable ILP](https://arxiv.org/abs/1711.04574)** — 2017. Evans and Grefenstette learn explanatory rules through a differentiable inductive-logic framework. Experiments address noisy symbolic data and coupling to neural perception; the available rule language bounds expressivity.
- **[Neural theorem proving](https://arxiv.org/abs/1705.11040)** — 2017. Rocktäschel and Riedel replace exact symbolic unification with similarity between learned embeddings inside backward chaining. This permits gradient learning of rules and symbols while changing the semantics of a proof score.
- **[NeuralLP](https://arxiv.org/abs/1702.08367)** — 2017. Learns compositions of differentiable logical operations for knowledge-base reasoning. A neural controller jointly selects rule structure and weights; results concern relational queries rather than unrestricted theorem proving.
- **[DreamCoder](https://arxiv.org/abs/2006.08381)** — 2020. Alternates program search, abstraction discovery and training a neural search guide on replayed or generated tasks. Learned libraries reuse symbolic components across tasks; the supplied programming language shapes the search.

## Grounded reasoning and theorem search

- **[Neuro-Symbolic Concept Learner](https://arxiv.org/abs/1904.12584)** — 2019. Learns object representations and question-to-program parsing from image/question/answer supervision. Symbolic programs execute over learned scene concepts; correct answers alone do not establish correct concept grounding.
- **[AlphaGeometry](https://www.nature.com/articles/s41586-023-06747-5)** — 2024. A neural language model proposes constructions for a symbolic geometry engine. Trinh et al. solve 25 of 30 selected olympiad problems using synthetic training data; the result concerns Euclidean plane geometry.
- **[AlphaGeometry2](https://arxiv.org/abs/2502.03544)** — 2025. Extends the geometry language, symbolic engine and search-tree knowledge sharing. The authors report solving 84% of IMO geometry problems from 2000–2024; this expands both language coverage and search beyond AlphaGeometry.
- **[LeanDojo / ReProver](https://arxiv.org/abs/2306.15626)** — 2023. Retrieves premises for language-model-guided proof search in Lean. Its novel-premise split tests proofs using lemmas absent from training proofs; checked formal proofs provide a different output guarantee from soft neural proof scores.

## Evidence and failure modes

- **[Reasoning shortcuts](https://arxiv.org/abs/2406.10368)** — 2024. rsbench tests whether correct downstream answers hide incorrect learned concepts. Bortolotti et al. find concept quality remains difficult for neural and neurosymbolic models; task accuracy alone misses these failures.
- **[Concept identifiability](https://arxiv.org/abs/2305.19951)** — 2023. Marconato et al. characterize reasoning shortcuts as unintended optima of the learning objective. Reconstruction and partial concept supervision have limits: matching task labels and rules can leave multiple incompatible concept meanings.
- **[Separate perception from reasoning](https://arxiv.org/abs/2406.10368)**. Measure concept accuracy, answer accuracy and constraint violations separately; test new compositions and inspect which rules are given. A correct symbolic derivation can still start from an incorrect perceptual fact.

## Software

- **[DeepProbLog implementation](https://github.com/ML-KULeuven/deepproblog)**. Official probabilistic-programming system with neural predicates and example tasks. The probabilistic program, neural architecture and inference configuration jointly define the experiment.
- **[LTNtorch](https://github.com/logictensornetworks/LTNtorch)**. PyTorch implementation of Logic Tensor Networks with logical operators, quantifiers and satisfaction objectives. Record the fuzzy operators and aggregation choices when comparing models.

## Related topics

[Symbolic regression](https://mlpapers.org/symbolic-regression/) · [Interpretability](https://mlpapers.org/interpretability/) · [Bayesian networks](https://mlpapers.org/bayesian-nets/) · [Graph neural networks](https://mlpapers.org/graph-neural-networks/) · [Meta-learning](https://mlpapers.org/meta-learning/) · [Generalization](https://mlpapers.org/generalization/).
