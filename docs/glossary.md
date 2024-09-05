# TigerGraph CuGraph Glossary of Terms

## Adjency Matrix

A square matrix used to represent a graph, where each element at position (i, j) indicates the presence (typically with a 1) or absence (typically with a 0) of an edge between the vertices i and j. For undirected graphs, the matrix is symmetric; for directed graphs, the matrix reflects the direction of edges.

## Batch

#### Compressed Row Storage (CRS)

A space-efficient format used to store sparse matrices. In CRS, only the non-zero elements of the matrix are stored, along with two additional arrays: one for the column indices of the non-zero elements and another to mark the starting index of each row in the data array. This format reduces memory usage and enables faster access to non-zero elements, especially when performing matrix-vector multiplication.

#### CuGraph

A collection of GPU-accelerated graph algorithms and services that run
on NVIDIA GPUs.

You can think of CuGraph as a version of NVIDIA CUDA C libraries but focused on working on graph data.

#### Edge Classification

#### Graph Neural Network (GNN)

A type of neural network specifically designed to operate on graph-structured data. It learns representations of nodes, edges, or entire graphs by iteratively aggregating and transforming information from a node's local neighborhood. GNNs are capable of capturing both the features of individual nodes and the relationships between them, making them well-suited for tasks like node classification, link prediction, and graph classification in applications such as social networks, molecular biology, and recommendation systems.

#### Link Prediction

The process of using machine learning to predict a new or missing link from an existing graph.

Link prediction is of the key use cases for GNNs,  Link prediction is also used in many
areas of process mining including predicting social network relationships, customer purchases
and recommendations.

###### NVIDIA Collective Communications Library (NCCL)

NCCL (pronounced "nickel") is an ID assigned to a process on one of the GPUs in a cluster.

* [NCCL on the NVIDIA Developer Website](https://developer.nvidia.com/nccl)
* [NCCL Current Docs](https://docs.nvidia.com/deeplearning/nccl/user-guide/docs/index.html)
* [NCCL Archive Docs](https://docs.nvidia.com/deeplearning/nccl/archives/nccl_247/nccl-developer-guide/docs/index.html)

#### NCCL ID

An object created by the [NCCL](#nvidia-collective-communications-library-nccl) that which is used by all processes and threads to synchronize and understand they are part of the same communicator.

Before using the NCLL software, you need to first create a unique object ID by calling the ncclGetUniqueId function.

The ncclGetUniqueId function returns an ID which has to be broadcast to all participating threads and processes using any CPU communication system, for example, passing the ID pointer to multiple threads, or broadcasting it to other processes using MPI or another parallel environment using, for example, sockets.

[NVIDA Deeplearning Web Site Archive](https://docs.nvidia.com/deeplearning/nccl/archives/nccl_247/nccl-developer-guide/docs/usage/communicators.html)

#### PageRank

#### PyTorch Geometic

#### RAPIDS

RAPIDS is NVIDIA developed Open Source software packatge designed to enable data scientists staff to more easily use NVIDIA GPUs.

RAPIDS has connectors that work with popular Python data science libraries such as Pandas, Scikit-Learn and NetworkX.

[RAPIDS website](https://rapids.ai/)

#### Sampling

The process of selecting a subset of nodes and their corresponding neighbors from a large graph to efficiently train the GNN.

Since processing the entire graph can be computationally expensive, sampling methods—such as node sampling, edge sampling, or neighborhood sampling—reduce the graph's size while preserving key structural properties. This allows the GNN to learn from local node interactions and aggregate information without needing to process the full graph at each training step.

#### Seeds

The initial set of nodes or edges selected as the starting point for the [sampling](#sampling) process. From these seed nodes, their neighbors are sampled in successive steps to construct a subgraph or a local neighborhood.

The choice of seed nodes influences which part of the graph is explored, and they are typically chosen based on specific criteria such as random selection, high centrality, or other graph metrics. Seeds help to reduce the computational cost of processing large graphs by focusing on smaller, relevant sections.

#### Sparse Matrix

A matrix in which most of the elements are zero.

It is commonly used in data structures and algorithms to efficiently represent large datasets with few non-zero elements, reducing memory usage and computational complexity compared to dense matrices. Sparse matrices are often stored using specialized formats like compressed row storage or coordinate format.

Most enterprise knowledge
graphs contain billions of verticies but each vertex only has around five releationships.
Useing an [adjency matrix](#adjency-matrix)

[Wikipedia Page on Sparse Matrix](https://en.wikipedia.org/wiki/Sparse_matrix)

#### User Defined Function

A function written by a specific user that adds new functionality to TigerGraph.  Unlike GSQL functions, User Defined Functions (UDFs) must be written in C/C++.

UDFs are the method that TigerGraph calls the CuGraph interfaces.

#### WholeGraph

WholeGraph is a software system that allows users to partion a large group on multiple GPUs.

WholeGraph was developed to help train large-scale Graph Neural Networks(GNN). WholeGraph provides underlying storage structure called WholeMemory. WholeMemory is a Tensor like storage and provide multi-GPU support. It is optimized for NVLink systems like DGX A100 servers. By working together with cuGraph, cuGraph-Ops, cuGraph-DGL, cuGraph-PyG, and upstream DGL and PyG, it will be easy to build GNN applications.

[WholeGraph GitHub Repo](https://github.com/rapidsai/wholegraph)

#### Worker


