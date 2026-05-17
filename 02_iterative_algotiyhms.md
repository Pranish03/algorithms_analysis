# Iterative Algorithms

## 1. GCD - Euclid's Algorithm

### 1.1. Algorithm(Pseudocode)

```.txt
GCD(a, b)
    Input: Two non-negative integers a and b
    Output: GCD of a and b

    WHILE b!= 0 DO
        temp <- b
        b = a % b
        a = temp
    END WHILE
    RETURN b
```

### 1.2. Complexity Analysis

#### 1.2.1. Time Complexity

1. **Best Case** - Occurs when the algorithm terminates on single step i.e. either $a = 0$ or $a mod b = 0$.
   so, $B(n) = O(n)$

2. **Average Case** - Occurs when each step replaces $(a,b)\rightarrow(b, a mod b)$.
   so, $A(n) = O(n)$

3. **Worst Case** - Occurs when reduction happens as slow as possible.
   so, $W(n) = O(\text{log}(\text{min}(a,b)))$

#### 1.2.2. Space Complexity

Only one variable used ($temp$).
so, $S(n)=O(1)$

---

## 2. Fibonacci Numbers

### 2.1. Algorithm(Pseudocode)

```.txt
FIBONACCI(n)
    Input: Non-negative integer n.
    Output: Nth fibonacci number.

    IF n == 0 THEN RETURN 0
    IF n == 1 THEN RETURN 1
    a <- 0
    b <- 1
    FOR i <- 2 TO n DO
        temp <- a + b
        a <- b
        b <- temp
    END FOR
    RETURN b
```

### 2.2. Complexity Analysis

#### 2.2.1. Time Complexity

Algorithm has a single loop that runs from $2$ to $n$, iterating ($n-2$) times.
so, $T(n) = O(n)$

#### 2.2.2. Space Complexity

Only three variables used ($a, b, temp$) regardless of the input size $n$.
so, $S(n)=O(1)$

---

## 3. Linear Search

### 3.1. Algorithm(Pseudocode)

```.txt
LINEAR_SEARCH(A, n, target)
    Input: Array A of size n, search key target.
    Output: Index of target if found else -1.

    FOR i <- 0 TO n - 1 DO
        IF A[i] == target THEN
            RETURN i
        ENDIF
    END FOR
    RETURN -1
```

### 3.2. Complexity Analysis

#### 3.2.1. Time Complexity

1. **Best Case** - Occurs when the target index is 0.
   so, $B(n) = O(n)$

2. **Average Case** - Occurs when target is in middle on average.
   so, $A(n) = O(n/2) = O(n)$

3. **Worst Case** - Occurs when target is at the end position or is absent.
   so, $W(n) = O(n^2)$

#### 3.2.2. Space Complexity

Uses constant amount of extra memory regardless of the input size $n$.
so, $S(n)=O(1)$

---

## 4. Bubble Sort

### 4.1. Algorithm(Pseudocode)

```.txt
BUBBLE_SORT(A, n)
    Input: Array A of size n.
    Output: Sorted array.

    FOR i <- 0 TO n - 1 DO
        SWAPPED <- FALSE
        FOR j <- 0 TO n - 2 - i DO
            IF A[j] > A[j+1]
                SWAP(A[j], A[j+1])
                SWAPPED <- TRUE
            ENDIF
        END FOR
        IF SWAPPED == FALSE THEN BREAK
    END FOR
    RETURN A
```

### 4.2. Complexity Analysis

#### 4.2.1. Time Complexity

1. **Best Case** - Occurs when the array is already sorted (i.e., early exit flag exists).
   so, $B(n) = O(1)$

2. **Average Case** - Occurs when items in the array are in random order.
   so, $A(n) = O(n^2)$

3. **Worst Case** - Occurs when the array is reversly sorted.
   so, $W(n) = O(n^2)$

#### 4.2.2. Space Complexity

Uses constant amount of extra memory regardless of the input size $n$.
so, $S(n)=O(1)$

---

## 5. Selection Sort

### 5.1. Algorithm(Pseudocode)

```.txt
SELECTION_SORT(A, n)
    Input: Array A of size n.
    Output: Sorted array.

    FOR i <- 0 TO n - 1 DO
        min <- i
        FOR j <- i + 1 TO n - 1 DO
            IF A[min] > A[j]
                min <- j
            ENDIF
        END FOR
        SWAP(A[min], A[i])
    END FOR
```

### 5.2. Complexity Analysis

#### 5.2.1. Time Complexity

Always exactly performs $n(n-1)/2$ comparisions.
so, $T(n) = \Theta(n^2)$

#### 5.2.2. Space Complexity

Uses constant amount of extra memory regardless of the input size $n$.
so, $S(n)=O(1)$

---

## 6. Insertion Sort

### 6.1. Algorithm(Pseudocode)

```.txt
INSERTION_SORT(A, n)
    Input: Array A of size n.
    Output: Sorted array.

    FOR i <- 1 TO n - 1 DO
        key <- A[i]
        j = i - 1
        WHILE j >= 0 AND A[j] > key DO
            A[j] <- A[j+1]
            j <- j - 1
        END WHILE
    END FOR
    RETURN A
```

### 6.2. Complexity Analysis

#### 6.2.1. Time Complexity

1. **Best Case** - Occurs when the array is already sorted (i.e., early exit flag exists).
   so, $B(n) = O(1)$

2. **Average Case** - Occurs when items in the array are in random order.
   so, $A(n) = O(n^2)$

3. **Worst Case** - Occurs when the array is reversly sorted.
   so, $W(n) = O(n^2)$

#### 6.2.2. Space Complexity

Uses constant amount of extra memory regardless of the input size $n$.
so, $S(n)=O(1)$
