# 📚 Types of Recursion in Detail

---

## 1. Tail Recursion

In tail recursion, the recursive call is the last operation performed by the function.

All actions or statements are executed before the recursive call, and nothing is left to do after the call returns.

**Example:**
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

![Recursion Flow/ Tracing tree Tree](./Images/example2.png "Recursion Diagram")
---

**Tracing Tree:**

```
3 2 1

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