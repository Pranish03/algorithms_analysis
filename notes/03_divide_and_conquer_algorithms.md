# Divide and Conquer Algorithms

## 1. Min-Max Finding (Iterative approach)

### 1.1. Algorithm(Pseudocode)

```.txt
SUBROUTINE MinMax(A, n)
    min <- A[0]
    max <- A[0]
    FOR i <- 0 TO n-1 DO
        IF A[i] < min THEN min <- A[i]
        IF A[i] > max THEN max <- A[i]
    END FOR
    RETURN (min, max)
END SUBROUTINE
```

### 1.2. Complexity Analysis

#### 1.2.1. Time Complexity

The number of comparision in iterative min-max finding algorithm is $2n-2$.
so, $T(n)=O(n)$

---

## 1. Min-Max Finding (Divide and Conquer)

### 2.1. Algorithm(Pseudocode)

```.txt
SUBROUTINE MinMax(A, start, end)
    IF start == end THEN RETURN (A[start], A[start])
    IF end == start + 1 THEN
        IF A[start] < A[end] THEN
            RETURN (A[start], A[end])
        ELSE
            RETURN (A[end], A[start])
        END IF
    END IF

    mid <- start + (end - start) / 2
    (min1, max1) <- MinMax(A, start, mid)
    (min2, max2) <- MinMax(A, mid+1, end)

    IF min1 < min2 THEN
        min <- min1
    ELSE
        min <- min2
    END IF

    IF max1 > max2 THEN
        max <- max1
    ELSE
        max <- max2
    END IF

    RETURN (min, max)
END SUBROUTINE
```

### 2.2. Complexity Analysis

#### 2.2.1. Time Complexity

The recurrence relation for divide and conquer min-max finding algorithm is,

$T(n) = \begin{cases} 2T(n/2)+1 & \text{if } n > 2 \\ 1 & \text{if } n \leq 2 \end{cases}$

Solving the recurrence relation we get $T(n)=\Theta(n)$

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
