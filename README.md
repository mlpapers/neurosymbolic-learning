# Neurosymbolic Learning and Reasoning

## Integration targets and historical foundations

- **KBANN** - Towell and Shavlik translate propositional domain theories into a neural network, then refine it by backpropagation. Rules initialize the architecture; subsequent training need not preserve them as hard constraints. [Towell and Shavlik 1994](<https://ftp.cs.wisc.edu/machine-learning/shavlik-group/towell.aij94.pdf> "Knowledge-based artificial neural networks; Artificial Intelligence").
- **Abductive learning** - Alternates learned perception with logical corrections of perceived facts. Dai et al. jointly learn digit recognition and mathematical operations from handwritten equations; logical consistency supplies training feedback for perception. [Dai et al. 2019](<https://papers.neurips.cc/paper_files/paper/2019/hash/9c19a2aa1d84e04b0bd4bc888792bd1e-Abstract.html> "Bridging Machine Learning and Logical Reasoning by Abductive Learning; NeurIPS").
- **Neural-symbolic integration** - Combines learned representations with symbolic knowledge or computation. Sarker et al. organize integration approaches; injecting a rule into training differs from executing a symbolic program at inference. [Sarker et al. 2022](<https://arxiv.org/abs/2105.05330> "Neuro-Symbolic Artificial Intelligence: Current Trends; AI Communications").

## Logical objectives and differentiable reasoning

- **Semantic loss** - Penalizes probability mass assigned to outputs that violate a propositional constraint. Xu et al. connect neural predictions to weighted model counting; a finite soft penalty differs from enforcing validity at decoding. [Xu et al. 2018](<https://proceedings.mlr.press/v80/xu18h.html> "A Semantic Loss Function for Deep Learning with Symbolic Knowledge; ICML").
- **SATNet** - Differentiates through a semidefinite relaxation of MAXSAT to integrate constraint solving with neural perception. Wang et al. test parity and Sudoku; the relaxed solver is not a general exact SAT oracle. [Wang et al. 2019](<https://proceedings.mlr.press/v97/wang19e.html> "SATNet: Bridging deep learning and logical reasoning using a differentiable satisfiability solver; ICML").
- **NeuroSAT** - A message-passing network learns from SAT/UNSAT labels; satisfying assignments can emerge in its activations. More iterations solve harder tested instances, but the authors report lower reliability than conventional SAT solvers. [Selsam et al. 2019](<https://arxiv.org/abs/1802.03685> "Learning a SAT Solver from Single-Bit Supervision; ICLR").
- **Logical Neural Networks** - Associate neurons with components of logical formulas and propagate bounds on truth values. Contradiction-aware learning and an open-world treatment support incomplete knowledge within the proposed logic. [Riegel et al. 2020](<https://arxiv.org/abs/2006.13155> "Logical Neural Networks; arXiv").
- **Logic Tensor Networks** - Represent first-order knowledge in a many-valued differentiable logic and optimize satisfaction alongside learning. Truth degrees depend on the chosen logical operators; they are not automatically calibrated probabilities. [Badreddine et al. 2022](<https://arxiv.org/abs/2012.13635> "Logic Tensor Networks; Artificial Intelligence").

## Compiled symbolic representations

- **Knowledge compilation** - Darwiche and Marquis compare logical representations by succinctness and tractable queries or transformations. Compiling a theory can make repeated reasoning cheap while enlarging the representation; tractability is query- and language-specific. [Darwiche and Marquis 2002](<https://arxiv.org/abs/1106.1819> "A Knowledge Compilation Map; JAIR").

## Probabilistic and answer-set programs

- **DeepProbLog** - Adds neural predicates to probabilistic logic programs and trains neural and symbolic components jointly from examples. Program structure supplies explicit reasoning; perceptual uncertainty enters through neural probabilities. [Manhaeve et al. 2018](<https://arxiv.org/abs/1805.10872> "DeepProbLog: Neural Probabilistic Logic Programming; NeurIPS").
- **NeurASP** - Treats neural outputs as distributions over atomic facts in answer-set programs. Rules can constrain perception and training; the paper reports substantial symbolic-reasoning overhead relative to neural training alone. [Yang 2020](<https://arxiv.org/abs/2009.10256> "Extending Answer Set Programs with Neural Networks; Electron. Proc. Theor. Comput. Sci.").
- **DeepStochLog** - Neural grammar rules define probabilities over derivations in stochastic logic programs. DeepProbLog instead uses possible-world semantics; the choice changes what a probability represents and how inference is computed. [Winters et al. 2022](<https://arxiv.org/abs/2106.12574> "DeepStochLog: Neural Stochastic Logic Programming; AAAI").
    - **DeepProofLog** - Learns neural guidance for derivation steps in stochastic logic programs. A mapping from resolution to Markov decision processes connects proof search with dynamic programming and reinforcement learning. [Jiao et al. 2026](<https://arxiv.org/abs/2511.08581> "DeepProofLog: Efficient Proving in Deep Stochastic Logic Programs; AAAI").
- **Scallop** - Combines Datalog-style rules, recursion, aggregation and negation with differentiable provenance-based reasoning. It offers a programming interface for integrating neural inputs with structured computations. [Li et al. 2023](<https://arxiv.org/abs/2304.04812> "Scallop: A Language for Neurosymbolic Programming; PACMPL").

## Learning rules and programs

- **Neural theorem proving** - Rocktäschel and Riedel replace exact symbolic unification with similarity between learned embeddings inside backward chaining. This permits gradient learning of rules and symbols while changing the semantics of a proof score. [Rocktäschel and Riedel 2017](<https://arxiv.org/abs/1705.11040> "End-to-End Differentiable Proving; NeurIPS").
- **NeuralLP** - Learns compositions of differentiable logical operations for knowledge-base reasoning. A neural controller jointly selects rule structure and weights; results concern relational queries rather than unrestricted theorem proving. [Yang et al. 2017](<https://arxiv.org/abs/1702.08367> "Differentiable Learning of Logical Rules for Knowledge Base Reasoning; NeurIPS").
- **Differentiable ILP** - Evans and Grefenstette learn explanatory rules through a differentiable inductive-logic framework. Experiments address noisy symbolic data and coupling to neural perception; the available rule language bounds expressivity. [Evans and Grefenstette 2018](<https://arxiv.org/abs/1711.04574> "Learning Explanatory Rules from Noisy Data; Journal of Artificial Intelligence Research").
- **DreamCoder** - Alternates program search, abstraction discovery and training a neural search guide on replayed or generated tasks. Learned libraries reuse symbolic components across tasks; the supplied programming language shapes the search. [Ellis et al. 2023](<https://arxiv.org/abs/2006.08381> "DreamCoder: Growing generalizable, interpretable knowledge with wake-sleep Bayesian program learning; Philosophical Transactions A").

## Grounded reasoning and theorem search

- **Neuro-Symbolic Concept Learner** - Learns object representations and question-to-program parsing from image/question/answer supervision. Symbolic programs execute over learned scene concepts; correct answers alone do not establish correct concept grounding. [Mao et al. 2019](<https://arxiv.org/abs/1904.12584> "The Neuro-Symbolic Concept Learner: Interpreting Scenes, Words, and Sentences From Natural Supervision; ICLR").
- **LeanDojo / ReProver** - Retrieves premises for language-model-guided proof search in Lean. Its novel-premise split tests proofs using lemmas absent from training proofs; checked formal proofs provide a different output guarantee from soft neural proof scores. [Yang et al. 2023](<https://arxiv.org/abs/2306.15626> "LeanDojo: Theorem Proving with Retrieval-Augmented Language Models; NeurIPS").
- **AlphaGeometry** - A neural language model proposes constructions for a symbolic geometry engine. Trinh et al. solve 25 of 30 selected olympiad problems using synthetic training data; the result concerns Euclidean plane geometry. [Trinh et al. 2024](<https://www.nature.com/articles/s41586-023-06747-5> "Solving olympiad geometry without human demonstrations; Nature").
    - **AlphaGeometry2** - Extends the geometry language, symbolic engine and search-tree knowledge sharing. The authors report solving 84% of IMO geometry problems from 2000-2024; this expands both language coverage and search beyond AlphaGeometry. [Chervonyi et al. 2025](<https://arxiv.org/abs/2502.03544> "Gold-medalist Performance in Solving Olympiad Geometry with AlphaGeometry2; JMLR").

## Evidence and failure modes

- **Concept identifiability** - Marconato et al. characterize reasoning shortcuts as unintended optima of the learning objective. Reconstruction and partial concept supervision have limits: matching task labels and rules can leave multiple incompatible concept meanings. [Marconato et al. 2023](<https://arxiv.org/abs/2305.19951> "Not All Neuro-Symbolic Concepts Are Created Equal: Analysis and Mitigation of Reasoning Shortcuts; NeurIPS").
- **Reasoning shortcuts** - rsbench tests whether correct downstream answers hide incorrect learned concepts. Bortolotti et al. find concept quality remains difficult for neural and neurosymbolic models; task accuracy alone misses these failures. [Bortolotti et al. 2024](<https://arxiv.org/abs/2406.10368> "A Neuro-Symbolic Benchmark Suite for Concept Quality and Reasoning Shortcuts; NeurIPS").

## Software

- **DeepProbLog implementation** - Official probabilistic-programming system with neural predicates and example tasks. The probabilistic program, neural architecture and inference configuration jointly define the experiment. [code](<https://github.com/ML-KULeuven/deepproblog>).
- **LTNtorch** - PyTorch implementation of Logic Tensor Networks with logical operators, quantifiers and satisfaction objectives. Record the fuzzy operators and aggregation choices when comparing models. [code](<https://github.com/logictensornetworks/LTNtorch>).

## Related topics

- [Symbolic regression](https://mlpapers.org/symbolic-regression/)
- [Interpretability](https://mlpapers.org/interpretability/)
- [Bayesian networks](https://mlpapers.org/bayesian-nets/)
- [Graph neural networks](https://mlpapers.org/graph-neural-networks/)
- [Meta-learning](https://mlpapers.org/meta-learning/)
- [Generalization](https://mlpapers.org/generalization/)
