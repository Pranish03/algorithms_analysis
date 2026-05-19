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

## 3. Merge Sort

### 3.1. Algorithm(Pseudocode)

```.txt
SUBROUTINE MergeSort(A)
    IF len(A) <= 1 THEN
        RETURN A
    END IF

    midPoint <- len(A) / 2

    leftHalf <- A[0 : midPoint]
    rightHalf <- A[midPoint : len(A)]

    leftHalf <- MergeSort(leftHalf)
    rightHalf <- MergeSort(rightHalf)

    RETURN Merge(leftHalf, rightHalf)
END SUBROUTINE

SUBROUTINE Merge(leftHalf, rightHalf)
    i <- 0
    j <- 0
    result <- []

    WHILE i < len(leftHalf) AND j < len(rightHalf) DO
        IF leftHalf[i] < rightHalf[j] THEN
            APPEND leftHalf[i] TO result
            i <- i + 1
        ELSE
            APPEND rightHalf[j] TO result
            j <- j + 1
        END IF
    END WHILE

    WHILE i < len(leftHalf) DO
        APPEND leftHalf[i] TO result
        i <- i + 1
    END WHILE

    WHILE j < len(rightHalf) DO
        APPEND rightHalf[j] TO result
        j <- j + 1
    END WHILE

    RETURN result
END SUBROUTINE
```

### 3.2. Complexity Analysis

#### 3.2.1. Time Complexity

The recurrence relation for merge sort algorithm is,

$T(n) = \begin{cases} 2T(n/2)+O(n) & \text{if } n > 1 \\ 1 & \text{if } n = 1 \end{cases}$

Solving the recurrence relation we get $T(n)=\Theta(n\text{log}_2n)$

#### 2.2.2. Space Complexity

Uses extra memory for left and right sub arrays.
so, $S(n)=O(n)$

---

## 4. Quick Sort

### 4.1. Algorithm(Pseudocode)

```.txt
SUBROUTINE QuickSort(A, start, end)
    IF start > end THEN
        RETURN A
    END IF

    pi <- Partition(A, start, end)
    QuickSort(A, start, pi-1)
    QuickSort(A, pi+1, end)
END SUBROUTINE

SUBROUTINE Partition(A, start, end)
    pivot <- A[end]
    i <- start - 1

    FOR j <- start TO end-1 DO
        IF A[j] < pivot THEN
            i <- i + 1
            Swap A[i] AND A[j]
        END IF
    END FOR
    Swap A[i+1] AND A[high]

    RETURN i+1
END SUBROUTINE
```
