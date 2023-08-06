# Quantum Neural Networks with Qutrits

This repository contains the code implementation for my thesis titled "Quantum Neural Networks with Qutrits" [^1], which investigates the potential of three-level quantum systems in quantum machine learning. Qutrits offer an expanded state space that enables richer data representation, capturing intricate patterns and relationships. This work introduces the Gell-Mann feature map, which encodes information within an 8-dimensional space, for classification tasks.

## Implementation

![vqc4](https://github.com/Themiscodes/Quantum-Neural-Networks/assets/73662635/8d97619a-4d0c-4513-9e6c-76b5181b93a5)

Parameterized quantum circuits encode input data into quantum states using a feature map, followed by a variational layer with adjustable parameter weights. These parameters are iteratively adjusted using classical optimization methods to minimize a predefined objective function.

### Feature Map

The feature map used in this research employs Gell-Mann rotation operators for the encoding process. The potential of this feature map is explored with a Quantum Kernel method, which, unlike variational circuits, relies solely on data encoding.

In the kernel-based method, a quantum device is used to encode the features of two data points. The inner product and kernel estimation of the encoded data are then used as input for a classical support vector machine for classification. The implementation can be found in the [quantum_kernels](quantum_kernels/) directory.

### Quantum Neural Network

The Quantum Neural Network (QNN) architecture explored in this research comprises stacked layers of Parameterized Quantum Circuits (PQCs), which are analogous to classical perceptrons. This approach is inspired by the paper "Data re-uploading for a universal quantum classifier" [^2].

![qnn](https://github.com/Themiscodes/Quantum-Neural-Networks/assets/73662635/29e4271d-a84c-4c6a-b64f-b41d5ef455fe)

The QNN class, implemented as a PyTorch module, allows for the specification of the number of layers and features during initialization. This design choice enables a modular framework that can be readily adjusted and modified during hyperparameter tuning to align with the underlying geometry of the problem. The implementaion can be found in the [quantum\_neural\_network](quantum_neural_network/) directory.

The effectiveness of increasing the number of qutrits varied across datasets. In some cases, utilizing multiple qutrits led to improved performance, whereas for other datasets, a single qutrit sufficed. These observations are also corroborated by the findings in the paper "Classification of data with a qudit, a geometric approach" [^3].

For more details, please refer to the [thesis](thesis/), which is designed to maintain clarity and accessibility for readers who may not possess prior familiarity with quantum computing. The research provides comprehensive descriptions of each architecture and implementation, while practical demonstrations and insights can be found in the corresponding notebooks.

## References

[^1]: [Quantum Neural Networks with Qutrits](https://pergamos.lib.uoa.gr/uoa/dl/frontend/el/browse/3338218) by Themistoklis Valtinos.

[^2]: [Data re-uploading for a universal quantum classifier](https://arxiv.org/abs/1907.02085) by Adrián Pérez-Salinas, Alba Cervera-Lierta, Elies Gil-Fuster, José I. Latorre.

[^3]: [Classification of data with a qudit, a geometric approach](https://arxiv.org/abs/2307.14060) by A. Mandilara, B. Dellen, U. Jaekel, T. Valtinos and D. Syvridis.
