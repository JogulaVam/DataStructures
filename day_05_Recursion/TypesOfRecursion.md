# 📚 Types of Recursion in Detail

---


## 1. Tail Recursion

In tail recursion, the recursive call is the last operation performed by the function.

All actions or statements are executed before the recursive call, and nothing is left to do after the call returns.

In case of tail recursion, loops are preferred as we can easily write code in loops by looking at tail recursion code.

### Example:
```c
#include <stdio.h>
void tailRec(int n) {
    if (n == 0) return;
    printf("%d ", n);
    tailRec(n - 1); // Recursive call is the last statement
}

int main() {
    tailRec(3);
    return 0;
}
```

**Output:** `3 2 1`

## Tracing Tree:
![Recursion Flow/ Tracing Tree](./Images/example2.png "Recursion Diagram")

---

## Changing above tail recursion into the loop:

```c
void fun(int n){
    while(n > 0){
        printf("%d ", n);
        n--;
    }
}
```

**Output:** `3 2 1`

---

### 🔍 Time Complexity

The while loop runs as long as `n > 0`. In each iteration:

- It prints the value of `n` (which is an O(1) operation).
- Then decrements `n` by 1.

So, the loop executes `n` times, doing constant work each time.

✅ **Time Complexity: O(n)**

---

### 🧠 Space Complexity

This version uses iteration, not recursion. So:

- No recursive call stack is created.
- No additional memory is allocated except for the variable `n`.

✅ **Space Complexity: O(1)**

---

### 📌 Summary

| Complexity Type | Value | Reason               |
|-----------------|--------|----------------------|
| Time            | O(n)   | Loop runs `n` times  |
| Space           | O(1)   | No recursion, constant space |

---

## Conclusion

As you can see, the loop version behaves similarly to the tail recursion version. However, in terms of space complexity, the loop is preferred because it avoids the overhead of recursive stack frames.

---

## 2. Head Recursion

In head recursion, the recursive call happens before any other operations in the function.

**Example:**
```c
#include <stdio.h>
void headRec(int n) {
    if (n == 0) return;
    headRec(n - 1); // Recursive call happens first
    printf("%d ", n);
}
```


## 🔁 2. Head Recursion

### 📌 Definition:
In **head recursion**, the recursive call is made **before** any other operations in the function. This means the function keeps calling itself until it reaches the base case, and only then does it start executing the remaining statements **after** the recursive calls return.

---

### ✅ Example in C:
```c
#include <stdio.h>

void headRec(int n) {
    if (n == 0) return;
    headRec(n - 1); // Recursive call happens first
    printf("%d ", n); // Executed after recursive call returns
}

int main() {
    headRec(3);
    return 0;
}
```

### 🧠 Execution Flow:
Let’s break down how `headRec(3)` works:

1. `headRec(3)` calls `headRec(2)`
2. `headRec(2)` calls `headRec(1)`
3. `headRec(1)` calls `headRec(0)`
4. `headRec(0)` hits the base case and returns
5. Now the calls start returning:
   - `headRec(1)` prints `1`
   - `headRec(2)` prints `2`
   - `headRec(3)` prints `3`

### 🖨️ Output:
```
1 2 3
```
## Tracing Tree:
![Recursion Flow/ Tracing Tree](./Images/example3.png "Recursion Diagram")
---

## 🔄 Head Recursion vs Loop

### 🧾 Loop Version:
```c
void fun(int n){
    int i = 1;
    while(i <= n){
        printf("%d ", i);
        i++;
    }
}
```

### 🧠 Execution Flow:
- The loop runs from `i = 1` to `n`, printing each value directly.

### 🖨️ Output:
```
1 2 3
```

---

## 🔍 Comparison

| Feature              | Head Recursion                          | Loop                                 |
|----------------------|------------------------------------------|--------------------------------------|
| **Control Flow**     | Function calls itself before doing work | Iterative, uses loop control         |
| **Memory Usage**     | Uses call stack (can be expensive)      | Efficient, uses constant memory      |
| **Execution Order**  | Bottom-up (work done after recursion)   | Top-down (work done immediately)     |
| **Readability**      | Good for problems with recursive nature | Easier for simple repetitive tasks   |
| **Performance**      | Slower due to overhead of recursion     | Faster and more efficient            |

---


---

## 3. Tree (Direct) Recursion

A function calls itself more than once in its body, creating a tree-like structure of calls.

**Example:**
```c
#include <stdio.h>
void treeRec(int n) {
    if (n == 0) return;
    printf("%d ", n);
    treeRec(n - 1); // First recursive call
    treeRec(n - 1); // Second recursive call
}
```

---

## 4. Indirect Recursion

A function calls another function, which eventually calls the original function.

**Example:**
```c
#include <stdio.h>
void funB(int n); // Forward declaration

void funA(int n) {
    if (n == 0) return;
    printf("%d ", n);
    funB(n - 1);
}

void funB(int n) {
    if (n == 0) return;
    printf("%d ", n);
    funA(n - 1);
}
```

---

## 5. Nested Recursion

The argument of a recursive function itself involves a recursive call.

**Example:**
```c
#include <stdio.h>
int nestedRec(int n) {
    if (n > 100) return n - 10;
    return nestedRec(nestedRec(n + 11));
}
```

---

[⬅️ Back: Introduction to Recursion](./Introduction.md)