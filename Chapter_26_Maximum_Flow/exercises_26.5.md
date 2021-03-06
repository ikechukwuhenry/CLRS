## 26.5 The relabel-to-front algorithm

### 26.5-1

> Illustrate the execution of RELABEL-TO-FRONT in the manner of Figure 26.10 for the flow network in Figure 26.1(a). Assume that the initial ordering of vertices in $$L$$ is $$\langle v_1, v_2, v_3, v_4 \rangle$$ and that the neighbor lists are
> 
> $$v_1.N = \langle s, v_2, v_3 \rangle$$,
> $$v_2.N = \langle s, v_1, v_3, v_4 \rangle$$,
> $$v_3.N = \langle v_1, v_2, v_4, t \rangle$$,
> $$v_4.N = \langle v_2, v_3, t \rangle$$,

### 26.5-2 $$\star$$

> We would like to implement a push-relabel algorithm in which we maintain a firstin, first-out queue of overflowing vertices. The algorithm repeatedly discharges the vertex at the head of the queue, and any vertices that were not overflowing before the discharge but are overflowing afterward are placed at the end of the queue. After the vertex at the head of the queue is discharged, it is removed. When the queue is empty, the algorithm terminates. Show how to implement this algorithm to compute a maximum flow in $$O(V^3)$$ time.

### 26.5-3

> Show that the generic algorithm still works if RELABEL updates $$u.h$$ by simply computing $$u.h = u.h + 1$$. How would this change affect the analysis of RELABEL-TO-FRONT?

### 26.5-4 $$\star$$

> Show that if we always discharge a highest overflowing vertex, we can make the
push-relabel method run in $$O(V^3)$$ time.

### 26.5-5

> Suppose that at some point in the execution of a push-relabel algorithm, there exists an integer $$0 < k \le |V| - 1$$ for which no vertex has $$v.h = k$$. Show that all vertices with $$v.h > k$$ are on the source side of a minimum cut. If such a $$k$$ exists, the __*gap heuristic*__ updates every vertex $$v \in V - \{s\}$$ for which $$v.h > k$$, to set $$v.h = \max(v.h, |V| + 1)$$. Show that the resulting attribute $$h$$ is a height function. (The gap heuristic is crucial in making implementations of the push-relabel method perform well in practice.)

