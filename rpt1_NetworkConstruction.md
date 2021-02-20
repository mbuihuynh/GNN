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


3. Classification of network formation techniques:






## References

[1] T. Christiano Silva and L. Zhao, Machine Learning in Complex Networks. Cham: Springer International Publishing, 2016.

[2]F. Chen, Y.-C. Wang, B. Wang, and C.-C. J. Kuo, “Graph representation learning: a survey,” APSIPA Transactions on Signal and Information Processing, vol. 9, p. e15, 2020, doi: 10.1017/ATSIP.2020.13.

