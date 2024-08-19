#include <stdio.h>
#include <stdlib.h>

// Define the node structure
struct Node {
    int data;
    struct Node* next;
};

// creating node 
struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

//insert node at beginning 
void insertAtBeginning(struct Node** head, int data) {
    struct Node* newNode = createNode(data);
    newNode->next = *head;
    *head = newNode;
}

//insert at last 

void insertAtEnd(struct Node** head, int data) {
    struct Node* newNode = createNode(data);
    if (*head == NULL) {
        *head = newNode;
        return;
    }
    struct Node* temp = *head;
    while (temp->next != NULL) {
        temp = temp->next;
    }
    temp->next = newNode;
}

//Deleting a node 

void deleteNode(struct Node** head, int key) {
    struct Node* temp = *head;
    struct Node* prev = NULL;

    // If the head node holds the key to be deleted
  
    if (temp != NULL && temp->data == key) {
        *head = temp->next;
        free(temp);
        return;
    }

    // Search for the key to be deleted
    while (temp != NULL && temp->data != key) {
        prev = temp;
        temp = temp->next;
    }

    // If the key was not present in the linked list
    if (temp == NULL) return;

    // Unlink the node from the linked list
    prev->next = temp->next;
    free(temp);
}

// traversing the list 


void printList(struct Node* head) {
    struct Node* temp = head;
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}






int main() {
    struct Node* head = NULL;

    insertAtEnd(&head, 10);
    insertAtEnd(&head, 20);
    insertAtEnd(&head, 30);
    insertAtBeginning(&head, 5);

    printf("Linked list: ");
    printList(head);  // Output: 5 -> 10 -> 20 -> 30 -> NULL

    deleteNode(&head, 20);
    printf("After deletion: ");
    printList(head);  // Output: 5 -> 10 -> 30 -> NULL

    return 0;
}



class Person
{
        String name;
        int age;
        public Person(String name, int age)
        {
                this.name = name;
                this.age = age;
        }
        public void dispPerson()
        {
                System.out.println("Name: " + name);
                System.out.println("Age: " + age);
        }
}
class Student extends Person
{
        String grade;
        public Student(String name, int age, String grade)
        {
                super(name, age);
                this.grade = grade;
        }
        public void dispStudent()
        {
                dispPerson();
                System.out.println("Grade: " + grade);
        }
}
class Person
{
        String name;
        int age;
        public Person(String name, int age)
        {
                this.name = name;
                this.age = age;
        }
        public void dispPerson()
        {
                System.out.println("Name: " + name);
                System.out.println("Age: " + age);
        }
}
class Student extends Person
{
        String grade;
        public Student(String name, int age, String grade)
        {
                super(name, age);
                this.grade = grade;
        }
        public void dispStudent()
        {
                dispPerson();
                System.out.println("Grade: " + grade);
        }
}
class Person
{
        String name;
        int age;
        public Person(String name, int age)
        {
                this.name = name;
                this.age = age;
        }
        public void dispPerson()
        {
                System.out.println("Name: " + name);
                System.out.println("Age: " + age);
        }
}
class Student extends Person
{
        String grade;
        public Student(String name, int age, String grade)
        {
                super(name, age);
                this.grade = grade;
        }
        public void dispStudent()
        {
                dispPerson();
                System.out.println("Grade: " + grade);
        }
}
public class cl1
{
        public static void main(String[] args)
        {
                Student student = new Student("Jesse James", 19, "A");
                student.dispStudent();
        }
}
