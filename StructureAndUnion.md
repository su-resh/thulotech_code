
### **Structure and Union**
### **Structure**

Structure is a user-defined datatype in C which allows us to combine different variables of dissimilar datatypes under a single name to store a particular type of record.

**Array and Structure**

 Structure is somehow similar to an array. It's like a mixed bag that can hold various details, unlike an array that only keeps similar things.

 For instance, if we need to store records of student which consists of student name, address, roll no and age, we cannot do so by using array. We need to define a structure to hold this information.

**Defining a structure**

*struct* keyword is used to define a structure. *struct* defines a new datatype which is collection of different types of data.
```
struct structure_name {
    Datatype1 member1;
    Datatype2 member2;
};
```
Eg:
```
struct Book
{
    char name[20];
    float price;
    int pages;
    char author[20];
}
```

**Declaring structure variable**

Structure variable can be declared in two ways:
1) Declaring structure variable separately:

   Eg:
    ```
   struct Book
   {
    char name[20];
    float price;
    int pages;
   };
   struct Book b1,b2;  //declaring variables of Book
   ```
2) Declaring variables with structure definition:

   Eg:
   ```
   struct Book{
    char name[20];
    float price;
    int pages;
   }b1,b2;     //declaring structure variables b1,b2
   ```
**Structure initialization**

Structure can be initialized at compile time as:
```
struct Book {
    char name[20];
    float price;
    int pages;
};
struct Book b1={"Ram",1200.50,450};
```
Or
```
struct Book {
    char name[20];
    float price;
    int pages;
};
struct Book b1;
b1.name="Ram";
b1.price=1200.50;
b1.pages=450;
```
**Accessing structure members**

The members of the structure can be accesed by using the dot(.) operator.

SYNTAX:
Structure_variable.member;

Eg:
```
struct Book{
    char name[20];
    float price;
    int pages;
}b1;
b1.name="Ram";  //accessing structure members
```
***Example.1***
```
#include<stdio.h>
struct student
{
   int rollno;
   char name[50];
   int marks;
};
void main()
 {
   struct student s={110,"Prakriti",568};
   printf("Roll no : %d\n", s.roll);
   printf("Name : %s\n", s.name);
   printf("Marks : %d\n", s.marks);
}
```
***Example.2***
```
#include <stdio.h>

// Define a structure named 'Person'
struct Person {
    char name[50];
    int age;
    float height;
};

int main() {
    // Declare a variable of type 'struct Person'
    struct Person person1;

    // Assign values to the members of the structure
    strcpy(person1.name, "John Doe");
    person1.age = 25;
    person1.height = 5.9;

    // Access and print the values
    printf("Name: %s\n", person1.name);
    printf("Age: %d\n", person1.age);
    printf("Height: %.2f\n", person1.height);

    return 0;
}
```
**Arrays of Structure**

Like we can create array of int,float or char datatypes,we can also create array of structures since structure is also a user-defined datatypes.
In normal structures, we have to make 50 structure variable like as st1,st2,st3,....st50,which is not a good technique.In this situation,we can use array of structure to store records of 50 students.

Eg:

**Normal Structures**
```
struct Student {
    char name[15];
    int roll;
    int marks;
}st1,st2,st3....st50;
```
**Array Structures**
```
struct Student {
    char name[15];
    int roll;
    int marks;
}st[50];
```
**Initializing of array of structure**

We can initialize array of structure in the same way as single structure.

Eg:
```
struct Student{
    char name[15];
    int roll;
    int marks;
};
struct Students[2]={'Prakriti',26,95},{'Bisheshata',13,98};
```

**Examples**
```
#include<stdio.h>
#include <string.h>
struct student{
int rollno;
char name[10];
};
int main(){
int i;
struct student st[5];
printf("Enter Records of 5 students");
for(i=0;i<5;i++){
printf("\nEnter Rollno:");
scanf("%d",&st[i].rollno);
printf("\nEnter Name:");
scanf("%s",&st[i].name);
}
printf("\nStudent Information List:");
for(i=0;i<5;i++){
printf("\nRollno:%d, Name:%s",st[i].rollno,st[i].name);
}
   return 0;
}
```

