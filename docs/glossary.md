# TigerGraph CuGraph Glossary of Terms

## Batch

## CuGraph

A collection of GPU-accelerated graph algorithms and services that run
on NVIDIA GPUs.

You can think of CuGraph as a version of NVIDIA CUDA C libraries but focused on working on graph data.

## Edge Classification

## Link Prediction

The process of using machine learning to predict a new or missing link from an existing graph.

Link prediction is of the key use cases for GNNs,  Link prediction is also used in many
areas of process mining including predicting social network relationships, customer purchases
and recommendations.

## NCCL

NCCL (pronounced "nickel") is an ID assigned to 

## PageRank

## PyTorch Geometic

## RAPIDS

RAPIDS is NVIDIA developed Open Source software packatge designed to enable data scientists staff to more easily use NVIDIA GPUs.

RAPIDS has connectors that work with popular Python data science libraries such as Pandas, Scikit-Learn and NetworkX.

[RAPIDS website](https://rapids.ai/)
## Sampling

## Seeds

Vertex seed
Edge Seed

## User Defined Function

A function written by a specific user that adds new functionality to TigerGraph.  Unlike GSQL functions, User Defined Functions (UDFs) must be written in C/C++.

UDFs are the method that TigerGraph calls the CuGraph interfaces.

### WholeGraph
WholeGraph is a software system that allows users to partion a large group on multiple GPUs.

WholeGraph was developed to help train large-scale Graph Neural Networks(GNN). WholeGraph provides underlying storage structure called WholeMemory. WholeMemory is a Tensor like storage and provide multi-GPU support. It is optimized for NVLink systems like DGX A100 servers. By working together with cuGraph, cuGraph-Ops, cuGraph-DGL, cuGraph-PyG, and upstream DGL and PyG, it will be easy to build GNN applications.

[WholeGraph GitHub Repo](https://github.com/rapidsai/wholegraph)

## Worker


