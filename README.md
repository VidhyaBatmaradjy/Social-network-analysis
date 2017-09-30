# Social-graph-analysis

Dataset: This is the collaboration network between Jazz musicians. Each node is a Jazz musician and an edge denotes that two 
         musicians have played together in a band. The data was collected in 2003.

NODES:   198 vertices (musicians)

EDGES:   2,742 edges (collaborations)

STRUCTURE:
“Real Network” has a clumpy structure with an average path length of 2.23 relative to “Random Network” with 1.87. Also, “Real Network” seems to have 7 local communities compared to the “Random Network” with just 1 whole community (using infomap.community() command). This is because a “Random Network” is not expected to have a community structure as any 2 vertices have the same probability to be adjacent.  
            
“Real Network” – (D=6)

![alt text](https://github.com/VidhyaBatmaradjy/Social-network-analysis/blob/master/graph%20analysis/screenshots/realnetwork.png)

“Random Network” – (D=3)

![alt text](https://github.com/VidhyaBatmaradjy/Social-network-analysis/blob/master/graph%20analysis/screenshots/randomnetwork.png)


NETWORK LEVEL METRICS

1: Degree Distribution: 
“Real Network” exhibits a scale free, “Power Law” degree distribution. On the other hand, with increasing connectivity, the “Random Network” show increasing divergence from power law. Thus “Real Network” has very few nodes with very low degree and some with very high degree, thus leaving the rest with modular degree.  On the other hand, due to random rewiring and shorter path length, most nodes in the “Random Network” have modular degrees except a couple of outliers with very low and high degrees.

![alt text](https://github.com/VidhyaBatmaradjy/Social-network-analysis/blob/master/graph%20analysis/screenshots/degree_realnetwork.png)


![alt text](https://github.com/VidhyaBatmaradjy/Social-network-analysis/blob/master/graph%20analysis/screenshots/degree_randomnetwork.png)


2: Clustering Co-efficient: 
“Real Network” has a higher global clustering co-efficient of 0.520 and more closed triplets of 17,899 compared to the “Random Network” with 0.144 and 10,573 respectively. This is reveals that musicians tend to collaborate with people who are also collaborating with each other, resulting in sets of musicians among which many edges exist. On the other hand, a set made from randomly chosen musicians as opposed to real connections has a much smaller number of edges between them.

3: Modularity: “Real Network” with a high modularity of 0.438 reflects dense connections within communities and sparse connections across communities. i.e. “Real Network” with a high level of modularity, likely reflect the lack of many paths between modules, requiring additional steps (6 hops) to reach nodes in different modules. On the other hand, the “Random Network” with a much lower modularity of 0.121 requires only 3 hops due to random rewiring.

4: Betweenness Centrality: “Real Network” has a long tailed distribution with moderate centralization for betweenness. Also, there exists a specific set of very important nodes(Musicians) with very high betweenness. This shows that the network has only limited access or connectivity to other networks which means that scope of creativity and fresh ideas is limited. Also, the network is at a potential risk of knowledge bottleneck.
“Random Network” resembles a normal curve with very low centralization. The betweenness centrality is not very skewed showing that most musicians are reasonably positioned to access opportunities, emphasizing that the network is well integrated. 

![alt text](https://github.com/VidhyaBatmaradjy/Social-network-analysis/blob/master/graph%20analysis/screenshots/betweenness_real.png)

![alt text](https://github.com/VidhyaBatmaradjy/Social-network-analysis/blob/master/graph%20analysis/screenshots/betweenness_random.png)


Characteristics of nodes and communities

Important Nodes: The below graphs describe the way that a musician is embedded in each network offering them opportunities. Musicians that face fewer constraints and have more opportunities than others are said to be in more favorable structural position. Only the 5 most prominent nodes in each network have been highlighted and sized based on betweenness for understanding.
                                          
“Real Network”: Nodes 67, 7 and 23 seem to be more influential having the highest centrality scores in terms of degree, betweenness and closeness. Nodes 23 and 90 are more powerful with higher betweenness relative to node 20 with a much higher degree.

![alt text](https://github.com/VidhyaBatmaradjy/Social-network-analysis/blob/master/graph%20analysis/screenshots/centralnodes_real.png)


“Random Network”: Rewiring the nodes leads to a different set of prominent nodes. Nodes 149,180 seem to have the highest centrality scores in terms of degree and betweenness. Node 193 though has a high degree is less influential compared to nodes 83 and 43 due to lower betweenness score. Most nodes are similarly positioned in terms of closeness centrality

![alt text](https://github.com/VidhyaBatmaradjy/Social-network-analysis/blob/master/graph%20analysis/screenshots/centralnodes_random.png)

Overlapping Communities
We get different communities depending on the algorithm used and what we are optimizing for. So, a clique which in some sense is a stronger version of a community is analyzed to identify overlapping communities and their effect.
“Real Network” has 746 maximal cliques, with the largest (1) of these maximal cliques containing 30 nodes. “Random Network” has 2581 maximal cliques, with the largest (7) of these maximal cliques containing 5 nodes each.

To perform a cluster analysis of the closeness of the cliques, the 3 largest cliques from “Real Network” and the 5 largest ones from “Random Network” have been considered.

“Real Network” shows that there are many nodes (red, yellow) which overlap between the different cliques. Also, the red nodes were found to overlap with almost most other cliques that are not shown in the graph. This clearly shows that conflict between the groups are less likely. Also, diffusion of information may spread rapidly across the entire network than where the groups don't overlap.

![alt text](https://github.com/VidhyaBatmaradjy/Social-network-analysis/blob/master/graph%20analysis/screenshots/clique_real.png)


“Random Network” shows very few nodes that tend to overlap and was found to differ for other cliques not shown. This shows that the network does not have a specific set of very important nodes and they appear to be less homogenous.

![alt text](https://github.com/VidhyaBatmaradjy/Social-network-analysis/blob/master/graph%20analysis/screenshots/clique_random.png)


Comparison Summary: The comparison reveals that both networks are sparse with the same network density of 0.1405. The distribution further shows that both the networks differ in terms of degrees and betweenness while the closeness distribution is similar. It is also clear that the “Real Network” appears to be more integrated with nodes having higher sense of community. While the “Random Network” explains some properties of real networks, notably the short distances between any two nodes, it fails in other respects. In particular, it cannot explain the ubiquitous presence of clustering, modularity and hubs in real networks.


