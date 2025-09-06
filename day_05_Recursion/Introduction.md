# Introduction to Recursion
## What is Recursion?
### Recursion is a Programming Technique where a function call it self directly or indirectly to solve a Problem.
###

### Example Code snippet ###

`void fun(int n)
{
    if(n > 0){
        printf("%d\n", n);
        fun(n-1);
    }
}
`