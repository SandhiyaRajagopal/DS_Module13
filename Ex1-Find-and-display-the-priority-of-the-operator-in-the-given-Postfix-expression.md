# EX 1 Display operator precedence in the infix expression.
## DATE: 22/08/25
## AIM:
To write a C program to find and display the priority of the operator in the given Postfix expression

## Algorithm
1. Define a function priority(ch) that returns a numeric value based on operator precedence.
2. Read or define the input expression as a string.
3. Scan the expression character by character from left to right.
4. If the character is an operator, call priority(ch) to get its precedence.
5. Print the operator along with its corresponding priority level.

## Program:
```
/*
Program to find and display the priority of the operator in the given Postfix expression
Developed by: SANDHIYA R
RegisterNumber: 212223240146
*/

#include <stdio.h>
#include <string.h>
int priority(char ch);
int priority(char ch) {
    switch(ch) {
        case '&':
        case '|':
            return 1; 
        case '+':
        case '-':
            return 2; 
        case '*':
        case '/':
        case '%':
            return 3; 
        case '^':
            return 4; 
        default:
            return 0; 
    }
}

int main() {
    int i, prio;
    char ch[100] = "(A*B)^C+(D%H)/F&G";


    for (i = 0; i < strlen(ch); i++) {
        // Check if current character is an operator
        if (ch[i] == '+' || ch[i] == '-' || ch[i] == '*' || ch[i] == '/' ||
            ch[i] == '%' || ch[i] == '^' || ch[i] == '&' || ch[i] == '|') {
            
            prio = priority(ch[i]);

            // Display based on priority
            printf("%c  ----> ", ch[i]);
            switch(prio) {
                case 1:
                    printf("Lowest Priority\n");
                    break;
                case 2:
                    printf("Second Lowest Priority\n");
                    break;
                case 3:
                    printf("Second Highest Priority\n");
                    break;
                case 4:
                    printf("Highest Priority\n");
                    break;
                default:
                    printf("Unknown Operator\n");
            }
        }
    }

    return 0;
}

```

## Output:
<img width="762" height="282" alt="image" src="https://github.com/user-attachments/assets/b3a27e51-d197-4bda-98e3-0e0ebb98aaed" />


## Result:
Thus the C program to find and display the priority of the operator in the given Postfix expression is implemented successfully
