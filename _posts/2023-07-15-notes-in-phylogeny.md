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
+ **Trees**:A tree is a graph that is connected and has no cycles,There are many alternative characterizations of trees:
  1. $$T=(V,E)$$ is a tree
  2. $$T=(V,E)$$ is connected and has $$\vert V \vert -1$$ edges
  3. for any two vertices $$u$$ and $$v$$ of $$T$$,there is a unique path from $$u$$ to $$v$$.
+ A *cherry* in a tree is a pair of leaves that are adjacent to a common interior vertex (this vertex may also be adjacent to other leaves).

Every tree $$T$$ that has more than one vertex always has at least two vertices of degree one. Such vertices are called *leaves*, whereas the remaining vertices are said to be *interior vertices*. Similarly, an edge that is incident with a leaf is said to be a *pendant edge*; other- wise, it is an interior edge. Every tree with three or more vertices has an interior vertex. A *star tree* is a tree with a single interior vertex that is adjacent to all the leaves.

##### Helly Property:
> If $$V_1,V_2,...,V_k \subseteq V$$ comprise the vertex sets of a family of subtrees of a tree $$T$$,and these sets satisfy the property that $$V_i \cap V j  \neq \varnothing$$ , then $$\bigcap^k_{i=1} V_i$$ is also nonempty.

Proof of this property can be done by induction on *k*, for the base case $$k=3$$, consider a vertex $$v\in V_1\cap V_2$$ but $$v\notin V_2 \cap V_3$$, and $$w\in V_1\cap V_3$$ but $$w\notin V_2 \cap V_3$$, then you can find a path $$P(V_1;v,w)$$ in $$V_1$$, now consider another pair of vertices  $$i,j\in V_2\cap V_3$$, there is a path $$P(V_2\cap V_3;i,j)$$, if these two pathes have common vertex, then we are done, if they share no common vertex, we can chooes a path $$P(V_2;v,i)$$ and another path $$P(V_3;w,j)$$, they will form a cycle.(This is just an outline, you can fill in the details).

One consequence of the Helly property is that, given a tree $$T$$ , if one takes any three vertices u,v, and w and considers the intersection in $$T$$ of the three paths $$P(T;u,v)$$, $$P(T;u,w)$$, and $$P(T;v,w)$$, then this intersection must be nonempty. Moreover, in this case the intersection consists of just a single vertex, called the median of u,v, and w, denoted $$med_T (u,v,w)$$.

Given a finite graph $$G = (V,E)$$ consisting of $$c_G$$ connected components, the cyclomatic number of $$G$$, denoted $$cy(G)$$, is defined by
\begin{equation}
cy(G)=|E|−|V|+c_G
\end{equation}

### Exercise:
1.Show that if a tree $$T$$ has five or more vertices and no vertex of degree 2, then $$T$$ has at least two disjoint pairs of leaves that form cherries of $$T$$.

*Proof:*  To prove this we first exhibit a fact about tree: *Any tree $$T$$ is either a star tree or it has two interior vertices $$v_1$$ and $$v_2$$, each of which is adjacent to exactly one nonleaf vertex*, this fact can be seen by considering the endpoints of the longest path formed by interior vertices.

 If it is a star tree, then it has more than 4 leaves, say, four of them are $$v_1,v_2,v_3,v_4$$, and $$\{v_1,v_2\}$$ and $$\{v_3,v_4\}$$ are two disjoint pairs of leaves that form cherries. If it is not a star tree, then by the fact above we have $$v_1$$ and $$v_2$$ that each of them is adjacent to exactly one nonleaf vertex, since we have no vertex of degree 2, each of $$v_1$$ and $$v_2$$ has at least 2 adjacent leaves, in other words, 2 cherries that shares no common vertex.$$ \blacksquare $$

2. Show that if $$\mathscr{P}= \{T1,T2,...,Tk\}$$ is a collection of subtrees of $$T$$, and each tree in contains strictly more than half the leaves of $$T$$ , then there is a vertex common to all trees in $$\mathscr{P}$$.

*Proof:* This is a direct corolloary of Helly Property. $$\blacksquare$$

