EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
Program:

//type your code here
```
#include <stdio.h>

// Step 1: Declare structure 'eligible' with age (integer) and n (character array)
struct eligible {
    int age;
    char n[50];
};

int main() {
    int i, num;

    printf("Enter the number of persons: ");
    scanf("%d", &num);

    // Declaring an array of structures as per the experiment title
    struct eligible e[num];

    // Loop to input data, check eligibility, and display details
    for(i = 0; i < num; i++) {
        printf("\n--- Entering details for person %d ---\n", i + 1);
        
        // Step 3: Input age and name using scanf, store in e
        printf("Enter Name: ");
        scanf("%s", e[i].n);
        printf("Enter Age: ");
        scanf("%d", &e[i].age);

        // Step 4: Eligibility Check
        if (e[i].age <= 6) {
            printf("Vaccine Eligibility: No\n");
        } else {
            printf("Vaccine Eligibility: Yes\n");
        }

        // Step 5: Print details
        printf("Details -> Name: %s, Age: %d\n", e[i].n, e[i].age);
    }

    // Step 6: Return 0
    return 0;
}

```

Output:

//paste your output here
<img width="702" height="576" alt="image" src="https://github.com/user-attachments/assets/b21bada6-5270-4db3-aa8e-d2cf72dcae39" />


Result:
Thus, the program is verified successfully. 



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

// 1. Define structure numbers with members a and b.
struct numbers {
    int a;
    int b;
};

// Function declaration for add
struct numbers add(struct numbers num);

int main() {
    // 2. Declare variable n of type numbers.
    struct numbers n;
    struct numbers result;

    // 3. Prompt the user to enter values for a and b.
    printf("Enter value for a: ");
    // 4. Input values for a and b into n using scanf.
    scanf("%d", &n.a);
    
    printf("Enter value for b: ");
    scanf("%d", &n.b);

    // 5. Call the add function with n as an argument.
    result = add(n);

    // 6. Print the result returned by the add function.
    printf("\n--- Result Structure ---\n");
    printf("Sum stored in member 'a': %d\n", result.a);

    // 7. Return 0
    return 0;
}

// Function definition that accepts a structure and returns a structure
struct numbers add(struct numbers num) {
    struct numbers temp;
    
    // Perform addition and store the result inside the structure members
    temp.a = num.a + num.b;
    temp.b = 0; // Initializing the unused member
    
    return temp;
}

```



Output:


//paste your output here

<img width="487" height="370" alt="image" src="https://github.com/user-attachments/assets/fc588f70-d7e2-4e32-8914-8205dce73252" />



Result:
Thus, the program is verified successfully


 
EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

Aim:
To write a C program to read a file name from user

Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare a character array name to store the file name.
4.	Prompt the user to enter a file name.
Use scanf to input the file name into the name array.
5.	Print a message indicating that the file with the specified name has been created successfully.
6.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
1.	Print a message indicating that the file has been opened successfully.
2.	Use fclose to close the file.
3.	Print a message indicating that the file has been closed.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:

//type your code here

```
#include <stdio.h>
#include <stdlib.h>

int main() {
    // 3. Declare a file pointer p and a character array to store the file name
    FILE *p;
    char name[100];

    // 4. Prompt the user to enter a file name and use scanf to input it
    printf("Enter the file name: ");
    scanf("%s", name);

    // 5. Print a message indicating that the file creation is initiated
    printf("Creating file '%s'...\n", name);

    // 6. Use fopen to open the file in write mode ("w")
    p = fopen(name, "w");

    // Check if the file opening was successful or unsuccessful
    if (p == NULL) {
        printf("Error: Could not create or open the file.\n");
        return 1; // Exit the program with a non-zero status
    }

    // 1. Print a message indicating that the file has been opened successfully
    printf("File opened successfully.\n");

    // 2. Use fclose to close the file
    fclose(p);

    // 3. Print a message indicating that the file has been closed
    printf("File closed successfully.\n");

    // 5. Return 0 to indicate successful program execution
    return 0;
}

