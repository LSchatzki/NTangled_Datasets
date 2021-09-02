# QuMEnt Datasets
Entanglement-based datasets and generators for quantum machine learning.

## Motivation
High quality, large-scale, datasets have played a crucial role in the development and success of classical machine learning.While most proposed novel 
quantum machine learning (QML) architectures are benchmarked using classical datasets, 
there is still doubt if whether QML on classical datasets is the best path towards a quantum advantage. In our work (arxiv link here) we argue that one should 
instead employ  quantum datasets composed of quantum states. For this purpose, we introduce the QuMEnt dataset composed of quantum states with 
different amounts and types of multipartite entanglement.

<img src="https://github.com/LSchatzki/QuMEnt_Datasets/blob/9b652b8f2b1724f98a1fdd218a29e12c71271abd/overview.png" align="right" alt="State generation through parameterized quantum circuits and state classification through quantum convolutional neural networks." width="300"/>

## Data Formatting

All datasets in this repository are provided in both Numpy (.npy) and txt formats. Loading from the .npy files is easiest; simply perform

`data = np.load('path/to/file')`

Data in .txt files requires more careful loading as will be explained below.

Entangled state generator data files have the following naming convention: 'qubits_ansatz_goalCE\* 100_depth_weights.npy(txt)'

## Entangled State Generation and Datasets
Here we consider training a parameterized quantum circuit to output states with a desired amount of entanglement. To quantify entanglement we use the concentratable entanglement, a multipartite entanglement measure (<a href="https://arxiv.org/abs/2104.06923">arXiv:2104.06923</a>).

The datasets consist of trained weights for a hardware efficient (HWE) type ansatz for different number of qubits, layers, and desired amounts of entanglement. Note that the weights take the shape (L,q,i) where L denotes layer, q denotes qubit, and i is in {0,1,2}.

To use this dataset download and load the desired weights into a program. From there use these weights in a HWE ansatz. Generate a state by inputting either a computational basis state or arbitrary product state into the ansatz.

<img src="https://github.com/LSchatzki/QuMEnt_Datasets/blob/d6f5839546b02425b2d405dceb783871eb7fc6a9/generator_hwe_ansatz.png" align="center" alt="State generation through parameterized quantum circuits and state classification through quantum convolutional neural networks." width="300"/>

## Ansatz Depth Learning
This dataset consists of parameters for another HWE ansatz uniformly drawn from 0 to 2pi. The goal here is to determine the depth of ansatz a state came from. While this dataset is easy to generate, we provide random samples here to fascilitate direction comparision between algorithms.
