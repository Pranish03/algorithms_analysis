# Greedy Algorithms

## 1. Fractional Knapsack

### 1.1. Algorithm(Pseudocode)

```.txt
SUBROUTINE FractionalKnapsack(items, n, W)
    sort_desc_by_items_value_per_weight_ratio(items)
    totalValue <- 0

    FOR i <- 0 TO n - 1 DO
        IF items[i].weight <= W THEN
            W <- W - items[i].weight
            totalValue <- totalValue + items[i].value
        ELSE
            totalValue <- totalValue + items[i].value * (W / items[i].weight)
            BREAK
        END IF
    END FOR

    RETURN totalValue
END SUBROUTINE
```

### 1.2. Complexity Analysis

#### 1.2.1. Time Complexity

$T(n)=O(n\text{log}_2n) \text{ for sorting } + O(n) \text{ for filling } = O(n\text{log}_2n)$

#### 1.2.2. Space Complexity

$S(n)=O(1)$

---

## 2. Job Sequencing with Deadlines

### 2.1. Algorithm(Pseudocode)

```.txt
SUBROUTINE JobSequencing(jobs, n)
    sort_desc_by_profit(jobs)
    maxDeadline <- find_max_deadline(jobs)

    slot <- [1 : maxDeadline]
    totalProfit <- 0

    FOR i <- 0 TO n - 1 DO
        FOR j <- jobs[i].deadline DOWN TO 1 DO
            IF slot[j] == EMPTY THEN
                slot[j] <- jobs[i].id
                totalProfit <- totalProfit + jobs[i].profit
                BREAK
            END IF
        END FOR
    END FOR

    RETURN (slot, totalProfit)
END SUBROUTINE
```

### 2.2. Complexity Analysis

#### 2.2.1. Time Complexity

$T(n) = O(n^2)$

---

## 3. Huffman Coding

### 3.1. Algorithm(Pseudocode)

```.txt
SUBROUTINE Huffman(C, n)
    Q <- minHeap(C)

    FOR i <- 1 TO n - 1 DO
        create node n
        x <- Q.extract()
        y <- Q.extract()

        n.left <- x
        n.right <- y

        n.data <- x.freq + y.freq

        Q.insert(n)
    END FOR

    RETURN extract(Q)
END SUBROUTINE

```

### 3.2. Complexity Analysis

#### 3.2.1. Time Complexity

$T(n) = O(n) \text{ Building heap } + O(n\text{log}_2n) \text{ Each insert/extract } = O(n\text{log}_2n)$

#### 2.2.2. Space Complexity

Creates node n in each iteration.
so, $S(n)=O(n)$

---

## 4. Kruskal's Algorithm

### 4.1. Algorithm(Pseudocode)

```.txt
SUBROUTINE Kruskal(G)
    sort_edges_by_weight(G.E)
    T <- set()

    FOR EACH edge (u, v) IN G.E DO
        IF find(u) != find(v) THEN
            T.add((u, v))
            union(u, v)
        END IF
    END FOR

    RETURN T
END SUBROUTINE
```

### 4.2. Complexity Analysis

#### 4.2.1. Time Complexity

$T(V, E) = O(E\text{log}E)$

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
