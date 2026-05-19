# Dynamic Programming

## 1. Matrix Chain Multiplication

### 1.1. Algorithm(Pseudocode)

```.txt
SUBROUTINE MatrixChain(dims, i, j)
    IF i == j THEN
        RETURN 0
    END IF

    cost <- INFINITY

    FOR k <- i TO j - 1 DO
        q <- MatrixChain(dims, i, k) + MatrixChain(dims, k+ 1, j) + dims[i - 1] * dims[k] * dims [j]
        if q < cost THEN
            cost <- q
        END IF
    END FOR

    RETURN cost
END SUBROUTINE
```

### 1.2. Complexity Analysis

#### 1.2.1. Time Complexity

$T(n)=O(n^3)$

#### 1.2.2. Space Complexity

$S(n)=O(n^2)$

---

## 2. 0/1 Knapsack Problem

### 2.1. Algorithm(Pseudocode)

```.txt
SUBROUTINE BinaryKnapsack(items, n, W)
    IF n == 0 OR W == 0 THEN
        RETURN 0
    END IF

    IF items[n-1].weight > W THEN
        RETURN BinaryKnapsack(items, n - 1, W)
    ELSE
        RETURN max(
            items[n-1].value + BinaryKnapsack(items, n - 1, W - items[n-1].weight),
            BinaryKnapsack(items, n - 1, W)
        )
    END IF
END SUBROUTINE
```

### 2.2. Complexity Analysis

#### 2.2.1. Time Complexity

$T(n, W) = O(nW)$

#### 2.2.2. Space Complexity

$S(n, W) = O(nW)$

---

## 3. Longest Common Subsequence

### 3.1. Algorithm(Pseudocode)

```.txt
SUBROUTINE LCS(X, Y, m, n)
    IF m == 0 OR n == 0 THEN
        RETURN 0
    END IF

    IF X[m] == Y[n] THEN
        RETURN 1 + LCS(X, Y, m - 1, n - 1)
    ELSE
        RETURN max(
            LCS(X, Y, m - 1, n),
            LCS(X, Y, m, n - 1)
        )
    END IF
END SUBROUTINE

```

### 3.2. Complexity Analysis

#### 3.2.1. Time Complexity

$T(m, n) = O(2^{m+n})$ Using recursion

$T(m, n) = O(mn)$ Using memoization

---

## 4. Floyd Warshall Algorithm

### 4.1. Algorithm(Pseudocode)

```.txt
SUBROUTINE FloydWarshall(dist, n)
    FOR k <- 1 TO len(G.V) DO
        FOR i <- 1 TO len(G.V) DO
            FOR j <- 1 TO len(G.V) DO
                IF dist[i][j] > dist[i][k] + dist[k][j] THEN
                    dist[i][j] <- dist[i][k] + dist[k][j]
                END IF
            END FOR
        END FOR
    END FOR

    RETURN dist
END SUBROUTINE
```

### 4.2. Complexity Analysis

#### 4.2.1. Time Complexity

$T(V, E) = O(V^3)$

#### 4.2.2. Space Complexity

$S(V, E) = S(V^2)$

---

## 5. Prim's Algorithm

### 5.1. Algorithm(Pseudocode)

```.txt
SUBROUTINE Prims(G, start)
    key <- []
    parent <- []

    FOR EACH vertex v in G.V DO
        key[v] <- INFINITY
        parent[v] <- NULL
    END FOR

    key[start] <- 0
    Q <- MinHeap(G.V, key)

    WHILE Q != EMPTY DO
        u <- Q.extractMin()

        FOR EACH vertex v adjacent to u DO
            IF v IN Q AND weight(u, v) < key[v] THEN
                key[v] <- weight(u, v)
                parent[v] <- u
                decreaseKey(Q, v, key[v])
            END IF
        END FOR
    END WHILE

    RETURN parent
END SUBROUTINE
```

### 5.2. Complexity Analysis

#### 5.2.1. Time Complexity

$T(V, E) = O(E\text{log}V)$

---

## 6. Dijkastra's Algorithm

### 6.1. Algorithm(Pseudocode)

```.txt
SUBROUTINE Dijkastra(G, source)
    FOREACH vertex v in G.V DO
        dist[v] <- INFINITY
        parent[v] <- NULL
        visited[v] <- FALSE
    END FOREACH

    dist[source] <- 0

    FOR i <- 1 TO |G.V| DO
        u <- vertex with minimum dist[u] where visited[u] == FALSE

        FOREACH vertex v adjacent to u DO
            IF visided[v] == FALSE AND dist[u] + weight(u, v) < dist[v] THEN
                dist[v] <- dist(u) + weight(u, v)
                parent[v] <- u
            END IF
        END FOREACH
    END FOR

    RETURN (dist, parent)
END SUBROUTINE
```

### 6.2. Complexity Analysis

#### 6.2.1. Time Complexity

$T(V, E) = O(V^2)$ using simple array

$T(V, E) = O((V+E)\text{log}V)$ using priority queue