**Array within structures**

C language permits the use of array as structures members.

Eg:
```
struct Student{
    char name[50];
    int rollno;
    int mark[3];
}st1;
```
Here,the member mark is an array of 3 elements mark[0],mark[1],mark[2].

These are accessed like:<br>
st1.mark[0];<br>
st1.mark[1];<br>
st1.mark[2];<br>
st1.mark[3];

**Nested structure (Structure within structure)**

A nested structure in C is a structure that contains one or more members that are themselves structures. Nested structures are useful for organizing complex data and can help improve a program's readability and maintainability.
This above representation of nested structure can be declared as:
```
struct date{
    int year;
    int month;
    int day;
}
struct person{
char name[20];
struct date DOB;   //nested structured
char address[20];
}p;
```
Alternatively, this can be written as:
```
struct person{
char name[20];
    struct date{
        int year;
        int month;
        int day;
    }DOB;
char address[20];
}p;
```
Here,the members of the nested structure are accessed as:
```
p.DOB.year
p.DOB.month
p.DOB.day
```
The members of outer structure are accessed as usual.
```
p.name
p.address
```
**Example**
```
#include <stdio.h>
struct date{
    int year,month,day;
};
struct person{
    char name[20];
    struct date DOB;
    char address[20];
}p;
main(){
    printf("Enter name,DOB-year,month,dayand address:\t");
    scanf("%s%d%d%d%s",&p.name,&p.DOB.year,&p.DOB,&p.DOB.day,&p.address);
    printf("The details of person are: \n");
    printf("Name: %s\n",p.name);
    printf("DOB: %d-%d-%d\n",p.DOB.year,p.DOB.month,p.DOB.day);
    printf("Address: %s", p.address);s
}
```
**Pointer to Strucutre**<br>
Pointer can be used with structure to store address of the structure.It is used to create complex data structures such as linked lists, trees, graphs, and so on.

**Declaration**<br>
Following is the declaration for pointers to structures in C programming −

```
struct tagname *ptr;
```
where *ptr** is pointer variable of structured type.<br>

**Acessing**<br>
The member of the structured can be accessed using arrow pointer(->).
```
ptr-> membername;
```
Also,they can be accessed using *operator as:
```
(*ptr).membername;
```
**Examples**
```
#include <stdio.h>

// Define a structure
struct Student {
    int studentID;
    char name[50];
    float GPA;
};

int main() {
    // Declare a structure variable
    struct Student student1;

    // Initialize the structure variable
    student1.studentID = 123;
    strcpy(student1.name, "John Doe");
    student1.GPA = 3.75;

    // Declare a pointer to a structure of type Student
    struct Student *ptrStudent;

    // Assign the address of student1 to the pointer
    ptrStudent = &student1;

    // Access structure members using the pointer
    printf("Student ID: %d\n", ptrStudent->studentID);
    printf("Name: %s\n", ptrStudent->name);
    printf("GPA: %.2f\n", ptrStudent->GPA);

    return 0;
}
```
**Self-referential structure**<br>
A self-referential structure, also known as a linked structure, is a structure in which a member of the structure is a pointer to another instance of the same type of structure.
Consider:
```
struct List{
    int data;
    struct List *next;
};
```
Here, **List** is a structure which has two members:<br>
1) data of type int
2) next which is pointer of parent type structure(List)<br>

This concept is commonly used in the implementation of linked lists.

