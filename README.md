# C++ Structures and Pointer Exercises

This repository contains C++ programs on **structures, arrays, and pointers**.  
It includes code for **Student and Employee structures** as well as **pointer-array examples**.

---

## **1️⃣ Student Structure**

**Question:**  
Create a structure `Student` with:
- roll number  
- name  
- marks  

Input details of 5 students and display students who scored **more than 75 marks**.

**Code:**
```cpp
#include <iostream>
using namespace std;

struct Student {
    int roll;
    string name;
    int marks;
};

int main() {
    Student s[5];

    for(int i = 0; i < 5; i++) {
        cout << "Enter roll, name, marks: ";
        cin >> s[i].roll >> s[i].name >> s[i].marks;
    }

    cout << "Students scoring more than 75:\n";
    for(int i = 0; i < 5; i++) {
        if(s[i].marks > 75)
            cout << s[i].roll << " " << s[i].name << " " << s[i].marks << endl;
    }
    return 0;
}

```
## **2️⃣ Employee Structure**

**Question:**
Define a structure Employee with:
- employee ID
- name
- basic salary

Calculate and display gross salary: **gross = basic + 20% HRA + 10% DA.**

**Code:**
```cpp
#include <iostream>
using namespace std;

struct Employee {
    int id;
    string name;
    double basic;
};

int main() {
    Employee e;
    cout << "Enter employee ID, name, basic salary: ";
    cin >> e.id >> e.name >> e.basic;

    double gross = e.basic + 0.2*e.basic + 0.1*e.basic;
    cout << "Gross Salary: " << gross << endl;

    return 0;
}
```
**Explanation:**

Gross salary = **basic * (1 + 0.2 + 0.1) = basic * 1.3**


## **3️⃣ Pointer and Array Examples**

**Question:**
Understand pointers with arrays and structs.

**Code:**
```cpp
#include <iostream>
using namespace std;

struct Data { int x; int y; };
struct Item { int price; };

int main() {
    // Example 1
    int arr1[] = {10, 20, 30, 40};
    int *p1 = arr1;
    cout << *p1 << " " << *(p1+1) << " " << *(p1+3) << endl;

    // Example 2
    int arr2[] = {5, 10, 15, 20};
    int *p2 = arr2 + 2;
    cout << *p2 << " " << *(p2-1) << endl;

    // Example 3
    int arr3[5] = {1,2,3,4,5};
    for(int i=0;i<5;i++) cout << *(arr3+i) << " ";
    cout << endl;

    // Example 4
    int arr4[] = {2,4,6,8};
    int *p4 = arr4;
    p4++;
    cout << *p4 << endl;

    // Example 5
    int arr5[] = {7,14,21};
    cout << arr5[1] << " " << 1[arr5] << endl;

    // Example 6
    int arr6[] = {10,20,30};
    int *p6 = arr6;
    cout << *p6 + 1 << " " << *(p6+1) << endl;

    // Example 7
    int arr7[] = {3,6,9,12};
    int *p7 = arr7;
    while(p7 <= &arr7[3]) {
        cout << *p7 << " ";
        p7++;
    }
    cout << endl;

    // Example 8
    int arr8[] = {1,2,3};
    int *p8 = arr8;
    for(int i=0;i<3;i++) cout << *(p8++) << " ";
    cout << endl;

    // Example 9 - pointer addresses
    int arr9[] = {10,20,30};
    int *p9 = arr9;
    cout << p9 << " " << p9+1 << endl;

    // Example 10 - char array pointer
    char arr10[] = {'A','B','C','\0'};
    char *p10 = arr10;
    cout << p10 << " " << p10+1 << endl;

    // Example 11 - struct Data pointer
    Data arrData[] = {{1,2},{3,4},{5,6}};
    Data *pData = arrData;
    cout << pData->x << " " << (pData+1)->y << endl;

    // Example 12 - struct Item pointer
    Item arrItem[] = {100,200,300};
    Item *pItem = arrItem;
    cout << pItem[2].price << " " << (*(pItem+1)).price << endl;

    return 0;
}
```
**Expected Output (Summary):**

```cpp
10 20 40
15 10
1 2 3 4 5
4
14 14
11 20
3 6 9 12
1 2 3
<address1> <address2>  (example, varies)
ABC BC
1 4
300 200
```
**Explanation:**
- arr is the base address of the array.
- *(arr + i) = element at index i.
- p++ moves the pointer to next element.
- p->x = (*p).x
- 1[arr] = arr[1]


