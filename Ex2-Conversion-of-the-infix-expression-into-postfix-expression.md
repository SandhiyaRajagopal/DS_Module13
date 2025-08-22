# Ex2 Conversion of the infix expression into postfix expression
## DATE:22/08/25
## AIM:
To write a C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule.

## Algorithm
1. Create a stack for operators and an empty string for the postfix expression.
2. Read the infix expression from left to right.
3. If it’s a number, add it to postfix; if it’s (, push it to the stack.
4. If it’s an operator or ):

Pop from the stack to postfix if the stack top has higher or equal precedence.
Push the operator to the stack (or discard ( if it’s a closing parenthesis).
5. At the end, pop all remaining operators from the stack to postfix.

## Program:
```
/*
Program to convert the infix expression into postfix expression
Developed by: SANDHIYA R
RegisterNumber: 212223240146 
*/

#include<stdio.h>
#include<ctype.h>

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
int priority(char x)
{
    if(x == '(')
        return 0;
    if(x == '&' || x == '|')
        return 1;
    if(x == '+' || x == '-')
        return 2;
    if(x == '*' || x == '/' || x == '%')
        return 3;
    if(x == '^')
        return 4;
    return 0;
}
char IntoPost(char *exp)
{
    char *e, x;
   
   
    e = exp;
    
    while(*e != '\0')
    {
        if(isalnum(*e))
            printf("%c ",*e);
        else if(*e == '(')
            push(*e);
        else if(*e == ')')
        {
            while((x = pop()) != '(')
                printf("%c ", x);
        }
        else
        {
            while(priority(stack[top]) >= priority(*e))
                printf("%c ",pop());
            push(*e);
        }
        e++;
    }
    
    while(top != -1)
    {
        printf("%c ",pop());
    }return 0;
}


int main()
{
    char exp[100]="2*3%(2-1)+5|3";
    IntoPost(exp);
    return 1;
    
}

```

## Output:

<img width="558" height="147" alt="image" src="https://github.com/user-attachments/assets/cfe2f991-b530-4cb7-b726-e5bc621dc006" />


## Result:
Thus, the C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule is implemented successfully.
