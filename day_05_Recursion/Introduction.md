# Introduction to Recursion
## What is Recursion?
### Recursion is a Programming Technique where a function call it self directly or indirectly to solve a Problem.
###

### Example Code snippet ###



```
void fun(int n)
{
    if(n > 0){
        printf("%d\n", n);
        fun(n-1);
    }
}

int main(){
    fun(3);
    return 0;
}
```
#### output for the above code is ####
`3 2 1`
![Recursion Flow/ Decision Tree](./images/example1.png "Recursion Diagram")



