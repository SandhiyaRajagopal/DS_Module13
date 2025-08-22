# Ex5 Stack Operations
## DATE: 22/08/25
## AIM:
To write a C function to perform push and pop operation of the stack in the infix to postfix conversion.

## Algorithm
1. Initialize an empty stack with top = -1.
2. To push(x): increment top and place element x at stack[top].
3. To pop(): if top == -1, return error (stack underflow).
4.  Otherwise, return stack[top] and decrement top.
   
## Program:
```
/*
Program to find and display the priority of the operator in the given Postfix expression
Developed by: SANDHIYA R
RegisterNumber: 212223240146 
*/

char stack[100];
int top = -1;
void push(char x)
{
    stack[++top] = x;
}

char pop()
{
    if(top == -1)
        return -1;
    else
        return stack[top--];
}
```

## Output:
<img width="487" height="239" alt="Screenshot 2025-08-22 143023" src="https://github.com/user-attachments/assets/9a60ecf5-0f0e-4205-afe9-165d7a0d9cf7" />



## Result:
Thus the C program to perform push and pop operation of the stack in the infix to postfix conversion is implemented successfully.
