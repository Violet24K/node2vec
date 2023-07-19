# node2vec

This is a reimplementation of node2vec algorithm in Python3 (original implementation is in Python2). Original repo: https://github.com/aditya-grover/node2vec


The *node2vec* algorithm learns continuous representations for nodes in any (un)directed, (un)weighted graph. Please check the [project page](https://snap.stanford.edu/node2vec/) for more details. 

### Basic Usage

#### Example
To run *node2vec* on Zachary's karate club network, execute the following command from the project home directory:<br/>
	``python src/main.py --input graph/karate.edgelist --output emb/karate.emd``

A weighted example with manually assigned dimension:<br/>
	``python src/main.py --input 'graph/generate_embedding_wikilens.txt' --output 'emb/wikilens.txt' --weighted --dimensions 300``

#### Options
You can check out the other options available to use with *node2vec* using:<br/>
	``python src/main.py --help``

#### Input
The supported input format is an edgelist:

	node1_id_int node2_id_int <weight_float, optional>
		
The graph is assumed to be undirected and unweighted by default. These options can be changed by setting the appropriate flags.

#### Output
The output file has *n+1* lines for a graph with *n* vertices. 
The first line has the following format:

	num_of_nodes dim_of_representation

The next *n* lines are as follows:
	
	node_id dim1 dim2 ... dimd

where dim1, ... , dimd is the *d*-dimensional representation learned by *node2vec*.

### Citing
If you find *node2vec* useful for your research, please consider citing the following paper:

	@inproceedings{node2vec-kdd2016,
	author = {Grover, Aditya and Leskovec, Jure},
	 title = {node2vec: Scalable Feature Learning for Networks},
	 booktitle = {Proceedings of the 22nd ACM SIGKDD International Conference on Knowledge Discovery and Data Mining},
	 year = {2016}
	}


