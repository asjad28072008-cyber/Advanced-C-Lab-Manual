EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.
Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:

//type your code here

```
#include <stdio.h>
#include <stdlib.h>

#define MAX 5 // Defining maximum size of the stack

// 2. Declare Global Variables
int stack[MAX];
int top = -1;

// 3. Define the Display Function
void display() {
    if (top == -1) {
        printf("Stack is empty!\n");
        return;
    }
    printf("Stack elements (from top to bottom):\n");
    for (int i = top; i >= 0; i--) {
        printf("| %d |\n", stack[i]);
    }
    printf("-----\n");
}

// Helper function to push elements onto the stack
void push(int value) {
    if (top == MAX - 1) {
        printf("Stack Overflow! Cannot push %d\n", value);
    } else {
        top++;
        stack[top] = value;
        printf("Pushed %d onto the stack.\n", value);
    }
}

// Helper function to pop elements from the stack
void pop() {
    if (top == -1) {
        printf("Stack Underflow! Nothing to pop.\n");
    } else {
        printf("Popped %d from the stack.\n", stack[top]);
        top--;
    }
}

// 4. Main Function
int main() {
    // 5. Initialize the stack and top as needed (Done via global variable declarations)
    printf("--- Stack Demonstration ---\n\n");

    // 6. Perform stack operations (push, pop, etc.)
    push(10);
    push(20);
    push(30);
    
    // 7. Use the display function to visualize the stack's contents
    display();

    // Perform more operations
    pop();
    
    // Display again to see the updated contents
    display();

    return 0;
}

```

Output:

//paste your output here

<img width="618" height="606" alt="image" src="https://github.com/user-attachments/assets/2cf3f76f-e900-4ead-8037-32075af8a6c3" />



Result:
Thus, the program to display stack elements using an array is verified successfully.
 

EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
Aim:
To create a C program to push the given element in to a stack using array.
Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:

//type your code here
```
#include <stdio.h>

#define MAX_CAPACITY 100

// 1. Declare global variables for the stack size, top index, and the stack itself.
int stack_size;
int top;
float stack[MAX_CAPACITY];

// 2. Define the push function to add a floating-point number to the stack.
void push(float element) {
    if (top >= stack_size - 1) {
        printf("Stack Overflow! Cannot push %.2f\n", element);
    } else {
        top++;
        stack[top] = element;
        printf("Successfully pushed %.2f into the stack.\n", element);
    }
}

int main() {
    // 3. Initialize the stack size, top index, and the stack itself.
    stack_size = 5; 
    top = -1;       // -1 indicates that the stack is currently empty

    printf("Stack initialized with maximum size: %d\n\n", stack_size);

    // 4. Call the push function as needed.
    push(10.55);
    push(23.40);
    push(45.67);
    push(12.00);
    push(89.12);
    
    // This call will trigger a stack overflow condition
    push(99.99);

    return 0;
}

```

Output:

//paste your output here


<img width="651" height="457" alt="image" src="https://github.com/user-attachments/assets/def335eb-411c-4474-816d-cfbd512bf8d4" />



Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:

//type your code here
```
#include <stdio.h>
#define SIZE 5

// 1. Declare global variables for the queue, rear, front, and iteration.
int queue[SIZE];
int front = -1;
int rear = -1;
int i; // Iteration variable

// Function declarations
void enqueue(int value);
void display();

int main() {
    // 3. Initialize the queue, rear, and front as needed (handled globally above).
    
    // 4. Perform queue operations and call the display function as needed.
    printf("--- Queue Operations Using Array ---\n");
    
    enqueue(10);
    enqueue(20);
    enqueue(30);
    enqueue(40);
    
    // Display the elements currently in the queue
    display();
    
    return 0;
}

// Function to insert elements into the queue
void enqueue(int value) {
    if (rear == SIZE - 1) {
        printf("Queue Overflow! Cannot enqueue %d\n", value);
    } else {
        if (front == -1) {
            front = 0;
        }
        rear++;
        queue[rear] = value;
        printf("Successfully enqueued: %d\n", value);
    }
}

// 2. Define the display function to print the elements of the queue.
void display() {
    if (front == -1 || front > rear) {
        printf("\nQueue is empty.\n");
    } else {
        printf("\nQueue elements are: ");
        for (i = front; i <= rear; i++) {
            printf("%d ", queue[i]);
        }
        printf("\n");
    }
}

```

