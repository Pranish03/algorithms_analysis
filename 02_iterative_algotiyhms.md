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

1. **Best Case** - Occurs when the algorithm terminates on single step i.e. either $a = 0$ or $a\;mod\;b = 0$.
   so, $B(n) = O(n)$

2. **Average Case** - Occurs when each step replaces $(a,b)\rightarrow(b, a\;mod\;b)$.
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

#### 3.2.1. Time Complexity

Algorithm has a single loop that runs from $2$ to $n$, iterating ($n-2$) times.
so, $T(n) = O(n)$

#### 3.2.2. Space Complexity

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
