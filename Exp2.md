EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION
Aim:
To write a C program for passing structure as function and returning a structure from a function

Algorithm:
1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
 
Program:

//type your code here
```
#include <stdio.h>

// 1. Define structure numbers with members a and b
struct numbers {
    int a;
    int b;
};

// Function prototype for passing and returning a structure
struct numbers add(struct numbers n);

int main() {
    // 2. Declare variable n of type numbers
    struct numbers n;
    struct numbers result;

    // 3. Prompt the user to enter values for a and b
    printf("Enter the value for a: ");
    // 4. Input values for a and b into n using scanf
    scanf("%d", &n.a);
    
    printf("Enter the value for b: ");
    scanf("%d", &n.b);

    // 5. Call the add function with n as an argument
    result = add(n);

    // 6. Print the result returned by the add function
    printf("\n--- Result ---\n");
    printf("Sum calculated inside structure: %d\n", result.a);

    // 7. Return 0
    return 0;
}

// Function that accepts a structure as an argument and returns a structure
struct numbers add(struct numbers n) {
    struct numbers temp;
    
    // Add members a and b, storing the sum in the member 'a' of a new structure
    temp.a = n.a + n.b;
    temp.b = 0; 
    
    return temp;
}

```



Output:

//paste your output screenshots here


<img width="601" height="357" alt="image" src="https://github.com/user-attachments/assets/433a4d0a-11ba-440a-a5de-4aa560e3c7e2" />





Result:
Thus, the program is verified successfully
