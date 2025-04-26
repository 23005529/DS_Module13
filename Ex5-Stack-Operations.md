# Ex5 Stack Operations
## DATE: 26.04.2025
## AIM:
To write a C function to perform push and pop operation of the stack in the infix to postfix conversion.

## Algorithm
1. Start by setting top = -1 and declare stack as a character array.
2. For push(), increment top and store the character in stack[top].
3. For pop(), check if top == -1; if yes, return -1 (stack underflow).
4. Otherwise, return stack[top].
5. After returning, decrement top.

## Program:
```
/*
Program to find and display the priority of the operator in the given Postfix expression
Developed by: Aliya Sheema 
RegisterNumber: 212223230011
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

![image](https://github.com/user-attachments/assets/4e8970ab-d31b-4629-bfa6-169497d7b5be)


## Result:
Thus the C program to perform push and pop operation of the stack in the infix to postfix conversion is implemented successfully.
