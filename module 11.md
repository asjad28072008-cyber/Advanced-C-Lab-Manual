

EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
Aim:
To write a C program to create a function to find the greatest number

Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
Program:
//type your code here
```
#include <stdio.h>

// Function to find the maximum of four numbers using if-else statements
int max_of_four(int a, int b, int c, int d) {
    if (a >= b && a >= c && a >= d) {
        return a;
    } else if (b >= a && b >= c && b >= d) {
        return b;
    } else if (c >= a && c >= b && c >= d) {
        return c;
    } else {
        return d;
    }
}

int main() {
    // Declare variables to store user input and the result
    int n1, n2, n3, n4, greater;

    // Prompt user and take four integers as input
    printf("Enter four integers: ");
    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);

    // Call the function and store the result
    greater = max_of_four(n1, n2, n3, n4);

    // Print the greatest number
    printf("The greatest number is: %d\n", greater);

    return 0;
}

```

Output:
//paste your output here


<img width="486" height="357" alt="image" src="https://github.com/user-attachments/assets/839dbc1d-8f6f-4e8a-9094-80d1576ea7a7" />


Result:
Thus, the program  that create a function to find the greatest number is verified successfully.


 
EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
Program:
//type your code here
```
#include <stdio.h>

// Function to calculate and print the maximum bitwise values less than k
void calculate_the_max(int n, int k) {
    int max_and = 0;
    int max_or = 0;
    int max_xor = 0;

    // Nested loops to iterate through all pairs (i, j) where 1 <= i < j <= n
    for (int i = 1; i <= n; i++) {
        for (int j = i + 1; j <= n; j++) {
            int current_and = i & j;
            int current_or = i | j;
            int current_xor = i ^ j;

            // Update maximum AND if it is less than k
            if (current_and > max_and && current_and < k) {
                max_and = current_and;
            }
            
            // Update maximum OR if it is less than k
            if (current_or > max_or && current_or < k) {
                max_or = current_or;
            }
            
            // Update maximum XOR if it is less than k
            if (current_xor > max_xor && current_xor < k) {
                max_xor = current_xor;
            }
        }
    }

    // Print the final maximum values
    printf("%d\n", max_and);
    printf("%d\n", max_or);
    printf("%d\n", max_xor);
}

int main() {
    int n, k;

    // Take two integers as input from the user
    scanf("%d %d", &n, &k);

    // Call the function with input values
    calculate_the_max(n, k);

    return 0;
}

```

Output:
//paste your output here

<img width="537" height="360" alt="image" src="https://github.com/user-attachments/assets/98e96259-935f-495f-9624-f6e66b6be48e" />


Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
Aim:
To write a C program to write the logic for the requests

Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
Program:
//type your code here
```
#include <stdio.h>
#include <stdlib.h>

int main() {
    // 1. Declare variables noshel and noque to store the number of shelves and queries
    int noshel, noque;

    // 2. Use scanf to take two integers as input for shelves and queries
    if (scanf("%d %d", &noshel, &noque) != 2) {
        return 1;
    }

    // 3. Declare a 2D array shelarr and an array nobookarr
    // Using dynamic memory allocation to handle variable sizes
    int** shelarr = (int**)malloc(sizeof(int*) * noshel);
    int* nobookarr = (int*)calloc(noshel, sizeof(int));

    for (int i = 0; i < noshel; i++) {
        shelarr[i] = NULL;
    }

    // 4. Declare variables to process queries (such as type, shelf index, and book pages/index)
    int type, x, y;

    // 5. Use a for loop to iterate over the queries
    for (int i = 0; i < noque; i++) {
        if (scanf("%d", &type) != 1) break;

        if (type == 1) {
            // Type 1: Insert a book with 'y' pages at the end of the 'x'-th shelf
            scanf("%d %d", &x, &y);
            nobookarr[x]++;
            shelarr[x] = (int*)realloc(shelarr[x], sizeof(int) * nobookarr[x]);
            shelarr[x][nobookarr[x] - 1] = y;

        } else if (type == 2) {
            // Type 2: Print the number of pages of the 'y'-th book on the 'x'-th shelf
            scanf("%d %d", &x, &y);
            printf("%d\n", shelarr[x][y]);

        } else if (type == 3) {
            // Type 3: Print the total number of books on the 'x'-th shelf
            scanf("%d", &x);
            printf("%d\n", nobookarr[x]);
        }
    }

    // Free allocated memory
    for (int i = 0; i < noshel; i++) {
        if (shelarr[i] != NULL) {
            free(shelarr[i]);
        }
    }
    free(shelarr);
    free(nobookarr);

    return 0;
}

```

Output:
//paste your output here


<img width="460" height="427" alt="image" src="https://github.com/user-attachments/assets/d5278e32-40db-426f-ac05-e7e3ca691b1a" />


Result:
Thus, the program to write the logic for the requests is verified successfully.


 
EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
Aim:
To write a C program print the sum of the integers in the array.

Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.



Program:
//type your code here
```
#include <stdio.h>

int main() {
    // 1. Declare a variable n to store the number of integers.
    int n;

    // 2. Use scanf to take an integer n as input.
    printf("Enter the number of elements: ");
    scanf("%d", &n);

    // 3. Declare an array a of size n to store the integers.
    int a[n];

    // 4. Declare a variable sum and initialize it to zero.
    int sum = 0;

    // 5. Use a for loop to iterate n times:
    printf("Enter %d integers:\n", n);
    for (int i = 0; i < n; i++) {
        // 6. Use scanf to input each integer and add it to the sum.
        scanf("%d", &a[i]);
        sum = sum + a[i];
    }

    // 7. Print the final sum using printf.
    printf("Sum of the integers in the array = %d\n", sum);

    return 0;
}

```

Output:
//paste your output here


<img width="562" height="422" alt="image" src="https://github.com/user-attachments/assets/f02e8d45-8785-4edb-b385-0dec3c0ec103" />
 


Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


 
EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A      SENTENCE



Aim:

To write a C program that counts the number of words in a given sentence.

Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



Program:
//type your code here
```
#include <stdio.h>
#include <ctype.h>

int main() {
    char sentence[1000];
    int count = 0;
    int in_word = 0;

    // 1. Input the sentence from the user
    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin);

    // 2. Process each character of the sentence
    for (int i = 0; sentence[i] != '\0'; i++) {
        // 4. Handle spaces and punctuation marks by skipping them
        if (isspace(sentence[i]) || ispunct(sentence[i])) {
            in_word = 0;
        } 
        // 3. If it's the first non-space character after a space or at the start
        else if (in_word == 0) {
            in_word = 1;
            count++; // Increment the word count
        }
    }

    // 5. Display the final result
    printf("Total number of words: %d\n", count);

    return 0;
}

```

Output:
//paste your output here

<img width="562" height="311" alt="image" src="https://github.com/user-attachments/assets/5da715ad-7bf8-4c73-ac38-abc656ffac14" />



Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