Output:

//paste your output here

<img width="606" height="420" alt="image" src="https://github.com/user-attachments/assets/d8fcf485-581c-4664-80bd-dfb9910d9018" />


Result:
Thus, the program to display queue elements using array is verified successfully.


 
EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:

//type your code here
```
#include <stdio.h>

#define SIZE 5

// 1. Declare global variables for the size, rear, front, and the queue itself.
float queue[SIZE];
int front = -1;
int rear = -1;

// 2. Define the enqueue function to add a float to the queue.
void enqueue(float value) {
    if (rear == SIZE - 1) {
        printf("Queue Overflow! Cannot insert %.2f\n", value);
        return;
    }
    
    if (front == -1) {
        front = 0;
    }
    
    rear++;
    queue[rear] = value;
    printf("Inserted %.2f into the queue.\n", value);
}

// Function to display the queue elements
void display() {
    if (front == -1 || front > rear) {
        printf("Queue is empty.\n");
        return;
    }
    printf("Queue elements: ");
    for (int i = front; i <= rear; i++) {
        printf("%.2f ", queue[i]);
    }
    printf("\n");
}

int main() {
    // 3. Initialize the rear, front, and size of the queue as needed.
    // (Initialized globally, size defined via MACRO)
    
    // 4. Call the enqueue function as needed.
    enqueue(10.5);
    enqueue(20.3);
    enqueue(30.8);
    
    display();
    
    return 0;
}

```
Output:

//paste your output here

<img width="572" height="337" alt="image" src="https://github.com/user-attachments/assets/dbb6fddf-9b47-4301-a49b-4794a6505405" />


Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



Aim:

To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



Program:

//type your code here
```
#include <stdio.h>
#define SIZE 5

int queue[SIZE];
int front = -1;
int rear = -1;

// Function to insert elements into the queue (Enqueue)
void enqueue(int value) {
    if (rear == SIZE - 1) {
        printf("Queue is Full (Overflow)\n");
    } else {
        if (front == -1) {
            front = 0;
        }
        rear++;
        queue[rear] = value;
        printf("Inserted %d\n", value);
    }
}

// Function to delete elements from the queue (Dequeue)
void dequeue() {
    // 1. Check if the Queue is Empty
    if (front == -1) {
        printf("Queue is Empty (Underflow). No elements to delete.\n");
        return;
    }

    // 2. Delete the Front Element
    int deletedElement = queue[front];
    printf("Deleted element: %d\n", deletedElement);
    front++; // Increment front pointer to point to the next element

    // 3. Check if the Queue Becomes Empty After Deletion
    if (front > rear) {
        front = -1;
        rear = -1;
    }
}

// Function to display the queue elements
void display() {
    if (front == -1) {
        printf("Queue is Empty\n");
    } else {
        printf("Queue elements: ");
        for (int i = front; i <= rear; i++) {
            printf("%d ", queue[i]);
        }
        printf("\n");
    }
}

int main() {
    printf("--- Enqueue Operations ---\n");
    enqueue(10);
    enqueue(20);
    enqueue(30);
    display();

    printf("\n--- Dequeue Operations ---\n");
    dequeue();
    display();

    dequeue();
    dequeue();
    display(); // Should show empty since all elements are deleted

    return 0;
}

```

Output:


<img width="667" height="582" alt="image" src="https://github.com/user-attachments/assets/449d78b6-8a77-4f66-b0a0-db7531283da5" />

//paste your output here


Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
