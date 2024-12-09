
Structure in C
A structure in C is a user-defined data type that enables us to store a collection of different data types. It is a derived data type where each element of a structure is called a member.

Syntax of Structure
c
Copy code
struct structure_name {
    data_type member1;
    data_type member2;
    data_type memberN;
};
Example:
c
Copy code
struct employee {
    int id;
    char name[20];
    float salary;
};
Declaring Structure Variables
There are two ways to declare a structure variable:

1. By using the struct keyword inside the main() function
c
Copy code
struct employee {
    int id;
    char name[50];
    float salary;
};

struct employee e1, e2;  // Variables created inside main function
Now you can write the given code inside the main() function. The variables e1 and e2 can be used to access the values stored in the structure, similar to how objects are used in C++ or Java.

2. By declaring the variable at the time of defining the structure
c
Copy code
struct employee {
    int id;
    char name[50];
    float salary;
} e1, e2;
Accessing Members of the Structure
You can access members of a structure in two ways:

Using the dot operator (.)
Using the structure pointer operator (->)
Example of Accessing Structure Members
c
Copy code
#include<stdio.h>
#include <string.h>

struct employee {
    int id;
    char name[50];
} e1;  // Declaring e1 variable for the structure

int main() {
    // Store first employee information
    e1.id = 101;
    strcpy(e1.name, "Sonoo Jaiswal"); // Copying string into char array
    
    // Printing first employee information
    printf("Employee 1 ID: %d\n", e1.id);
    printf("Employee 1 Name: %s\n", e1.name);
    
    return 0;
}
Output:
yaml
Copy code
Employee 1 ID: 101
Employee 1 Name: Sonoo Jaiswal
Nested Structure
C allows you to nest one structure inside another to create more complex data types. A structure can be nested in the following two ways:

1. By Separate Structure
Here, we create two separate structures, but the dependent structure is used inside the main structure as a member.

c
Copy code
struct Date {
    int dd;
    int mm;
    int yyyy;
};

struct Employee {
    int id;
    char name[20];
    struct Date doj;  // Nested structure
} emp1;
2. By Embedded Structure
The embedded structure enables you to define the structure inside another structure. It requires fewer lines of code but cannot be used in multiple data structures.

c
Copy code
struct Employee {
    int id;
    char name[20];
    struct Date {
        int dd;
        int mm;
        int yyyy;
    } doj;  // Embedded structure
} emp1;
Accessing Nested Structure
To access members of a nested structure, use the following notation: Outer_Structure.Nested_Structure.member

For example:

c
Copy code
e1.doj.dd
e1.doj.mm
e1.doj.yyyy
Passing Structure to Function
Like other variables, a structure can also be passed to a function. You can either pass the structure members individually or pass the entire structure at once.

Example:
c
Copy code
#include<stdio.h>

struct address {
    char city[20];
    int pin;
    char phone[14];
};

struct employee {
    char name[20];
    struct address add;  // Nested structure
};

void display(struct employee);

int main() {
    struct employee emp;
    printf("Enter employee information:\n");
    scanf("%s %s %d %s", emp.name, emp.add.city, &emp.add.pin, emp.add.phone);
    display(emp);
}

void display(struct employee emp) {
    printf("Printing the details...\n");
    printf("%s %s %d %s", emp.name, emp.add.city, emp.add.pin, emp.add.phone);
}
Output:
css
Copy code
Printing the details...
John NewYork 10001 1234567890
Structure Padding in C
Structure padding is a concept in C where one or more empty bytes are added between memory addresses to align the data in memory. This ensures that the structure’s members are properly aligned to meet the requirements of the machine architecture, which may improve performance or prevent errors.
