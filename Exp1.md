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

// Type your code here
```
#include <stdio.h>

// 1. Declare structure eligible with age (integer) and n (character array)
struct eligible {
    int age;
    char n[50];
};

int main() {
    int i, size;

    printf("Enter the number of persons: ");
    scanf("%d", &size);

    // 2. Declare an array of structure 'eligible'
    struct eligible e[size];

    // Loop to process each person in the array
    for (i = 0; i < size; i++) {
        printf("\nEnter details for person %d:\n", i + 1);
        
        printf("Enter name: ");
        scanf("%s", e[i].n);
        
        printf("Enter age: ");
        scanf("%d", &e[i].age);

        // 4. Check eligibility (Age above 6 years)
        if (e[i].age <= 6) {
            printf("Vaccine Eligibility: No\n");
        } else {
            printf("Vaccine Eligibility: Yes\n");
        }

        // 5. Print details
        printf("Details -> Name: %s, Age: %d\n", e[i].n, e[i].age);
    }

    // 6. Return 0
    return 0;
}

```


Output:

// paste the output screenshot


<img width="417" height="627" alt="image" src="https://github.com/user-attachments/assets/0b6b822c-d8fc-4b78-aa22-c541c9ba70fb" />



Result:
Thus, the program is verified successfully.
