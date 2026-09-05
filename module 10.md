EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:

//type your code here
```
#include <stdio.h>
#include <stdlib.h>
#include <stdbool.h>

// 1. Define the structure for a node in a linked list
struct Node {
    char data;
    struct Node* next;
};

// 2. Define the search function to find a specific character in the linked list
bool searchElement(struct Node* head, char target) {
    struct Node* current = head;
    
    while (current != NULL) {
        if (current->data == target) {
            return true; // Element found
        }
        current = current->next;
    }
    return false; // Element not found
}

// Function to helper insert a new node at the beginning of the list
void insertAtHead(struct Node** head_ref, char new_data) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    new_node->data = new_data;
    new_node->next = (*head_ref);
    (*head_ref) = new_node;
}

// Function to print the linked list
void printList(struct Node* node) {
    while (node != NULL) {
        printf("%c -> ", node->data);
        node = node->next;
    }
    printf("NULL\n");
}

// Function to free allocated memory
void freeList(struct Node* head) {
    struct Node* temp;
    while (head != NULL) {
        temp = head;
        head = head->next;
        free(temp);
    }
}

int main() {
    // 3. Initialize the head of the linked list as needed
    struct Node* head = NULL;
    char target;

    // Insert sample character data into the linked list
    insertAtHead(&head, 'E');
    insertAtHead(&head, 'D');
    insertAtHead(&head, 'C');
    insertAtHead(&head, 'B');
    insertAtHead(&head, 'A');

    printf("Linked List elements: ");
    printList(head);

    // 4. Call the search function and perform operations
    printf("\nEnter the character to search: ");
    scanf(" %c", &target);

    if (searchElement(head, target)) {
        printf("Element '%c' is FOUND in the linked list.\n", target);
    } else {
        printf("Element '%c' is NOT FOUND in the linked list.\n", target);
    }

    // Clean up memory
    freeList(head);

    return 0;
}

```

Output:

//paste your output here


<img width="756" height="332" alt="image" src="https://github.com/user-attachments/assets/7cae696a-9c5d-47a3-a4ac-aae9259939cf" />


Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:

//type your code here
```
#include <stdio.h>
#include <stdlib.h>

// Step 1: Define the structure for a node in a linked list
struct Node {
    char data;
    struct Node* next;
};

// Step 2: Define the insert function to insert a new node with character data at the end of the linked list
void insertAtEnd(struct Node** head_ref, char new_data) {
    // Allocate memory for new node
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    
    // Assign data and set next to NULL since it's being added to the end
    new_node->data = new_data;
    new_node->next = NULL;

    // If the Linked List is empty, make the new node the head
    if (*head_ref == NULL) {
        *head_ref = new_node;
        return;
    }

    // Otherwise, traverse until the last node
    struct Node* last = *head_ref;
    while (last->next != NULL) {
        last = last->next;
    }

    // Change the next of the last node to point to the new node
    last->next = new_node;
}

// Helper function to display the linked list
void displayList(struct Node* node) {
    while (node != NULL) {
        printf("%c -> ", node->data);
        node = node->next;
    }
    printf("NULL\n");
}

int main() {
    // Step 3: Initialize the head of the linked list as needed
    struct Node* head = NULL;

    // Step 4: Call the insert function and perform other linked list operations as needed
    printf("Inserting character data into the linked list:\n");
    insertAtEnd(&head, 'A');
    insertAtEnd(&head, 'B');
    insertAtEnd(&head, 'C');
    insertAtEnd(&head, 'D');

    // Display the final list
    printf("Linked List contents: ");
    displayList(head);

    // Free the allocated memory before exiting
    struct Node* current = head;
    struct Node* next_node;
    while (current != NULL) {
        next_node = current->next;
        free(current);
        current = next_node;
    }

    return 0;
}

```

Output:

//paste your output here

<img width="672" height="335" alt="image" src="https://github.com/user-attachments/assets/bee87fd3-4d1d-449d-af60-2c17cb2227cc" />


 
Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
Aim:
To write a C program to traverse a doubly linked list.

Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:

//type your code here
```
#include <stdio.h>
#include <stdlib.h>

// Define the structure for a doubly linked list node
struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
};

// Function to traverse and print the doubly linked list
void traverseList(struct Node* head) {
    // 1. Initialize a temporary pointer (temp) to the head of the list.
    struct Node* temp = head;

    printf("Doubly Linked List Elements: ");
    
    // 2. Use a while loop to traverse the list until the end (temp == NULL) is reached.
    while (temp != NULL) {
        // 3. Inside the loop, print the data of the current node.
        printf("%d ", temp->data);
        
        // 4. Move to the next node by updating the temp pointer (temp = temp->next).
        temp = temp->next;
    }
    printf("\n");
}

// Helper function to create a new node
struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = NULL;
    return newNode;
}

int main() {
    // Creating a sample doubly linked list: 10 <-> 20 <-> 30
    struct Node* head = createNode(10);
    struct Node* second = createNode(20);
    struct Node* third = createNode(30);

    // Linking the nodes together
    head->next = second;
    second->prev = head;
    
    second->next = third;
    third->prev = second;

    // Call the traversal function
    traverseList(head);

    // Free allocated memory
    free(head);
    free(second);
    free(third);

    return 0;
}

```

