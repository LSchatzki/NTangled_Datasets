To fascilitate usage of this dataset we provide pseudocode for all ansatzes and operations within those ansatzes.

First, some notation. CNOT(i,j) indicates a controlled not with register i as control and j as target. CZ(i,j) indicates a controlled Z on i and j. 2QU indicates an arbitrary 2 qubit unitary (see decomposition below), and U3 indicates an arbitrary 1 qubit unitary.

We use the following single qubit unitary decomposition:
U3(i;θ,ϕ,λ) = Rz(ϕ)Rx(-𝜋/2)Rz(θ)Rx(𝜋/2)Rz(λ)

![2qu](https://github.com/LSchatzki/NTangled_Datasets/blob/main/Assets/two_qubit_unitary_pseudocode.png)
![hwe](https://github.com/LSchatzki/NTangled_Datasets/blob/main/Assets/hwe_gen_pseudocode.png)
![sea](https://github.com/LSchatzki/NTangled_Datasets/blob/main/Assets/sea_gen_pseudocode.png)
![conv](https://github.com/LSchatzki/NTangled_Datasets/blob/main/Assets/conv_gen_pseudocode.png)
![depth_learning](https://github.com/LSchatzki/NTangled_Datasets/blob/main/Assets/depth_learning_hwe_pseudocode.png)
