# Ex-1 IMPLEMENTATION-OF-SYMBOL-TABLE
# Name: ASHOK KUMAR PREETHAM KUMAR
# Register Number :212224040032
# Date : 11/04/2025
# AIM :
## To write a C program to implement a symbol table.
# ALGORITHM
1.	Start the program.
2.	Get the input from the user with the terminating symbol ‘$’.
3.	Allocate memory for the variable by dynamic memory allocation function.
4.	If the next character of the symbol is an operator then only the memory is allocated.
5.	While reading, the input symbol and memory address are inserted into the symbol table.
6.	The steps are repeated till ‘$’ is reached.
7.	To reach a variable, enter the variable to be searched and the symbol table has been checked for the corresponding variable, the variable along with its address is displayed as a result.
8.	Stop the program. 
# PROGRAM
```
#include <stdio.h> 
#include <ctype.h> 
#include <string.h> 
#include <stdlib.h> 
#define MAX_EXPRESSION_SIZE 100

int main() 
{
    int i = 0, j = 0, x = 0, n, flag = 0; 
    void *add[5]; 
    char b[MAX_EXPRESSION_SIZE], d[15], c, srch;
    printf("Enter the Expression terminated by $: "); 
    while ((c = getchar()) != '$' && i < MAX_EXPRESSION_SIZE - 1) 
    { 
        b[i++] = c; 
        
    } 
    b[i] = '\0'; n = i - 1;
    printf("Given Expression: %s\n", b);
    printf("\nSymbol Table\n"); 
    printf("Symbol\taddr\ttype\n");
    for (j = 0; j <= n; j++) 
    {
        c = b[j]; 
        if (isalpha((unsigned char)c)) 
        { 
            if (j == n || b[j + 1] == '+' || b[j + 1] == '-' || b[j + 1] == '*' || b[j + 1] == '=') 
            { 
                void *p = malloc(sizeof(char)); 
                if (p == NULL) 
                { 
                    printf("Memory allocation failed\n");
                    return 1; 
                } 
                add[x] = p; d[x] = c; 
                printf("%c\t%p\tidentifier\n", c, p); x++; 
            } 
        }
    }
    printf("\nThe symbol to be searched: "); 
    getchar(); srch = getchar();
    for (i = 0; i < x; i++) 
    { 
        if (srch == d[i]) 
        { 
        printf("Symbol Found\n"); 
        printf("%c@address %p\n", srch, add[i]); 
        flag = 1; break; 
        } 
    }
    if (flag == 0) 
    {
        printf("Symbol Not Found\n");
    }
    for (i = 0; i < x; i++) 
    { 
        free(add[i]); 
    }
    return 0;    
}
```

# OUTPUT

![image](https://github.com/user-attachments/assets/5047fb26-4cb7-49fa-a840-598d565ce3cc)

![image](https://github.com/user-attachments/assets/e83b40b0-d3e4-449d-a1f6-ebb7fe0e32f2)

# RESULT
### The program to implement a symbol table is executed and the output is verified.
