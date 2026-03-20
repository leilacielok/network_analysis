# Network Analysis Project
This project analyzes the structure of a political interaction network on Twitter. The dataset represents interactions between members of the U.S. Congress and is used to study the structural properties of the network using tools from network science.

For this network analysis, data from Twitter of the Congressional network was used. The dataset was collected using the Twitter API and is available at: https://snap.stanford.edu/data/congress-twitter.html.

This dataset was introduced by Christian G. Fink et al. (2023) and models influence dynamics through weighted, directed edges, where weights represent transmission probabilities between nodes.

The file congress_network_data.json contains the following data:

* inList: list of lists such that inList[i] is a list of all the nodes sending connections TO node i
* inWeight: list of lists containing the connection weights (transmission probabilities) corresponding to the connections in inList
* outList: list of lists such that outList[i] is a list of all the nodes receiving connections FROM node i
* outWeight: list of lists containing the connection weights (transmission probabilities) corresponding to the connections in outList
* usernameList[i] gives the Twitter username corresponding to node i

The file congress.edgelist contains the weighted, directed edgelist for the Congressional network, in NetworkX format

## Repository Structure
This repository contains the following files:

#### `network_analysis.ipynb`
Main notebook containing the complete network analysis.
The analysis includes:

- loading and preprocessing the network
- basic network statistics (nodes, edges, density, connectivity)
- connectivity analysis
- degree distribution analysis
- comparison with an Erdős–Rényi random null model
- clustering coefficient analysis
- bridge detection and analysis of structural bridges
- centrality measures (degree, betweenness, closeness, PageRank)
- community detection using the Louvain method
- node classification using machine learning methods:
    - representation learning with Node2Vec embeddings
    - structural feature extraction using Graphlet Degree Vectors (GDV)
    - performance comparison between embedding-based and structural feature approaches
 
#### `gdv_features.ipynb`
This notebook is used to compute Graphlet Degree Vector (GDV) features for the nodes of the network using the ORCA orbit-counting algorithm.

Due to compatibility issues when compiling ORCA on Windows, this notebook was executed in Google Colab, where the orbit-counting binary could be compiled and run correctly. The notebook therefore serves mainly to:

- download and compile the ORCA orbit-counting tool
- compute orbit counts for each node
- generate the GDV feature vectors used in the node classification task

The resulting GDV features are then used in the main analysis notebook for comparison with Node2Vec embeddings.

## Reproducibility
1. Install the required dependencies: `pip install -r requirements.txt`
2. Download the dataset from SNAP website.
3. Run the notebook: `network_analysis.ipynb`

