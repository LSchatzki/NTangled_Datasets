# NTangled Datasets
Entanglement-based quantum datasets and generators for quantum machine learning. <a href="https://arxiv.org/abs/2109.03400">Link to paper</a>.

## Motivation
High quality, large-scale, datasets have played a crucial role in the development and success of classical machine learning. While most proposed novel 
quantum machine learning (QML) architectures are benchmarked using classical datasets, 
there is still doubt if whether QML on classical datasets is the best path towards a quantum advantage. In our work (arxiv link here), we argue that one should 
instead employ quantum datasets composed of quantum states. For this purpose, we introduce the NTangled dataset composed of quantum states with 
different amounts and types of multipartite entanglement.

We generate states by sending product state inputs into parameterized quantum circuits (a) and then classify them through quantum neural networks (b).

<img src="https://github.com/LSchatzki/QuMEnt_Datasets/blob/9b652b8f2b1724f98a1fdd218a29e12c71271abd/overview.png" align="right" alt="State generation through parameterized quantum circuits and state classification through quantum convolutional neural networks." width="300"/>

## Data Formatting

All datasets in this repository are provided in both Numpy (.npy) and txt formats. Loading from the .npy files is easy; simply perform

`data = np.load('path/to/file')`

Data in .txt files is stored in JSON formatting and can be loaded via

`data = json.load('path/to/file')`

Entangled state generator data files have the following naming convention: 'ansatz_qubits_inputtype_(goalCE\* 100)_depth_weights.npy(txt)'

## Entangled State Generation and Datasets
Here we consider training a parameterized quantum circuit to output states with a desired amount of entanglement. To quantify entanglement we use the concentratable entanglement, a multipartite entanglement measure (<a href="https://arxiv.org/abs/2104.06923">arXiv:2104.06923</a>).

The datasets consist of trained weights for three ansatzes--hardware efficient (a), strongly entangling (b), and convolutional (c)--with various numbers of qubits, depths, and goal values of entanglement.

To use this dataset download and load the desired weights. From there, feed states from the input distribution into a parameterized circuit using the provided parameters. The outputs will be entangled states.

Further details about each ansatz, including proper input distributions and pseudocode for implementation, are provided in their respective subfolders.

![Ansatzes for Entangled State Generation](https://github.com/LSchatzki/NTangled_Datasets/blob/main/Assets/generator_ansatzes.png)

## Ansatz Depth Learning
In this task one takes a state generated via some number of layers of an ansatz and tries to determine what depth the ansatz was. Note that the input is not a fixed state, but rather a random product state. We include pseudocode below for the ansatz. Note that CNOT(i,j) indicates a controlled not with register i as the control and j as the target. U3 indicates an arbitrary single qubit unitary on register i.

![Depth Pseudocode](https://github.com/LSchatzki/NTangled_Datasets/blob/main/Assets/depth_learning_hwe_pseudocode.png)
