EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
Aim:
To write a C program print the lowercase English word corresponding to the number
Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
Program:

//type your code here
```
#include <stdio.h>

int main() {
    int n;

    // Prompt user for input
    printf("Enter an integer: ");
    if (scanf("%d", &n) != 1) {
        printf("Invalid input.\n");
        return 1;
    }

    // Switch statement to match the specific number mapping
    switch (n) {
        case 5:
            printf("seventy one\n");
            break;
        case 6:
            printf("seventy two\n");
            break;
        case 7:
            printf("seventy three\n");
            break;
        case 8:
            printf("seventy four\n");
            break;
        case 9:
            printf("seventy five\n");
            break;
        case 10:
            printf("seventy six\n");
            break;
        case 11:
            printf("seventy seven\n");
            break;
        case 12:
            printf("seventy eight\n");
            break;
        case 13:
            printf("seventy nine\n");
            break;
        default:
            if (n > 13) {
                printf("Greater than 13\n");
            } else {
                printf("Less than 5\n");
            }
            break;
    }

    return 0;
}

```



Output:


//paste your output here


<img width="553" height="247" alt="image" src="https://github.com/user-attachments/assets/de6a27d6-094b-445e-83d6-ac1cf16ac650" />





Result:
Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:

//type your code here
 ```
#include <stdio.h>
#include <string.h>

int main() {
    // Declare a character array to store the input string
    char a[100];
    
    // Read the input string (including spaces if any, up to newline)
    scanf("%[^\n]%*c", a);
    
    // Outer loop to check each digit from '0' to '9'
    for (char digit = '0'; digit <= '9'; digit++) {
        int c = 0; // Initialize counter for the current digit
        
        // Inner loop to scan through each character of the string
        for (int i = 0; i < strlen(a); i++) {
            if (a[i] == digit) {
                c++; // Increment count if a match is found
            }
        }
        
        // Print the frequency count followed by a space
        printf("%d ", c);
    }
    
    printf("\n");
    return 0;
}

```



Output:


//paste your output here

<img width="548" height="186" alt="image" src="https://github.com/user-attachments/assets/f195cd29-7c14-4e92-82e5-780630edf318" />






Result:
Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
Aim:
To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:

//type your code here
```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// Function to find the next lexicographical permutation
int next_permutation(int n, char **s) {
    // 1. Find the largest index i such that s[i] < s[i+1]
    int i = n - 2;
    while (i >= 0 && strcmp(s[i], s[i+1]) >= 0) {
        i--;
    }
    
    // If no such index exists, we are at the last permutation
    if (i < 0) {
        return 0;
    }
    
    // 2. Find the largest index j greater than i such that s[i] < s[j]
    int j = n - 1;
    while (strcmp(s[i], s[j]) >= 0) {
        j--;
    }
    
    // 3. Swap s[i] and s[j]
    char *tmp = s[i];
    s[i] = s[j];
    s[j] = tmp;
    
    // 4. Reverse the elements from index i + 1 to the end of the array
    int left = i + 1;
    int right = n - 1;
    while (left < right) {
        tmp = s[left];
        s[left] = s[right];
        s[right] = tmp;
        left++;
        right--;
    }
    
    return 1;
}

int main() {
    // Step 2: Declare variables
    int n;
    char **s;

    // Step 4: Read the number of strings from the user
    printf("Enter the number of strings: ");
    if (scanf("%d", &n) != 1 || n <= 0) {
        return 1;
    }

    // Step 3: Dynamically allocate memory for the array of string pointers
    s = (char **)malloc(n * sizeof(char *));
    if (s == NULL) {
        return 1;
    }

    // Step 4: Dynamically allocate memory for each string and read input
    printf("Enter %d strings:\n", n);
    for (int i = 0; i < n; i++) {
        s[i] = (char *)malloc(100 * sizeof(char)); // Allocates space for up to 99 characters
        if (s[i] == NULL) {
            return 1;
        }
        scanf("%s", s[i]);
    }

    // Optional: Sort the initial array so permutations begin in strict lexicographical order
    for (int i = 0; i < n - 1; i++) {
        for (int j = i + 1; j < n; j++) {
            if (strcmp(s[i], s[j]) > 0) {
                char *tmp = s[i];
                s[i] = s[j];
                s[j] = tmp;
            }
        }
    }

    printf("\nAll permutations in strict lexicographical order:\n");
    
    // Step 5: Permutation Generation Loop
    do {
        for (int i = 0; i < n; i++) {
            printf("%s%c", s[i], i == n - 1 ? '\n' : ' ');
        }
    } while (next_permutation(n, s));

    // Step 6: Memory Deallocation
    for (int i = 0; i < n; i++) {
        free(s[i]);
    }
    free(s);

    // Step 7: End
    return 0;
}

```



Output:


//paste your output here

<img width="680" height="420" alt="image" src="https://github.com/user-attachments/assets/835e0ea7-c548-4ad8-a5b8-c20ef097b5ef" />






Result:
Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:

//type your code here

```
#include <stdio.h>

int main() {
    int n, i, j, min;

    // Read the value of n from the user
    printf("Enter the value of n: ");
    if (scanf("%d", &n) != 1) {
        return 1;
    }

    // Calculate the length of the side of the square matrix
    int len = n * 2 - 1;

    // Matrix Generation Loop
    for (i = 0; i < len; i++) {
        for (j = 0; j < len; j++) {
            
            // Calculate min as the minimum distance to the four borders
            int top = i;
            int bottom = len - 1 - i;
            int left = j;
            int right = len - 1 - j;

            min = top;
            if (bottom < min) min = bottom;
            if (left < min) min = left;
            if (right < min) min = right;

            // Print the value based on the minimum distance
            printf("%d ", n - min);
        }
        printf("\n");
    }

    return 0;
}

```


Output:


//paste your output here



<img width="511" height="495" alt="image" src="https://github.com/user-attachments/assets/8ef2af3b-44ab-46a5-9fae-f9c794c73a3a" />




Result:
Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

Program:

//type your code here
```
#include <stdio.h>

// Function declaration
int square();

int main() {
    int result;

    // Call the square() function and store the returned value
    result = square();

    // Display the result
    printf("The square of the number is: %d\n", result);

    return 0;
}

// Function definition: without arguments, with return type
int square() {
    int num, squared_val;

    // Ask the user to input a number
    printf("Enter an integer: ");
    scanf("%d", &num);

    // Calculate the square of the number
    squared_val = num * num;

    // Return the squared value
    return squared_val;
}

```



Output:


//paste your output here


<img width="617" height="276" alt="image" src="https://github.com/user-attachments/assets/dc9d8c5c-4d9f-4d0e-be84-55b2ea861efd" />





Result:
Thus, the program is verified successfully



























