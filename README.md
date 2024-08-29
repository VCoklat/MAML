
# ProFONet: Prototypical Feature Space Optimized Network for Few-Shot Classification

## Introduction

Welcome to the official repository for **ProFONet**, presented in our paper titled **"ProFONet: Prototypical Feature Space Optimized Network for Few-Shot Classification"** 📝, accepted at the **27th International Conference of Pattern Recognition** 🎉.

Few-shot learning (FSL) techniques aim to perform well with limited data, but they often face significant challenges such as overfitting and representation collapse, especially when working with imbalanced datasets. Existing inductive methods attempt to learn fine-grained features, but they frequently fail to capture the critical correlations between the support and query embeddings. This results in limited discriminative feature learning, producing sparse prototypes and overlapping decision boundaries, which are less effective in practical applications.

To overcome these limitations, we introduce **ProFONet** 🛠️, a novel approach for training inductive prototypical networks. ProFONet focuses on learning both inter-class and intra-class relationships, which helps to broaden decision boundaries and enhance feature space optimization. By integrating variance, invariance, and covariance regularization techniques, ProFONet produces more discriminative prototype clusters and robust representations that are adaptable to inductive FSL architectures.

## 🧠 Abstract

Conventional Few-shot learning (FSL) techniques often struggle with overfitting and representation collapse, especially with imbalanced datasets. Existing inductive methods try to learn fine-grained features but fail to capture the correlation between the support and query embeddings. This leads to limited discriminative feature learning, resulting in sparse prototypes and overlapping decision boundaries. To address these issues, we propose **Prototypical Feature Optimized Network (ProFONet)**, a novel approach for training inductive prototypical networks that emphasizes learning inter-class and intra-class relationships while broadening decision boundaries. ProFONet integrates variance, invariance, and covariance regularization techniques to optimize feature space, resulting in more discriminative prototype clusters and robust representations. The proposed method exhibits adaptability to inductive FSL architectures and demonstrates superior performance on imbalanced datasets. By preventing collapse and reducing false positives, ProFONet outperforms state-of-the-art methods on the **CUB** benchmark and a newly curated long-tailed medical imaging dataset **GIF**.

## 🌍 Key Contributions

Our contributions in this paper are summarized as follows:

1. **Variance-Invariance-Covariance (VIC) Injected Feature Optimization:** The main contribution of this work is the introduction of **VIC Injected Feature Optimization**. By utilizing a weighted loss function, **VIC Injected ProtoLoss** \(\mathcal{L_\theta}\), ProFONet maintains the information content across each embedding level:
   - **Variance:** Managed by a hinge loss, preserving the standard deviation across the support set, ensuring diverse and rich embeddings.
   - **Invariance:** Enforced through the mean square distance between class embedding vectors, enhancing the robustness and generalization of learned features.
   - **Covariance:** Inspired by Barlow Twins, this regularization combats representation collapse due to embedding redundancy, leading to more effective and discriminative feature representations.

2. **Unified Framework with Fewer Architectural Constraints:** Unlike recent works such as MLVICX, ProFONet offers a more flexible and unified framework without being dependent on specific architectural constraints. This allows ProFONet to yield compact clusters and encourage separation among class prototypes, making it highly adaptable to various feature extractors and inductive FSL architectures.

3. **Performance on Benchmark and Curated Datasets:** We demonstrate the effectiveness of feature space optimization by evaluating the representations learned with ProFONet on the **CUB** dataset. Additionally, we present **GI-Findings (GIF)**, a curated dataset designed for few-shot classification on gastro-intestinal findings, supporting a 5-way 5-shot scenario. ProFONet outperforms state-of-the-art methods on both these datasets, showcasing its superior adaptability and performance.

## 📸 Visual Overview

Here is a key image that illustrates the ProFONet architecture:

![ProFONet Architecture](ProFONet (1)-1.png)
*📷 Fig 1: ProFONet architecture. At the start of each episode of prototypical training, images from the Support set \(S\) and Query set \(Q\) go through the shared encoder \(E_\theta\) and produce embedding points. Distance function learns the prototypes \(P_k\) and forms the clusters from initial embedding. Proposed Feature Optimization (O) generates denser and well-separated clusters of prototypes in \(P_{optimized}\) by inter-class repulsion and intra-class condensation using proposed VIC Injected ProtoLoss \(\mathcal{L_\theta}\). On the top row, the effect of covariance regularization is shown where embedded points are aligned diagonally after feature optimization (Three classes are selected randomly from a novel set).*

## 🚀 Code and Data

The code, training scripts, and datasets used in this paper will be made available soon in this repository. Stay tuned! 🔜

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
