# Network Construction Techniques

Summary: before applying the machine learning on complex graph, this network needs constructed from unstructured data such as from vector based data or time series data.

1. Introductions:

Vector based data is a set of items which can have an inter related data without intra vectors. If we try to combine these relationships into vector, it can loss information or becomes complex. Network is components obtaining the relation data such as social network (Facebook, Twitter), customer - purchase - items set, drugs design,etc (refer to Unstructure vs. Structure data diagram at Fig1)

<img title='Fig. 1 Unstructure vs. Structure data &[1&]' src='https://github.com/mbuihuynh/GNN/blob/main/images/rpt1_GraphPresent.png' width="1000" alt='Unstructure vs. Structure data'>

Each item in dataset can be presented by a node in network. Edges are created by obtaining the similarity among data items. <br>

To time series data, similarity definition declared to state recurrence x(i), when state x(j) at time j is similiarity to state x(i) in allowed threashold epsilon.


2. Network Construction Techniques:
- Similarity/Dissimilarity functions <br>
Informally, similarity/dissimilarity express a comparision between two data items. Conceptually, similarity function measures divergence/coincidence value between two elements in a given domain: 
  - Simiarity function f: AxA -> Rs. &exist;a: s(x,y) <= a. Closedness property: s(x,y) = s_min
  - Dissimilarity function f: AxA -> Rd. &exist;a: d(x,y) >= a. Closedness property: d(x,y) = d_max
  - Some popular techniques for distance measures: depending on data types (categorical, numerical data), there are reasonable measures
    - Numerical data: Euclidean distance, Manhattan, Chebyshev (max of elements), Minkowski distance (generalization of Euclidean, Manhattan), Gaussian kernel similarity, Cosine similarity
    - Categorical data: Hamming distance, Jaccard similarity

- Transforming Vector-based data into Networks <br>
  - How to define the related items into network, using k-NN or epsilon radius techniques
  - b-matching network: to ensure each node in network has #edges to create balance graph.
  - k-NN technique applied to build network
  <img title='Fig. 2 k-NN technique' src='https://github.com/mbuihuynh/GNN/blob/main/images/rpt1_kNN.png' width="1000" >
  - Epsilon radius technique applied to build network
  <img title='Fig. 3 Epsilon radius technique' src='https://github.com/mbuihuynh/GNN/blob/main/images/rpt1_epsilon.png' width="1000" >

- Transforming time series-based data into Networks <br>
  - Cycle network: studying about topological features of time series.
  - Correlation network: presented time series as state vector and used the Pearson correlation coefficient.
  - Recurrence network: adjacency matrices are defined by the recurrence matrics of time series.
  - Transition network: a network is a single time series, then build transition network to find the varying signal margin to another time series.


3. Graph Presentation/Embedded [2]:

Opposite to the graph construction, there are some approaches to represent the graph/subgraph/nodes/edges in vector and then applied the machine learning that called as graph embedding or feature representation. It's upon on specified tasks that we can present the according components in graph into vector. For example, node embedding for node classification/clustering, edge embedding for link prediction, hybrid of nodes and edges for sub-graph/community learning.
- The first-order proximity/relation in a network is the weighted edge linked by two nodes. The task is obtained by minimizing the distance between the joint probability distribution in the vector space.
- The second-order relation in a network is other relationship between two nodes such as the nodes share similar neighborhood structures.
<img title='Fig. 3 Graph presentation' src='https://github.com/mbuihuynh/GNN/blob/main/images/rpt1_graph_to_vector.png' width="500" >

- Graph embedded techniques
  - Dimensionality reduction
  - Random walk
  - Matrix factorization
  - Neural networks: applying the CNN/RNN techniques to transform the graph/nodes/edges into vector. Some recently prominent works are,
    + Node2vec: this paper used the sample strategy (random walk) to generate the directed sub-graph
    + GraphSAGE is induction framework learnt to recognize structure properties of node's neighborhood representing local roles in graph and global position. We can image the node's neighborhood feature as context features. This approach learnt the aggregation function of a number of different hops or search depth from neighborhood and design the unsupervised loss function to train this framework without specified tasks. GraphSAGE is tested cross domains such as Citation, Reddit to predict paper/post categories or predict the protein function from dataset of protein-protein interaction. This framework improved classification F1-score than node features alone.    
  - Large graph
  - Hypergraphs
  - Attention mechanism
  - Adversial generation





## References

[1] T. Christiano Silva and L. Zhao, Machine Learning in Complex Networks. Cham: Springer International Publishing, 2016.

[2]F. Chen, Y.-C. Wang, B. Wang, and C.-C. J. Kuo, “Graph representation learning: a survey,” APSIPA Transactions on Signal and Information Processing, vol. 9, p. e15, 2020, doi: 10.1017/ATSIP.2020.13.

