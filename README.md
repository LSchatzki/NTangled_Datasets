# NTangled Datasets
Entanglement-based quantum datasets and generators for quantum machine learning.

## Motivation
High quality, large-scale, datasets have played a crucial role in the development and success of classical machine learning. While most proposed novel 
quantum machine learning (QML) architectures are benchmarked using classical datasets, 
there is still doubt if whether QML on classical datasets is the best path towards a quantum advantage. In our work (arxiv link here), we argue that one should 
instead employ quantum datasets composed of quantum states. For this purpose, we introduce the NTangled dataset composed of quantum states with 
different amounts and types of multipartite entanglement.

<img src="https://github.com/LSchatzki/QuMEnt_Datasets/blob/9b652b8f2b1724f98a1fdd218a29e12c71271abd/overview.png" align="right" alt="State generation through parameterized quantum circuits and state classification through quantum convolutional neural networks." width="300"/>

## Data Formatting

All datasets in this repository are provided in both Numpy (.npy) and txt formats. Loading from the .npy files is easy; simply perform

`data = np.load('path/to/file')`

Data in .txt files is stored in JSON formatting and can be loaded via

`data = json.load('path/to/file')`

Entangled state generator data files have the following naming convention: 'ansatz_qubits_inputtype_(goalCE\* 100)_depth_weights.npy(txt)'

![test](https://github.com/LSchatzki/NTangled_Datasets/Assets/generator_ansatzes.png)

## Entangled State Generation and Datasets
Here we consider training a parameterized quantum circuit to output states with a desired amount of entanglement. To quantify entanglement we use the concentratable entanglement, a multipartite entanglement measure (<a href="https://arxiv.org/abs/2104.06923">arXiv:2104.06923</a>).

The datasets consist of trained weights for three ansatzes--hardware efficient, strongly entangling, and convolutional--with various numbers of qubits, depths, and goal values of entanglement.

To use this dataset download and load the desired weights. From there, feed states from the input distribution into a parameterized circuit using the provided parameters. The outputs will be entangled states.

Further details about each ansatz, including proper input distributions and pseudocode for implementation, are provided in their respective subfolders.

## Ansatz Depth Learning
This dataset consists of parameters for another HWE ansatz uniformly drawn from 0 to 2pi. The goal here is to determine the depth of ansatz a state came from. While this dataset is easy to generate, we provide random samples here to fascilitate direction comparision between algorithms.
