

EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display stack elements using linked list.

Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
Program:

//type your code here
```
#include <stdio.h>
#include <stdlib.h>

// 1. Define a structure Node with two members: data and next
struct Node {
    int data;
    struct Node* next;
};

// 2. Declare a global variable head representing the starting node of the linked list
struct Node* head = NULL;

// Function to push elements onto the stack (helper function to build the stack)
void push(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (newNode == NULL) {
        printf("Stack Overflow\n");
        return;
    }
    newNode->data = value;
    newNode->next = head; // New node points to the current head
    head = newNode;       // Head now points to the new node
}

// 3. Define a function display to print the elements of the linked list
void display() {
    // 4. Declare a pointer p and initialize it with the head of the linked list
    struct Node* p = head;

    if (p == NULL) {
        printf("Stack is empty.\n");
        return;
    }

    printf("Stack elements: ");
    // 5. Use a while loop to traverse the linked list
    while (p != NULL) {
        // 6. Print the data of the current node
        printf("%d -> ", p->data);
        
        // 7. Move to the next node using the next pointer
        p = p->next;
    }
    printf("NULL\n");
}

int main() {
    // Pushing elements to demonstrate the display function
    push(10);
    push(20);
    push(30);
    push(40);

    // Call the display function to show the stack elements
    display();

    return 0;
}

```

Output:

//paste your output here

<img width="593" height="208" alt="image" src="https://github.com/user-attachments/assets/c356239b-f97b-40c9-9287-018340ff65a3" />



Result:
Thus, the program to display stack elements using linked list is verified successfully. 



EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
Aim:
To write a C program to pop an element from the given stack using liked list.

Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
Program:

//type your code here
```
#include <stdio.h>
#include <stdlib.h>

// Define the structure for a node in the stack
struct Node {
    int data;
    struct Node* next;
};

// Global top/head pointer for the stack
struct Node* head = NULL;

// Function to push an element onto the stack
void push(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (newNode == NULL) {
        printf("Stack Overflow! Memory allocation failed.\n");
        return;
    }
    newNode->data = value;
    newNode->next = head;
    head = newNode;
    printf("%d pushed to stack.\n", value);
}

// Function to pop an element from the stack following the given algorithm
void pop() {
    // 1. Check for Empty Stack
    // 2. If head is equal to NULL, Print "Stack is empty."
    if (head == NULL) {
        printf("Stack is empty.\n");
        return;
    }

    // 3. Else Proceed to the next step.
    struct Node* temp = head;
    printf("Popped element: %d\n", temp->data);

    // 4. Set head to point to the next node in the stack.
    head = head->next;

    // Free the memory of the popped node
    free(temp);
}

// Function to display the elements of the stack
void display() {
    if (head == NULL) {
        printf("Stack is empty.\n");
        return;
    }
    struct Node* temp = head;
    printf("Stack elements: ");
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    // Pushing elements to demonstrate the pop operation
    push(10);
    push(20);
    push(30);
    display();

    // Performing pop operations
    pop();
    display();

    pop();
    display();

    pop();
    display();

    // Trying to pop from an empty stack to test the algorithm condition
    pop();

    return 0;
}

```
Output:

//paste your output here

<img width="552" height="545" alt="image" src="https://github.com/user-attachments/assets/9b6b708d-4ce1-4c81-a891-913c5cadae9d" />



Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display queue elements using linked list.
Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
Program:

//type your code here
```
#include <stdio.h>
#include <stdlib.h>

// Structure to create a node for the linked list
struct Node {
    int data;
    struct Node* next;
};

// Global pointers to keep track of the front and rear of the queue
struct Node* front = NULL;
struct Node* rear = NULL;

// Function to insert elements into the queue
void enqueue(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (newNode == NULL) {
        printf("Queue Overflow\n");
        return;
    }
    newNode->data = value;
    newNode->next = NULL;
    
    if (front == NULL && rear == NULL) {
        front = rear = newNode;
    } else {
        rear->next = newNode;
        rear = newNode;
    }
    printf("%d enqueued to queue\n", value);
}

// Function to display queue elements using a linked list
void display() {
    // 1. Check if Queue is Empty
    if (front == NULL) {
        printf("Queue is Empty\n");
        return;
    }

    // 2. Display Queue Elements
    printf("Queue elements: ");
    
    // Using a temporary pointer to traverse without destroying the queue
    struct Node* temp = front; 
    
    while (temp != NULL) {
        // 3. Print the data of the current node
        printf("%d ", temp->data);
        
        // 4. Update the pointer to point to the next node
        temp = temp->next;
    }
    printf("\n");
    
    // 5. End the display function
}

int main() {
    int choice, value;

    while (1) {
        printf("\n--- Queue Operations Menu ---\n");
        printf("1. Enqueue\n");
        printf("2. Display\n");
        printf("3. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter value to insert: ");
                scanf("%d", &value);
                enqueue(value);
                break;
            case 2:
                display();
                break;
            case 3:
                exit(0);
            default:
                printf("Invalid choice! Please try again.\n");
        }
    }

    return 0;
}

```