Output:

//paste your output here

<img width="630" height="252" alt="image" src="https://github.com/user-attachments/assets/69a93465-5455-45a2-a318-e76af18cecca" />



Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:

//type your code here
```
#include <stdio.h>
#include <stdlib.h>

// Define the structure for a doubly linked list node
struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
};

// Function to insert an element at the end of the doubly linked list
void insertAtEnd(struct Node** head_ref, int value) {
    // 1. Create a new node and allocate memory for it
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    
    // 2. Set the data of the new node to the provided value
    newNode->data = value;
    newNode->next = NULL; // Since it will be the last node

    // 3. If the list is empty, set the new node as the head
    if (*head_ref == NULL) {
        newNode->prev = NULL;
        *head_ref = newNode;
        return;
    }

    // 4. If the list is not empty, traverse the list to find the last node
    struct Node* last = *head_ref;
    while (last->next != NULL) {
        last = last->next;
    }

    // 5. Set the new node's prev pointer to the last node 
    // and update the last node's next pointer to the new node
    last->next = newNode;
    newNode->prev = last;
}

// Function to print/traverse the doubly linked list
void displayList(struct Node* node) {
    printf("Doubly Linked List: ");
    while (node != NULL) {
        printf("%d <-> ", node->data);
        node = node->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;

    // Inserting elements into the doubly linked list
    insertAtEnd(&head, 10);
    insertAtEnd(&head, 20);
    insertAtEnd(&head, 30);
    insertAtEnd(&head, 40);

    // Displaying the list elements
    displayList(head);

    return 0;
}

```

Output:

//paste your output here

<img width="750" height="261" alt="image" src="https://github.com/user-attachments/assets/7d71eb32-e1c4-401e-bb62-1daf9026f976" />



Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST




Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.


Program:

//type your code here
```
#include <stdio.h>
#include <stdlib.h>

// Definition of the Node structure
struct Node {
    int data;
    struct Node* next;
};

// Function to delete a given element from the linked list
void deleteElement(struct Node** head, int key) {
    // 1. Check if the Linked List is Empty
    if (*head == NULL) {
        printf("The list is empty. Cannot delete element.\n");
        return;
    }

    struct Node* temp = *head;
    struct Node* prev = NULL;

    // 3. Handle Deletion of the First Node
    if (temp != NULL && temp->data == key) {
        *head = temp->next; // Update the head to point to the next node
        free(temp);         // Free the memory allocated to the node to be deleted
        printf("Element %d deleted successfully.\n", key);
        return;             // Exit the function
    }

    // 2 & 4. Traverse and Delete from the Middle or End
    while (temp != NULL && temp->data != key) {
        prev = temp;
        temp = temp->next; // Move to the next node
    }

    // 4. When the node with the element is found
    if (temp != NULL) {
        prev->next = temp->next; // Update the previous node's next pointer
        free(temp);              // Free the memory allocated to the node to be deleted
        printf("Element %d deleted successfully.\n", key);
        return;
    }

    // 5. Handle the Case when the Element is Not Found
    printf("Element %d is not present in the list.\n", key);
}

// Helper function to insert a node at the beginning of the list
void insertAtBeginning(struct Node** head, int new_data) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    new_node->data = new_data;
    new_node->next = *head;
    *head = new_node;
}

// Helper function to print the linked list
void printList(struct Node* node) {
    while (node != NULL) {
        printf("%d -> ", node->data);
        node = node->next;
    }
    printf("NULL\n");
}

// Main function to demonstrate the program
int main() {
    struct Node* head = NULL;

    // Creating a sample linked list: 40 -> 30 -> 20 -> 10
    insertAtBeginning(&head, 40);
    insertAtBeginning(&head, 30);
    insertAtBeginning(&head, 20);
    insertAtBeginning(&head, 10);

    printf("Original Linked List: ");
    printList(head);

    // Test Case 1: Deleting the first node
    printf("\nDeleting 10 (First Node):\n");
    deleteElement(&head, 10);
    printList(head);

    // Test Case 2: Deleting a node from the middle
    printf("\nDeleting 30 (Middle Node):\n");
    deleteElement(&head, 30);
    printList(head);

    // Test Case 3: Handling an element not found
    printf("\nDeleting 50 (Element Not Found):\n");
    deleteElement(&head, 50);
    printList(head);

    return 0;
}

```

Output:

//paste your output here



<img width="738" height="582" alt="image" src="https://github.com/user-attachments/assets/3172d9ff-db41-465b-a4b1-3482156a098e" />



Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





