---
layout: post
title: notes in phylogeny
date: 2023-07-15 11:12:00
description: the first notes in phylogeny
tags: formatting math
categories: sample-posts
related_posts: false
---
This is the first note for phyogeny, the main content will come from **Phylogeny:Discrete and Random Processes in Evolution** by Mike Steel.

## Graph and Trees
For those who are not familiar with the notations in graph theory, you can refer to any graph theory textbook or the <a href="https://en.wikipedia.org/wiki/Graph_theory">wiki page</a>. Here I just list some important concepts in phylogeny:


### Definition
+ A *clique* in $$G$$ is a subset of vertices for which each pair of vertices is adjacent.
+ The *diameter of a graph* $$G=(V,E)$$ is $$\Delta(G)=max\{d(u,v):u,v\in V \}$$ where $$d(u,v)$$ is the length (number of edges) of the shortest path in $$G$$ connecting $$u$$ and $$v$$, in other words, the longest path needed (in a shortest path) to connect any two vertices of $$G$$.
+ A graph $$G$$ is bipartite if its vertex set can be partitioned into two nonempty subsets $$U$$ and $$W$$ so that all edges of $$G$$ consist of a vertex from each subset. It is a classical result that a graph is bipartite if and only if it does not contain any cycles of odd length.
+ **Trees**:A tree is a graph that is connected and has no cycles:
  1. $$T=(V,E)$$ is a tree
  2. $$T=(V,E)$$ is connected and has $$|V|-1$$ edges
  3. for any two vertices $$u$$ and $$v$$ of $$T$$,there is a unique path from $$u$$ to $$v$$.