Output:

//paste your output here

<img width="232" height="497" alt="image" src="https://github.com/user-attachments/assets/e4db2315-6cc9-4253-895a-cec55dad1916" />


Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

Aim:
To write a C program to insert elements in queue using linked list

Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
Program:

//type your code here
```
#include <stdio.h>
#include <stdlib.h>

// Structure to define a node in the queue
struct Node {
    int data;
    struct Node* next;
};

// Global pointers to keep track of the front and rear of the queue
struct Node* front = NULL;
struct Node* rear = NULL;

// Function to insert an element into the queue (Enqueue operation)
void enqueue(int value) {
    // 1. Allocate Memory for New Node
    struct Node* p = (struct Node*)malloc(sizeof(struct Node));
    
    if (p == NULL) {
        printf("Queue Overflow / Memory Allocation Failed\n");
        return;
    }

    // 2. Set Data and Next Pointer
    p->data = value;
    p->next = NULL;

    // 3. Check if Queue is Empty
    if (front == NULL && rear == NULL) {
        // 4. Set both front and rear to point to the new node p
        front = p;
        rear = p;
    } else {
        // 5. Set the next pointer of the current rear to point to the new node p
        rear->next = p;
        rear = p; // Update rear to the new node
    }
    
    printf("Successfully inserted %d into the queue.\n", value);
    // 6. End of Enqueue Operation
}

// Function to display the elements of the queue
void display() {
    if (front == NULL) {
        printf("Queue is empty.\n");
        return;
    }
    
    struct Node* temp = front;
    printf("Queue elements: ");
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

// Main function to test the implementation
int main() {
    int choice, value;

    printf("--- Queue Using Linked List Implementation ---\n");
    while (1) {
        printf("\n1. Enqueue (Insert)\n2. Display\n3. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter the value to insert: ");
                scanf("%d", &value);
                enqueue(value);
                break;
            case 2:
                display();
                break;
            case 3:
                printf("Exiting program.\n");
                exit(0);
            default:
                printf("Invalid choice! Please try again.\n");
        }
    }
    return 0;
}

```

Output:

//paste your output here

<img width="342" height="528" alt="image" src="https://github.com/user-attachments/assets/c0801cdc-e7be-44c8-8a87-d21a3ec141ba" />


Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

Program:

//type your code here
```
#include <stdio.h>
#include <stdlib.h>
#include <limits.h> // Used for INT_MIN to indicate an error value

// Structure to represent a node in the linked list
struct Node {
    int data;
    struct Node* next;
};

// Structure to represent the queue
struct Queue {
    struct Node* front;
    struct Node* rear;
};

// Function to create a new node
struct Node* newNode(int data) {
    struct Node* temp = (struct Node*)malloc(sizeof(struct Node));
    temp->data = data;
    temp->next = NULL;
    return temp;
}

// Function to create an empty queue
struct Queue* createQueue() {
    struct Queue* q = (struct Queue*)malloc(sizeof(struct Queue));
    q->front = q->rear = NULL;
    return q;
}

// Function to add an element to the queue (Enqueue)
void enqueue(struct Queue* q, int data) {
    struct Node* temp = newNode(data);
    
    if (q->rear == NULL) {
        q->front = q->rear = temp;
        return;
    }
    
    q->rear->next = temp;
    q->rear = temp;
}

// --- FUNCTION TO FIND THE PEEK OF THE QUEUE ---
int peek(struct Queue* q) {
    // 1. Check if the queue is empty
    if (q->front == NULL) {
        printf("Error: The queue is empty.\n");
        return INT_MIN; // Returns a minimum integer value as an error indicator
    }
    
    // 2. Access the front element
    return q->front->data;
}

// Main function to demonstrate the implementation
int main() {
    struct Queue* q = createQueue();
    
    // 1. Add elements to the queue first
    enqueue(q, 10);
    enqueue(q, 20);
    enqueue(q, 30);
    
    // 2. Now check the front element
    printf("The front element (peek) is: %d\n", peek(q));
    
    return 0;
}


```

Output:

//paste your output here


<img width="476" height="232" alt="image" src="https://github.com/user-attachments/assets/2cad9c43-3deb-4256-a17b-49316e16e525" />



Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


