# QuMEnt Datasets
Entanglement-based datasets and generators for quantum machine learning.

## Motivation
High quality, large-scale, datasets have played a crucial role in the development and success of classical machine learning.While most proposed novel 
quantum machine learning (QML) architectures are benchmarked using classical datasets, 
there is still doubt if whether QML on classical datasets is the best path towards a quantum advantage. In our work (arxiv link here) we argue that one should 
instead employ  quantum datasets composed of quantum states. For this purpose, we introduce the QuMEnt dataset composed of quantum states with 
different amounts and types of multipartite entanglement.

## Data Formatting

All datasets in this repository are provided in both Numpy (.npy) and txt formats. Loading from the .npy files is easiest; simply perform

`data = np.load('path/to/file')`

Data in .txt files requires more careful loading as will be explained below.

## Entangled State Generation and Datasets

## Ansatz Depth Learning