```


Output:


//paste your output here




<img width="852" height="212" alt="image" src="https://github.com/user-attachments/assets/3728890d-e49a-48b2-b66b-cf50d8209a6f" />







Result:
Thus, the program is verified successfully
 


EXP NO:4   PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE
Aim:
To write a C program to read, a file and insert text in that file
Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare character arrays name and text. Declare an integer variable num.
4.	Prompt the user to enter a file name and the number of strings.
Use scanf to input the file name into the name array and the number of strings into the num variable.
5.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
6.	Print a message indicating that the file has been opened successfully.
1.	Use a loop to input strings from the user and write them to the file using fputs.
2.	Use fclose to close the file.
3.	Print a message indicating that data has been added successfully.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:

//type your code here
```
#include <stdio.h>

int main() {
    // Declare file pointer, character arrays, and integer variable
    FILE *p;
    char name[100];
    char text[100];
    int num;

    // Prompt user for file name and number of strings
    printf("Enter the file name: ");
    scanf("%s", name);
    
    printf("Enter the number of strings: ");
    scanf("%d", &num);

    // Open the file in write mode ("w")
    p = fopen(name, "w");

    // Check if the file opening was unsuccessful
    if (p == NULL) {
        printf("Error: Could not open or create the file.\n");
        return 1; 
    }

    // Print message indicating file opened successfully
    printf("File has been opened successfully.\n");

    // Loop to input strings from the user and write them to the file
    printf("Enter the %d strings:\n", num);
    for (int i = 0; i < num; i++) {
        scanf("%s", text);
        fputs(text, p);
        fputs("\n", p); // Adds a newline character after each string in the file
    }

    // Close the file
    fclose(p);

    // Print message indicating data has been added successfully
    printf("Data has been added successfully.\n");

    // Return 0 to indicate successful execution
    return 0;
}

```



Output:


//paste your output here

<img width="798" height="317" alt="image" src="https://github.com/user-attachments/assets/f3d02267-55c3-4214-bb3a-bf61ac59ed0a" />





Result:
Thus, the program is verified successfully



Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

Aim:
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

Algorithm:
1.Input the number of subjects.

2.Read the integer value n from the user, which represents the number of subjects.

3.Dynamically allocate memory:

4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).

5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.

6.Input the details of each subject

7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.

8.Display the details of each subject

9.Use another for loop to print the name and marks of each subject.

10.Free the allocated memory

11.After all operations are done, call free(s) to release the dynamically allocated memory.

12.Return from the main function

13.End the program by returning 0.

Program:

//type your code here
```
#include <stdio.h>
#include <stdlib.h>

// Define the structure for a subject
struct Subject {
    char name[50];
    int marks;
};

int main() {
    int n;
    struct Subject *s;

    // 1 & 2. Input and read the number of subjects from the user
    printf("Enter the number of subjects: ");
    scanf("%d", &n);

    // 3, 4 & 5. Dynamically allocate memory using malloc and check if allocation fails
    s = (struct Subject *)malloc(n * sizeof(struct Subject));
    if (s == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    // 6 & 7. Input the name and marks of each subject using a for loop
    for (int i = 0; i < n; i++) {
        printf("\nEnter details for subject %d:\n", i + 1);
        printf("Enter subject name: ");
        scanf("%s", s[i].name);
        printf("Enter marks: ");
        scanf("%d", &s[i].marks);
    }

    // 8 & 9. Display the stored details using another for loop
    printf("\n--- Displaying Subject Details ---\n");
    for (int i = 0; i < n; i++) {
        printf("Subject Name: %s, Marks: %d\n", s[i].name, s[i].marks);
    }

    // 10 & 11. Free the dynamically allocated memory to prevent memory leaks
    free(s);

    // 12 & 13. Return from the main function and end the program
    return 0;
}

```



Output:


//paste your output here


<img width="537" height="642" alt="image" src="https://github.com/user-attachments/assets/dccb24be-51b4-4915-9497-06f28b65f1f4" />





Result:
Thus, the program is verified successfully
