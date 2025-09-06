# 🔄 Introduction to Recursion

---

## 📌 What is Recursion?
Recursion is a **programming technique** where a function calls itself, either **directly** or **indirectly**, to solve a problem.  
It simplifies complex problems by breaking them down into smaller subproblems until a simple **base case** is reached.

---

## 💻 Example Code Snippet (C)

```c
#include <stdio.h>

void fun(int n) {
    if (n > 0) {            // base case check
        printf("%d\n", n);  // print current value
        fun(n - 1);         // recursive call
    }
}

int main() {
    fun(3);                 // function call
    return 0;
}
```
#### output for the above code is `3 2 1` ####
![Recursion Flow/ Decision Tree](./Images/example1.png "Recursion Diagram")



