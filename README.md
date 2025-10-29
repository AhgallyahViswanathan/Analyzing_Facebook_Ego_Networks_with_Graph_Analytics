# Analyzing_Facebook_Ego_Networks_with_Graph_Analytic 
This repository contains the project for the CSC4406 - Big Data Analytics course. The project involves analyzing the structure of a Facebook ego-network to identify influential users and detect community structures using graph analytics techniques.

## 👩‍💻 Group 5 Members

* **Ahgallyah** (214747) 
* **Nurul Ilyana** (214695) 
* **Alya Batrisyia** (214726) 
* **Aisyah Humaira** (214732) 
* **Nurfarhannis Nabila** (216536) 

## 🎯 Project Goal

The primary goal is to analyze the structure of a specific Facebook ego-network. This includes:
1.  Identifying the most influential users within the network using various centrality measures.
2.  Exploring and visualizing the community-like structures formed by clusters of users.
3.  Interpreting what these structures and measures tell us about influence and social behavior in the network.

## 📊 Dataset

**Name:** Facebook Ego-Networks 
**Source:** Stanford Network Analysis Project (SNAP) 
**Link:** [http://snap.stanford.edu/data/egonets-Facebook.html](http://snap.stanford.edu/data/egonets-Facebook.html) 
**Chosen Network:** For this analysis, we selected the ego-network for **Node 107**.

## 🛠️ Tools and Libraries
**Language:** Python 
**Core Libraries:**
    **Pandas:** For loading and handling the dataset
    **NetworkX:** For graph creation, manipulation, and analysis (calculating properties, centrality, etc.)
    **Matplotlib:** For visualizing the network graphs
    **`python-louvain`:** For performing community detection

## 📈 Methodology

The project was broken down into three main tasks:

### 1. Data Loading and Graph Creation
The edge list for Node 107 was loaded from the dataset files using Pandas.
A NetworkX graph object was created from the edge list.
* Basic graph properties were calculated:
   **Number of Nodes** 
   **Number of Edges** 
   **Graph Density**
   **Average Degree** 

### 2. Centrality Analysis
To identify influential users, four different centrality measures were calculated : 

**Degree Centrality:** Measures the number of connections a node has (popularity).
**Betweenness Centrality:** Measures how often a node lies on the shortest path between other nodes (a "bridge" or "gatekeeper").
**Closeness Centrality:** Measures how quickly a node can reach all other nodes in the network (information efficiency).
**Eigenvector Centrality:** Measures a node's influence based on the influence of its neighbors (connected to other influential users).

### 3. Community Detection
The **Louvain Community Detection algorithm** was applied to the graph.
This algorithm partitions the network into distinct communities or clusters based on edge density.
The detected communities were then visualized and analyzed to see how they relate to the centrality scores.

## 💡 Key Findings and Interpretation

Our analysis of the Node 107 ego-network revealed a clear "core-periphery" structure.

**The Core Influencer:** **Node 107** (the ego of the network) is unambiguously the most central and influential user.It ranked **#1 in all four centrality measures**: Degree, Betweenness, Closeness, and Eigenvector.

**Dominant Communities:** The Louvain algorithm identified five distinct communities.
**Community 0:** This is the core community, centered around **Node 107**.
**Community 4:** This is another highly influential and dense cluster, containing many of the other top users (like nodes 1888, 1800, and 1663).

**Influence is Clustered:** There is a strong relationship between high centrality and community membership.The most influential users are not scattered but are concentrated within the dominant communities (0 and 4).

**The Role of Bridges:** While influence is centralized, users in smaller communities (like nodes 483 and 917) scored high in betweenness centrality.This shows they play a crucial role as "bridge nodes," connecting the peripheral groups to the central core and facilitating network-wide communication.

## 🚀 How to Run the Code
1.  Clone this repository or download the `.ipynb` notebook file.
2.  Open the notebook in Google Colab or a local Jupyter environment.
3.  Ensure you have the required dataset file (`107.edges`) available.
4.  In Colab, you can upload the file to your session storage or mount your Google Drive.
5.  Install the `python-louvain` library:
    ```bash
    pip install python-louvain
    ```
6.  Run the notebook cells sequentially to reproduce the analysis and visualizations.
