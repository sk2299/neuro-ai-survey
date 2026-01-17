<div align="center">

# Machine Learning Methods for Studying Latent Neural Activity Dynamics

**Supplementary Appendix for IJCAI 2026 Survey Track Submission**

</div>

---

## 📖 About This Repository

This repository serves as the **Online Appendix** for the survey paper titled **"Machine Learning Methods for Studying Latent Neural Activity Dynamics"**, submitted to the **35th International Joint Conference on Artificial Intelligence (IJCAI 2026)**, Survey Track.

While the main manuscript outlines the theoretical foundations and key advancements in the field, this repository provides a comprehensive, structured, and living catalog of:
1.  **Literature:** A detailed taxonomy of state-of-the-art papers categorized by their modeling focus.
2.  **Datasets:** A curated list of benchmark neural recordings across various species and tasks.
3.  **Metrics:** Standardized evaluation criteria for reconstruction fidelity, dynamical consistency, and behavioral decoding.

---

## 📚 Table of Contents
- [Taxonomy](#-taxonomy)
- [List of Survey Papers](#-list-of-survey-papers)
  - [Single-Region Latent Dynamics](#single-region-latent-dynamics)
  - [Multi-Region Communication in Latent Space](#multi-region-communication-in-latent-space)
  - [Behavior-Aligned Latent Modeling](#behavior-aligned-latent-modeling)
- [Datasets and Benchmarks](#-datasets-and-benchmarks)
- [Metrics](#-metrics)

---

## 🧩 Taxonomy

![taxonomy](figure/taxonomy.png)

---

## 📑 List of Survey Papers

### Single-Region Latent Dynamics

- **Representation learning for neural population activity with neural data transformers**, *arXiv 2021* [[paper](https://arxiv.org/abs/2108.01210)]
  - **Model:** NDT
  - **Problem Setting:** Addresses the temporal processing bottleneck in explicit dynamic models (like RNNs), which impede real-time applications.
  - **Methodology:** Adapts the Transformer architecture to infer discharge rates from noisy neural pulse sequences, replacing sequential RNN processing with parallel self-attention mechanisms.

- **Training biologically plausible recurrent neural networks on cognitive tasks with long-term dependencies**, *NeurIPS 2023* [[paper](https://proceedings.neurips.cc/paper_files/paper/2023/hash/65ccdfe02045fa0b823c5fa7ffd56b66-Abstract-Conference.html)]
  - **Model:** DASC
  - **Problem Setting:** How to train biologically plausible RNNs to perform complex cognitive tasks requiring the learning of long-term temporal dependencies.
  - **Methodology:** Introduces specialized time-jump connections (SCTT and DASC) as auxiliary elements to stabilize gradients during training, which are removed upon completion to restore biological plausibility.

- **Tractable dendritic RNNs for reconstructing nonlinear dynamical systems**, *ICML 2022* [[paper](https://proceedings.mlr.press/v162/brenner22a.html)]
  - **Model:** dendPLRNN
  - **Problem Setting:** Overcoming the limitations of existing deep learning approaches (lack of interpretability and requirement for high-dimensional latent spaces) when inferring nonlinear dynamical systems.
  - **Methodology:** Inspired by dendritic computing, this method enhances the Piecewise Linear RNN (PLRNN) with linear spline basis expansion, enabling the approximation of arbitrary nonlinear systems in lower dimensions with mathematical tractability.

- **Disentangling the Roles of Distinct Cell Classes with Cell-Type Dynamical Systems**, *NeurIPS 2024* [[paper](https://proceedings.neurips.cc/paper_files/paper/2024/hash/3b2fa36f85cda678363cc19cf62b7c5c-Abstract-Conference.html)]
  - **Model:** CTDS
  - **Problem Setting:** Existing latent linear dynamic system (LDS) models often neglect the presence of multiple cell types within neural circuits.
  - **Methodology:** Extends the standard LDS by defining distinct latent variables for each cell type (e.g., Excitatory/Inhibitory) and introducing constraints based on Dale's law to capture functional roles and interactions among cell categories.

- **Inferring Latent Dynamics Underlying Neural Population Activity via Neural Differential Equations**, *ICML 2021* [[paper](https://proceedings.mlr.press/v139/kim21h)]
  - **Model:** PLNDE
  - **Problem Setting:** Addressing the lack of interpretability in existing methods (such as LFADS) when dealing with low data volumes.
  - **Methodology:** Employs Neural Ordinary Differential Equations (Neural ODEs) to construct low-dimensional nonlinear continuous-time dynamics, combined with stochastic jump mechanisms to handle noisy discrete sensory inputs.

- **Inferring single-trial neural population dynamics using sequential auto-encoders**, *Nature Methods 2018* [[paper](https://www.nature.com/articles/s41592-018-0109-9)]
  - **Model:** LFADS
  - **Problem Setting:** Accurately inferring underlying neural population dynamics and precise instantaneous firing rates from noisy single-trial neural spike data.
  - **Methodology:** A sequential variant of Variational Autoencoders (VAEs) based on nonlinear RNNs. It models neural data as a dynamic system, inferring dynamics by modeling the latent state, initial conditions, and inputs.

- **Empirical models of spiking in neural populations**, *NIPS 2011* [[paper](https://proceedings.neurips.cc/paper_files/paper/2011/hash/7143d7fbadfa4693b9eec507d9d37443-Abstract.html)]
  - **Model:** PLDS
  - **Problem Setting:** Determining whether to use a "directly coupled GLM" or a "low-dimensional latent variable + dynamic system" to explain shared variability in simultaneous cortical recordings.
  - **Methodology:** Constructs the Poisson-Linear Dynamic System (PLDS) and learns parameters using EM combined with a global Laplace approximation.

- **Gaussian-process factor analysis for low-dimensional single-trial analysis of neural population activity**, *NIPS 2008* [[paper](https://proceedings.neurips.cc/paper/2008/hash/ad972f10e0800b49d76fed33a21f6698-Abstract.html)]
  - **Model:** GPFA
  - **Problem Setting:** Extracting smooth, low-dimensional neural trajectories from high-noise, high-dimensional activity in single trials.
  - **Methodology:** Unifies time smoothing (Gaussian Process) and dimensionality reduction (Factor Analysis) in a probabilistic framework to model multi-timescale dynamics.

- **Variational latent gaussian process for recovering single-trial dynamics from population spike trains**, *Neural Computation 2017* [[paper](https://direct.mit.edu/neco/article-abstract/29/5/1293/8259/Variational-Latent-Gaussian-Process-for-Recovering)]
  - **Model:** vLGP
  - **Problem Setting:** Extracting interpretable low-dimensional latent dynamics while capturing interactive relationships between brain regions.
  - **Methodology:** Infers continuous latent states using variational inference that maximizes the ELBO, employing incomplete Cholesky decomposition to optimize computational complexity.

- **A large-scale neural network training framework for generalized estimation of single-trial population dynamics**, *Nature Methods 2022* [[paper](https://www.nature.com/articles/s41592-022-01675-0)]
  - **Model:** AutoLFADS
  - **Problem Setting:** Overcoming the inefficiency of manual hyperparameter tuning in LFADS to enable large-scale estimation and generalization.
  - **Methodology:** An unsupervised automated model tuning framework using Coordinated Dropout and Population-Based Training for large-scale hyperparameter search.

- **Bayesian learning and inference in recurrent switching linear dynamical systems**, *AISTATS 2017* [[paper](https://proceedings.mlr.press/v54/linderman17a.html)]
  - **Model:** rSLDS
  - **Problem Setting:** Modeling complex behavioral pattern switching where state transitions depend on continuous latent variables or observations, rather than just the preceding discrete state.
  - **Methodology:** Proposes a recursive SLDS using stick-breaking logistic regression for transition probabilities and Polya-gamma auxiliary variables to enable efficient block Gibbs sampling.

- **Modeling Latent Neural Dynamics with Gaussian Process Switching Linear Dynamical Systems**, *NeurIPS 2024* [[paper](https://arxiv.org/abs/2408.03330)]
  - **Model:** gpSLDS
  - **Problem Setting:** Recovering smooth, structured nonlinear latent dynamics with uncertainty estimates while avoiding the "unnatural oscillations" at boundaries found in rSLDS.
  - **Methodology:** Uses a Smooth Switching Linear (SSL) kernel function within Gaussian Process SDEs to generate smoothly varying, locally linear dynamics.

- **Expressive dynamics models with nonlinear injective readouts enable reliable recovery of latent features from neural activity**, *arXiv 2023* [[paper](https://pmc.ncbi.nlm.nih.gov/articles/PMC10516113/)]
  - **Model:** ODIN
  - **Problem Setting:** Addressing non-injectivity in the mapping between latent space and neural space, which renders representations non-interpretable.
  - **Methodology:** Uses Neural ODEs for latent evolution and maps to neural space via a structure analogous to a reversible residual network, trained by maximizing Poisson likelihood.

- **Inferring stochastic low-rank recurrent neural networks from neural data**, *NeurIPS 2024* [[paper](https://arxiv.org/abs/2406.16749)]
  - **Model:** SLRNN
  - **Problem Setting:** Fitting random low-rank RNNs to noisy data to capture inter-trial variability and efficiently analyzing fixed points in polynomial time.
  - **Methodology:** Proposes Variational Sequential Monte Carlo (VSMC) for fitting stochastic low-rank RNNs and provides an analytical method for computing fixed points at polynomial cost.

- **Identifying signal and noise structure in neural population activity with Gaussian process factor models**, *NeurIPS 2020* [[paper](https://proceedings.neurips.cc/paper_files/paper/2020/hash/9eed867b73ab1eab60583c9d4a789b1b-Abstract.html)]
  - **Model:** SNP-GPFA
  - **Problem Setting:** Simultaneously separating "signal" structure locked to the stimulus from "noise" structure arising from random fluctuations.
  - **Methodology:** Combines Gaussian process factor models with Poisson observations using Fourier-domain black-box variational inference to estimate shared signal and trial-specific noise variables.

### Multi-Region Communication in Latent Space

- **Disentangling the flow of signals between populations of neurons**, *Nature Computational Science 2022* [[paper](https://www.nature.com/articles/s43588-022-00282-5)]
  - **Model:** DLAG
  - **Problem Setting:** Decoupling simultaneous, bidirectional inter-region signal flows from concurrent recordings.
  - **Methodology:** A probabilistic framework utilizing Gaussian processes and linear dimensionality reduction.

- **Multi-Region Markovian Gaussian Process: An Efficient Method to Discover Directional Communications Across Multiple Brain Regions**, *ICML 2024* [[paper](https://pmc.ncbi.nlm.nih.gov/articles/PMC11526605/)]
  - **Model:** MRM-GP
  - **Problem Setting:** Efficiently identifying directional communication within high-dimensional neural activity.
  - **Methodology:** Combines Gaussian processes and linear dynamic systems to enhance efficiency and interpretability.

- **Uncovering motifs of concurrent signaling across multiple neuronal populations**, *NeurIPS 2023* [[paper](https://proceedings.neurips.cc/paper_files/paper/2023/hash/6cf7a37e761f55b642cf0939b4c64bb8-Abstract-Conference.html)]
  - **Model:** mDLAG
  - **Problem Setting:** Characterizing multidimensional signal flows among more than two neuronal populations.
  - **Methodology:** A multi-brain-region extension of DLAG.

- **NONLINEAR MULTIREGION NEURAL DYNAMICS WITH PARAMETRIC IMPULSE RESPONSE COMMUNICATION CHANNELS**, *ICLR 2025* [[paper](https://openreview.net/forum?id=LbgIZpSUCe)]
  - **Model:** MRDS-IR
  - **Problem Setting:** Understanding how regions collectively support distributed computation and extracting interpretable dynamic structures.
  - **Methodology:** Combines nonlinear local dynamics with linear communication channels parameterized by impulse response.

- **CREIMBO: Cross-Regional Ensemble Interactions in Multi-view Brain Observations**, *ICLR 2025* [[paper](https://par.nsf.gov/biblio/10616080)]
  - **Model:** CREIMBO
  - **Problem Setting:** Integrating non-simultaneous and non-aligned data across different subjects and sessions.
  - **Methodology:** Uses multi-perspective learning and the shared subcircuit hypothesis to align cross-session ensembles through graph-driven dictionary learning.

- **Modeling state-dependent communication between brain regions with switching nonlinear dynamical systems**, *ICLR 2024* [[paper](https://openreview.net/forum?id=WQwV7Y8qwa)]
  - **Model:** MR-SDS
  - **Problem Setting:** Modeling complex, state-dependent interactions with a focus on interpretability.
  - **Methodology:** Introduces discrete states and quantifiable "messages" to analyze directed information flows.

- **Learning Time-Varying Multi-Region Brain Communications via Scalable Markovian Gaussian Processes**, *ICML 2025* [[paper](https://openreview.net/forum?id=pOAEfqa26i)]
  - **Model:** ADM
  - **Problem Setting:** Capturing communication patterns and temporal delays over time with high computational efficiency.
  - **Methodology:** Links stationary Gaussian processes (GP) and state-space models (SSM), introducing continuous time-varying delay parameters.

- **Accurate Identification of Communication Between Multiple Interacting Neural Populations**, *ICML 2025* [[paper](https://arxiv.org/abs/2506.19094)]
  - **Model:** MR-LFADS
  - **Problem Setting:** Distinguishing influence sources (inter-region vs. unobserved input vs. local dynamics).
  - **Methodology:** A Sequential Variational Autoencoder (SVAE) extending LFADS with specific latent variable structures to disentangle sources of influence.

- **MARBLE: interpretable representations of neural population dynamics using geometric deep learning**, *Nature Methods 2025* [[paper](https://www.nature.com/articles/s41592-024-02582-2)]
  - **Model:** MARBLE
  - **Problem Setting:** Extracting consistent latent representations to compare dynamics across conditions/systems without behavioral supervision.
  - **Methodology:** Decomposes dynamics into local flow fields (LFFs) and maps them to a shared space using unsupervised geometric deep learning.

- **Identifying interactions across brain areas while accounting for individual-neuron dynamics with a Transformer-based variational autoencoder**, *NeurIPS 2025* [[paper](https://arxiv.org/abs/2506.02263)]
  - **Model:** GLM-Transformer
  - **Problem Setting:** Isolating genuine cross-region interaction signals amidst non-stationary individual neuron dynamics.
  - **Methodology:** Transformer-based VAE modeling trial-by-trial dynamics while retaining GLM interpretability.

- **Between-area communication through the lens of within-area neuronal dynamics**, *Science Advances 2024* [[paper](https://www.science.org/doi/10.1126/sciadv.adl6120)]
  - **Model:** Structured SNN + RRR
  - **Problem Setting:** Distinguishing whether shared dynamics arise from local emergence or upstream inheritance.
  - **Methodology:** Uses a three-layer feedforward-recursive SNN to control E/I balance, Factor Analysis for shared covariance, and Rank Reduction Regression (RRR) to evaluate predictive power.

- **Recurrent Switching Dynamical Systems Models for Multiple Interacting Neural Populations**, *NeurIPS 2020* [[paper](https://proceedings.neurips.cc/paper/2020/hash/aa1f5f73327ba40d47ebce155e785aaf-Abstract.html)]
  - **Model:** mp-srSLDS
  - **Problem Setting:** Capturing low-dimensional latent states, interactions, and non-stationarity simultaneously.
  - **Methodology:** Extends rSLDS by assigning dedicated latent variables to populations and parametrizing discrete state rules to define driving populations.

- **Rethinking brain-wide interactions through multi-region ‘network of networks’ models**, *Current Opinion in Neurobiology 2020* [[paper](https://www.sciencedirect.com/science/article/pii/S0959438820301707)]
  - **Model:** mRNNs
  - **Problem Setting:** Moving beyond hierarchical/isolated node models to account for complex recursive connections.
  - **Methodology:** A multi-region "network-of-networks" model optimized using connectome data.

- **Towards a “universal translator” for neural dynamics at single-cell, single-spike resolution**, *NeurIPS 2024* [[paper](https://proceedings.neurips.cc/paper_files/paper/2024/hash/934eb45b99eff8f16b5cb8e4d3cb5641-Abstract-Conference.html)]
  - **Model:** MtM
  - **Problem Setting:** Creating a foundational model for neural dynamics that generalizes across regions and scales.
  - **Methodology:** Uses Multi-Task-Masking (MtM) with alternating masking strategies and a learnable prompt token within a Transformer architecture.

- **Feedforward and feedback interactions between visual cortical areas use different population activity patterns**, *Nature Communications 2022* [[paper](https://www.nature.com/articles/s41467-022-28552-w)]
  - **Model:** CCA
  - **Problem Setting:** Determining if feedforward and feedback signals communicate through the same low-dimensional subspaces.
  - **Methodology:** Uses time delay analysis and Common Component Analysis (CCA) to compare subspaces.

- **Multiplexed subspaces route neural activity across brain-wide networks**, *Nature Communications 2025* [[paper](https://www.nature.com/articles/s41467-025-58698-2)]
  - **Model:** RRR-based
  - **Problem Setting:** Uncovering mechanisms determining brain network activation and dynamic alignment.
  - **Methodology:** Combines Neuropixels and wide-field calcium imaging with Reduced-Rank Regression (RRR) and CNMF to identify subspace dimensions.

### Behavior-Aligned Latent Modeling

- **Learnable latent embeddings for joint behavioural and neural analysis**, *Nature 2023* [[paper](https://www.nature.com/articles/s41586-023-06031-6)]
  - **Model:** CEBRA
  - **Problem Setting:** Learning consistent neural representations across animals/sessions linked to behavior.
  - **Methodology:** Contrastive learning utilizing behavioral or temporal information as supervision.

- **Dissociative and prioritized modeling of behaviorally relevant neural dynamics using recurrent neural networks**, *Nature Neuroscience 2024* [[paper](https://www.nature.com/articles/s41593-024-01731-2)]
  - **Model:** DPAD
  - **Problem Setting:** Isolating and prioritizing dynamics directly related to behavior.
  - **Methodology:** A four-step optimization method to decompose dynamics into behavior-related and behavior-irrelevant components.

- **BRAID: Input-driven Nonlinear Dynamical Modeling of Neural-Behavioral Data**, *arXiv 2025* [[paper](https://pmc.ncbi.nlm.nih.gov/articles/PMC12486053/)]
  - **Model:** BRAID
  - **Problem Setting:** Distinguishing between "intrinsic dynamics" and "externally input-driven dynamics" (building on DPAD).
  - **Methodology:** Explicitly models external inputs and uses a multi-step prediction training strategy.

- **Neural Encoding and Decoding at Scale**, *arXiv 2025* [[paper](https://arxiv.org/abs/2504.08201)]
  - **Model:** NEDS
  - **Problem Setting:** Constructing a unified model for large-scale encoding and decoding.
  - **Methodology:** A unified multimodal, multi-task model learning encoding and decoding simultaneously.

- **Latent Diffusion for Neural Spiking Data**, *NeurIPS 2024* [[paper](https://arxiv.org/abs/2407.08751)]
  - **Model:** LDNS
  - **Problem Setting:** Generating realistic neural spikes from low-dimensional latent representations.
  - **Methodology:** Encodes discrete pulse data into continuous latent representation and trains a conditional diffusion model.

- **Exploring Behavior-Relevant and Disentangled Neural Dynamics with Generative Diffusion Models**, *NeurIPS 2024* [[paper](https://arxiv.org/abs/2410.09614)]
  - **Model:** BeNeDiff
  - **Problem Setting:** Overcoming mixed selectivity to reveal interpretable behavior-associated dynamics.
  - **Methodology:** Uses a behavior-guided LVM to identify a decoupled subspace, followed by generative diffusion models to synthesize behavioral videos.

- **Robust alignment of cross-session recordings of neural population activity by behaviour via unsupervised domain adaptation**, *ICML 2022* [[paper](https://proceedings.mlr.press/v162/jude22a.html)]
  - **Model:** SABLE
  - **Problem Setting:** Recovering stable latent dynamics from unseen session data without retraining.
  - **Methodology:** Combines sequential VAE with unsupervised domain adaptation (backpropagation layers).

- **Neural Latent Aligner: Cross-trial Alignment for Learning Representations of Complex, Naturalistic Neural Data**, *ICML 2023* [[paper](https://proceedings.mlr.press/v202/cho23a.html)]
  - **Model:** NLA
  - **Problem Setting:** Learning behavior-relevant, cross-trial consistent representations from naturalistic data.
  - **Methodology:** Aligns trials using contrastive learning and a differentiable temporal alignment model (TWM).

- **Geometry Linked to Untangling Efficiency Reveals Structure and Computation in Neural Populations**, *bioRxiv 2024* [[paper](https://pubmed.ncbi.nlm.nih.gov/40236228/)]
  - **Model:** GLUE
  - **Problem Setting:** Quantifying "untangling" in category manifolds and uncovering geometric mechanisms.
  - **Methodology:** Uses manifold capacity theory and geometric metrics (radius, dimension, alignment) to analyze computational efficiency.

- **Modeling behaviorally relevant neural dynamics enabled by preferential subspace identification**, *Nature Neuroscience 2021* [[paper](https://www.nature.com/articles/s41593-020-00733-0)]
  - **Model:** PSID
  - **Problem Setting:** Distinguishing behavior-related dynamics from behavior-irrelevant dynamics that may mask them.
  - **Methodology:** A two-stage linear state-space model projecting "future actions" onto "past neural activity" to prioritize relevant latent variables.

- **A Unified, Scalable Framework for Neural Population Decoding**, *NeurIPS 2023* [[paper](https://proceedings.neurips.cc/paper_files/paper/2023/hash/8ca113d122584f12a6727341aaf58887-Abstract-Conference.html)]
  - **Model:** POYO
  - **Problem Setting:** Generalizing decoding across animals, experiments, and neuronal ensembles.
  - **Methodology:** Tokenizes neural spikes and uses PerceiverIO with a cross-attention query mechanism for decoding.

- **Extracting computational mechanisms from neural data using low-rank RNNs**, *NeurIPS 2022* [[paper](https://proceedings.neurips.cc/paper_files/paper/2022/hash/9877d915a4b4f00e85e7b4cfdf41e450-Abstract-Conference.html)]
  - **Model:** LINT
  - **Problem Setting:** Extracting interpretable dynamics to reveal interactive mechanisms and correlate with behavior.
  - **Methodology:** Uses "explainable low-rank RNNs" to reverse-engineer connection structures data-drivenly.

- **Inference of Neural Dynamics Using Switching Recurrent Neural Networks**, *NeurIPS 2024* [[paper](https://proceedings.neurips.cc/paper_files/paper/2024/hash/ed8baaf9059a5cee3ffe56cedbf26f69-Abstract-Conference.html)]
  - **Model:** SRNN
  - **Problem Setting:** Recovering time-switching nonlinear latent dynamics and detecting behavior-related discrete states.
  - **Methodology:** A generative state-space model where RNN weights switch according to a discrete latent state, trained via variational inference.

- **Modeling and dissociation of intrinsic and input-driven neural population dynamics underlying behavior**, *PNAS 2024* [[paper](https://www.pnas.org/doi/abs/10.1073/pnas.2212887121)]
  - **Model:** IPSID
  - **Problem Setting:** Separating intrinsic vs. input-driven dynamics to avoid misinterpretation due to neglected inputs.
  - **Methodology:** Extends PSID to model inputs explicitly, performing oblique projections of future actions onto "past neural activity + past inputs".

- **Modeling conditional distributions of neural and behavioral data with masked variational autoencoders**, *Cell Reports 2025* [[paper](https://www.sciencedirect.com/science/article/pii/S2211124725001093)]
  - **Model:** masked VAE
  - **Problem Setting:** Modeling conditional distributions in high-dimensional data while maintaining interpretability.
  - **Methodology:** Introduces structured masking during VAE training to model conditional distributions even with missing data.

- **Multiscale low-dimensional motor cortical state dynamics predict naturalistic reach-and-grasp behavior**, *Nature Communications 2021* [[paper](https://www.nature.com/articles/s41467-020-20197-x)]
  - **Model:** Multiscale Dynamical Model
  - **Problem Setting:** Revealing relationships between motor cortex activity and naturalistic behavior.
  - **Methodology:** Integrates spiking activity and LFP using an unsupervised multiscale EM algorithm.

---

## 💯 Datasets and Benchmarks

### Task: Reaching

| Dataset | Size | Species | Subjects | Input | Output | Description |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **pmd-1** [[Link](https://crcns.org/data-sets/motor-cortex/pmd-1/about-pmd-1)] | 385 MB | Macaque | 2 | Cursor pos/vel/acc | PMd/M1 activity | Sequential reaching task recordings |
| **alm-3** [[Link](https://crcns.org/data-sets/motor-cortex/alm-3/about-alm-3)] | ~12 GB | Mouse | 19 | ALM recordings | Spikes, optogenetics | Premotor cortex dynamics in planning |
| **MC_RTT** [[Link](https://dandiarchive.org/dandiset/000129)] | 48.6 MiB | Rhesus | 1 | Spike times, pos | Sorted spikes | Self-paced reaching in 8x8 grid |
| **NHP Reaching** [[Link](https://zenodo.org/records/3854034)] | 24 GB | Monkey | 2 | M1/S1 spikes | Position | Self-paced reaching in grid-target task |
| **Reaching Dynamics** [[Link](https://dandiarchive.org/dandiset/000070/)] | 49.7 GiB | Rhesus | 2 | M1/PMd spikes | Spikes, position | Population activity, right-hand reaching |

### Task: Maze / Spatial

| Dataset | Size | Species | Subjects | Input | Output | Description |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **MC_Maze** [[Link](https://dandiarchive.org/dandiset/000128)] | 662 MiB | Rhesus | 1 | Neural + behavior | Sorted spikes | Maze reaching, straight & curved dynamics |
| **hc-2** [[Link](https://crcns.org/data-sets/hc/hc-2/about-hc-2)] | 136 GB | Rat | 3 | Hippocampal + video | LFP, spikes, pos | Open field foraging task |
| **hc-11** [[Link](https://crcns.org/data-sets/hc/hc-11/about-hc-11)] | 8 sess | Rat | 4 | Spikes, LFP, EMG | CA1 firing, LFPs | Maze learning + rest recordings |

### Task: Visual / Stimulus

| Dataset | Size | Species | Subjects | Input | Output | Description |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **pvc-11** [[Link](https://crcns.org/data-sets/vc/pvc-11/about)] | 180 MB | Macaque | 4-5 | Visual stimuli | Spike times | V1 visual neuron responses |
| **v1v2-1** [[Link](https://crcns.org/data-sets/vc/v1v2-1/about_v1v2-1)] | 143 MB | Macaque | 3 | Oriented gratings | Spikes V1/V2 | Anesthetized V1/V2 recordings |
| **Allen Visual Coding** [[Link](https://allensdk.readthedocs.io/en/latest/visual_coding_neuropixels.html)] | 855 GB | Mouse | 58 | Visual stimuli | Spikes, LFP | Multi-region mouse brain visual recordings |
| **Steinmetz 2019** [[Link](https://figshare.com/articles/dataset/Steinmetz_et_al_2019_dataset/9598406)] | 8.25 GB | Mouse | / | Stimulus, wheel | Spikes + behavior | Visual perception and behavior |

### Task: Memory / Cognitive

| Dataset | Size | Species | Subj | Input | Output | Description |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Mesoscale Map** [[Link](https://dandiarchive.org/dandiset/000363/0.231012.2129)] | 59.8 TiB | Mouse | 28 | Ephys + behavior | Spikes, behavior | Memory-guided movement across regions |
| **Decision Term.** [[Link](https://zenodo.org/records/7946011)] | 565 MB | Monkey | 2 | Neural + behavior | Decision analysis | Decision termination study replication |

### Task: Motor Perturbation / Force

| Dataset | Size | Species | Subj | Input | Output | Description |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Area2_Bump** [[Link](https://dandiarchive.org/dandiset/000127)] | 1.7 GiB | Rhesus | 1 | Kinematics, bumps | Area 2 spikes | Reaching with perturbations |
| **DMFC_RSG** [[Link](https://dandiarchive.org/dandiset/000130)] | 14.9 MiB | Rhesus | 1 | Interval stimuli | Spike times | Time interval reproduction |

### Task: Neural Recording

| Dataset | Size | Species | Subj | Input | Output | Description |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **EEG Motor** [[Link](https://physionet.org/content/eegmmidb/1.0.0/)] | 3.4 GB | Human | 109 | 64-ch EEG | Motion onset | Real/imagined hand/foot movement |
| **Fly Walking** [[Link](https://zenodo.org/records/11002776)] | 3.4 GB | Fly | 3 | Video tracking | Timeseries | 2D arena walking behavior |
| **Multiplexed** [[Link](https://datadryad.org/dataset/doi:10.5061/dryad.gxd2547x8)] | 13.6 GB | Mouse | 3 | Ca2+, spikes | Subspace nets | Cortex-wide Ca + Neuropixels |
| **Mesoscale** [[Link](https://datadryad.org/dataset/doi:10.5061/dryad.ttdz08m0z)] | 785 MB | Mouse | / | Widefield Ca2+ | Lever pulls | Pre-movement cortical dynamics |
| **MARBLE Rep.** [[Link](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/KTE4PC)] | 8.6 GB | Macaque | / | Spikes, kinem. | Embeddings | MARBLE model replication data |
| **Kato2015** [[Link](https://osf.io/2395t/overview)] | 145 MB | C. elegans | / | Neural traces | Corrected traces | Whole-brain calcium imaging |
| **Brainwide Map** [[Link](https://www.internationalbrainlab.com/data)] | Large | Mouse | Multi | Ephys + behavior | Neural patterns | Cross-brain neural activity |
| **Repro. Ephys** [[Link](https://docs.internationalbrainlab.org/notebooks_external/2024_data_release_repro_ephys.html)] | 91 sess | Mouse | / | Signals + behavior | Raw signals | Multi-lab Neuropixels reproducibility |

---

## 🧪 Metrics

| Category | Metric | Definition | Evaluation Focus |
| :--- | :--- | :--- | :--- |
| **Reconstruction** | **Poisson NLL** | Negative log-likelihood under Poisson model on held-out data | Statistical fidelity of modeling |
| | **Log-Likelihood** | Log probability of observed data given model | Generative modeling quality |
| | **Co-smoothing R²**
