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
## 🌳 What is a Tracing Tree?

A Tracing Tree (also called Recursion Tree) is a diagrammatic representation of recursive calls made by a function.

- It helps us trace the execution flow step by step.

- Each node in the tree represents a function call.

- The branches show how one function call leads to further recursive calls.

![Recursion Flow/ Tracing tree Tree](./Images/example1.png "Recursion Diagram")

The function fun(n) is a simple recursive function that:

Prints the value of n.
Calls itself with n - 1 until n becomes 0.
So, for fun(3), the calls will be:

fun(3) → prints 3
fun(2) → prints 2
fun(1) → prints 1
fun(0) → base case, does nothing
This results in n recursive calls, each doing O(1) work (just a printf). 

🔍 Time Complexity Analysis
The function fun(n) is a simple recursive function that:

Prints the value of n.
Calls itself with n - 1 until n becomes 0.
So, for fun(3), the calls will be:

fun(3) → prints 3
fun(2) → prints 2
fun(1) → prints 1
fun(0) → base case, does nothing
This results in n recursive calls, each doing O(1) work (just a printf).

✅ Time Complexity: O(n)

🧠 Space Complexity Analysis
Space complexity in recursive functions is primarily due to the call stack.

Each recursive call adds a new frame to the stack. So for fun(n), the maximum depth of recursion is n.

There are no additional data structures or memory allocations, just the call stack.

✅ Space Complexity: O(n)



# 🔁 Loops vs 🔄 Recursion

## 1. Definition
- **Loop**: A control structure (`for`, `while`, `do-while`) that repeats a block of code until a condition is false.  
- **Recursion**: A function calls itself (directly or indirectly) until a base condition is 
met. 

## 2. Key Differences

| Aspect              | Loop                                  | Recursion                                                       |
|---------------------|---------------------------------------|-----------------------------------------------------------------|
| **Control Mechanism** | Uses iteration (`for`, `while`)       | Function calls itself                                            |
| **Termination**      | Condition in loop header/body         | Base condition                                                   |
| **Memory Usage**     | Efficient (constant memory)           | Each call adds a stack frame → more memory usage                 |
| **Performance**      | Usually faster                       | Slower due to function call overhead                             |
| **Readability**      | Better for simple repetition          | Better for problems with natural recursive structure (trees, divide & conquer) |
| **Risk**             | Infinite loop if condition never false | Stack overflow if base case missing                              |


---

## Types of Recursion

- **Tail Recursion**: The recursive call is the last statement in the function.
- **Head Recursion**: The recursive call happens before any other operations in the function.
- **Tree (Direct) Recursion**: A function calls itself more than once in its body, creating a tree-like structure of calls.
- **Indirect Recursion**: A function calls another function, which eventually calls the original function.
- **Nested Recursion**: The argument of a recursive function itself involves a recursive call.

---
Let us see about types of recursions in detail on the next page.

[➡️ Next: Types of Recursion in Detail](./TypesOfRecursion.md)