**Example**
```
#include <stdio.h>
#include <stdlib.h>

// Define a self-referential structure for a linked list node
typedef struct Node {
    int data;
    struct Node* next; // Pointer to the next Node
} Node;

// Function to create a new node with given data
Node* createNode(int data) {
    Node* newNode = (Node*)malloc(sizeof(Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

int main() {
    // Create three nodes for a linked list
    Node* head = createNode(1);
    Node* second = createNode(2);
    Node* third = createNode(3);

    // Link the nodes together to form a linked list
    head->next = second;
    second->next = third;

    // Traverse the linked list and print the data
    Node* current = head;
    while (current != NULL) {
        printf("%d -> ", current->data);
        current = current->next;
    }
    printf("NULL\n");

    // Free the allocated memory
    free(head);
    free(second);
    free(third);

    return 0;
}

```
**Unions**
A union is a special data type available in C that allows to store different data types in the same memory location. You can define a union with many members, but only one member can contain a value at any given time. Unions provide an efficient way of using the same memory location for multiple-purpose.
**Defining a Union**
To define a union, you must use the union statement in the same way as you did while defining a structure. The union statement defines a new data type with more than one member for your program.<br>Eg:
```
#include <stdio.h>
#include <string.h>
 
union Data {
   int i;
   float f;
   char str[20];
};
 
int main( ) {

   union Data data;        

   printf( "Memory size occupied by data : %d\n", sizeof(data));

   return 0;
}
```

**Accessing Union members**
To access any member of a union, we use the member access operator (.).<br>Eg:
```
#include <stdio.h>
#include <string.h>
 
union Data {
   int i;
   float f;
   char str[20];
};
 
int main( ) {

   union Data data;

   data.i = 10;
   data.f = 220.5;
   strcpy( data.str, "C Programming");

   printf( "data.i : %d\n", data.i);
   printf( "data.f : %f\n", data.f);
   printf( "data.str : %s\n", data.str);

   return 0;
}
```
**Structure Vs Union**
| **Characteristic**      | **Structures**                                        | **Unions**                                             |
|-------------------------|-------------------------------------------------------|--------------------------------------------------------|
| **Memory Allocation**   | Each member has its own memory space.| All members share the same memory space.             |
| **Usage**               | Suitable for grouping related but different data types.| Useful when you want to save memory with different data types sharing the same space. |
| **Access to Members**   | You can access all members simultaneously.| Only one member can be accessed at a time.|
| **Memory Size**         | Size is the sum of the sizes of individual members.| Size is determined by the largest member.
**Array Vs Structure**
| Aspect                      | Array                                                      | Structure                                                  |
|-----------------------------|------------------------------------------------------------|------------------------------------------------------------|
| **Definition**              | An array is a data structure that stores elements of the same data type in contiguous memory locations. | A structure, or struct, is a composite data type that groups together variables of different data types under a single name. |
| **Usage in Databases**      | Arrays are not standard in relational databases. Some non-relational databases may support arrays as a data type. | Structures are not commonly used in standard relational databases. |
| **Storage**                 | In relational databases, data is organized into tables with rows and columns. Arrays are not used to store multiple values within a single column. | Relational databases organize data into tables, where each column has a specific data type. Structures are not used to represent columns directly. |
| **Example**                 | In a non-relational database that supports arrays, a column may contain an array of values, like `[1, 2, 3]`. Each element in the array is accessible by its index. | In some NoSQL databases or object-relational databases, you might find structures or nested documents grouping multiple values together. However, this differs from a traditional programming language struct. |

**Passing structure to functions**
In C, structures can be passed to functions similar to other data types. When passing a structure to a function, you have the flexibility to do it by passing the structure itself or by passing a pointer to the structure.
**Passing by Value:**
When you pass a structure by value, a copy of the structure is made, and modifications inside the function do not affect the original structure.
```
void printPoint(struct Point p) {
    // Function code
}

// Call: printPoint(myPoint);
```
**Passing by Reference (Using Pointers):**
When you pass a structure by reference, you use a pointer to the structure. This allows modifications inside the function to affect the original structure.
```
void printPoint(struct Point p) {
    // Function code
}
// Call: printPoint(myPoint);
```
**Example**
```
#include <stdio.h>

// Define a structure
struct Point {
    int x;
    int y;
};

// Function that takes a structure by value
void printPoint(struct Point p) {
    printf("Point coordinates: (%d, %d)\n", p.x, p.y);
}

int main() {
    // Create a structure variable
    struct Point myPoint = {5, 10};

    // Call the function and pass the structure
    printPoint(myPoint);

    return 0;
}
```
