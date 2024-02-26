# Standard Template Library (STL)
The **Standard Template Library** is a set of C++ template classes to provide common programming tools to implemet algorithms and data structures like vectors, map, queues, stack etc.One of the key benifits of the STL is that it proives a way to write generic, reusable code that can be applied to different data types.
### Vector in C++
In C++, vectors are used to store elements of similar data types. The size of vector can grow dynamically.
Vectors are part of the C++ Standard Template Library. To use vectors, we need to include ```vector``` header file in our program.
### Example: 
```C++
#include <iostream>
#include <vector>

int main() {
    std::vector<std::string> myVector;
    myVector.push_back("Good ");
    myVector.push_back("Day");

    for (std::vector<std::string>::const_iterator it = myVector.begin(); it != myVector.end(); ++it)
        std::cout << *it;

    return 0;
}

```
### Basic Operations:
The ```vector``` class provides various methods to execute different operations. Some of them are:

- **Add**
- **Access**
- **Change**
- **Remove**

### 1) Adding Elements to a Vector
We use the ```push_back()``` function to add single element to a vector. Here's an example:
``` C++
#include <iostream>
#include <vector>
#include <stdio.h>

int main() {
    // Declare a vector of integers and initialize it with values
    std::vector<int> myVector;

    // Add elements to the vector using push_back
    myVector.push_back(10);
    myVector.push_back(20);

    // Display the initial elements in the vector
    printf("Elements in the vector: ");

    // Use a range-based for loop to iterate through the vector
    for (int element : myVector) {
        printf("%d ", element);
    }

    // Display a message before adding more elements
    printf("\nElements after pushing 30 and 40: ");

    // Add more elements to the vector
    myVector.push_back(30);
    myVector.push_back(40);

    // Use the same range-based for loop to iterate through the updated vector
    for (int element : myVector) {
        printf("%d ", element);
    }

    return 0;
}

```
### 2) Access the Elements of a Vector
In C++ we use the index value to access the element present in the vector. We use ```at()``` function in order to excess the element from the required index. Here's an example:
```C++
#include <iostream>
#include <vector>
using namespace std;

int main() {
  // Declare a vector of integers and initialize it with values 1, 2, 3, 4, 5
  vector<int> data {1, 2, 3, 4, 5};

  // Display the element at Index 0 using the at() method
  cout << "Element at Index 0: " << data.at(0) << endl;

  // Display the element at Index 2 using the at() method
  cout << "Element at Index 2: " << data.at(2) << endl;

  // Display the element at Index 4 using the at() method
  cout << "Element at Index 4: " << data.at(4);

  return 0;
}

```
### 3) Change Vector Element
Changing vector element also can be done by using ```at()``` function. Here's an example:
``` C++
#include <iostream>
#include <vector>
#include <stdio.h>

int main() {
    // Declare a vector of integers and initialize it with values
    std::vector<int> data {1, 2, 3, 4, 5};

    // Display the initial vector
    printf("Initial Vector: ");

    // Use a range-based for loop to iterate through the vector
    for (const int& i : data) {
        printf("%d  ", i);
    }

    // Change elements at indexes 1 and 4
    data.at(1) = 9;
    data.at(4) = 7;

    // Display the updated vector
    printf("\n Updated Vector: ");

    // Use the same range-based for loop to iterate through the updated vector
    for (const int& i : data) {
        printf("%d  ", i);
    }
     return 0;
}

```
### 4) Deleting the Elements of Vector
To delete a single element from vector we use a ```pop_back``` function. Here's an example below:
``` C++
#include <iostream>
#include <vector>

using namespace std;

int main() {
  vector<int> odd_numbers{1, 3, 5, 7};
  
  // initial vector
  cout << "Initial Vector: ";
  for (int i : odd_numbers) {
    cout << i << " ";
  }

  // remove the last element
  odd_numbers.pop_back();

  // final vector
  cout << "\nAfter deleteing 7: ";
  for (int i : odd_numbers) {
    cout << i << " ";
  }
  
  return 0;
}
```
# Queue:
The STL `queue` provides the queue data structure. This structure follows **First In First Out** principle. <br>

### Inserting Element to a Queue
We can use `push()` function to insert the element in queue. This method pushes an element back to a queue. Here's an example below:
``` C++
#include <iostream>
#include <queue>

using namespace std;

int main() {
    // Create a queue
    queue<int> myQueue;

    // Display the initial queue
    cout << "Initial Queue: ";
    while (!myQueue.empty()) {
        cout << myQueue.front() << " ";
        myQueue.pop();
    }
    cout << endl;

    // Inserting elements into the queue
    myQueue.push(10);
    myQueue.push(20);
    myQueue.push(30);

    // Display the updated queue 
    printf("Updated Queue: ");
    while (!myQueue.empty()) {
        printf("%d ", myQueue.front());
        myQueue.pop();
    }
    printf("\n");

    return 0;
}
```
### Accessing Element from the Queue
We can access the element of a `queue` using the functions below: <br>
- `front()`
- `back()`

### Front():
This functions returns the element from the front of the queue. Here's an example below:
``` C++
#include <stdio.h>
#include <queue>

using namespace std;

int main() {
    // Create a queue
    queue<int> myQueue;

    // Inserting elements into the queue
    myQueue.push(10);
    myQueue.push(20);
    myQueue.push(30);

    // Accessing the front element of the queue 
    if (!myQueue.empty()) {
        int frontElement = myQueue.front();
        printf("Front Element of the Queue: %d\n", frontElement);
    } else {
        printf("The queue is empty.\n");
    }

    return 0;
}
```
### back():
This functions returns the element from the back of the queue. Here's an example below:
``` C++
#include <iostream>
#include <queue>

using namespace std;

int main() {
    // Create a queue
    queue<int> myQueue;

    // Inserting elements into the queue
    myQueue.push(10);
    myQueue.push(20);
    myQueue.push(30);

    // Accessing the back element of the queue 
    if (!myQueue.empty()) {
        int backElement = myQueue.back();
        printf("Back Element of the Queue: %d\n", backElement);
    } else {
        printf("The queue is empty.\n");
    }

    return 0;
}
```
### Accessing the Size of the Queue
We can see the size of the elements provided in queue using `size()` function. Here's an example:
``` C++
#include <iostream>
#include <queue>

using namespace std;

int main() {
    // Create a queue
    queue<int> myQueue;

    // Inserting elements into the queue
    myQueue.push(10);
    myQueue.push(20);
    myQueue.push(30);

    // Get the size of the queue 
    size_t queueSize = myQueue.size();
    printf("Size of the Queue: %d \n", queueSize);

    return 0;
}
```
### Removing an Element from Queue:
We can use the `pop()` method to remove an element from the front of a queue.Here's an example:
``` C++
#include <iostream>
#include <queue>
using namespace std;

int main() {
    // Create a queue of string
    queue<string> animals;

    // Push elements into the queue
    animals.push("Cat");
    animals.push("Dog");
    animals.push("Fox");

    // Display the initial queue
    cout << "Initial Queue: ";
    while (!animals.empty()) {
        cout << animals.front() << ", ";
        animals.pop();
    }
    cout << endl;

    // Re-populate the queue
    animals.push("Elephant");
    animals.push("Lion");

    // Display the updated queue
    cout << "Updated Queue: ";
    while (!animals.empty()) {
        cout << animals.front() << ", ";
        animals.pop();
    }
    cout << endl;

    return 0;
}
```
# Deque:
A deque, short for "double-ended queue," is a dynamic data structure that extends the capabilities of a queue by allowing insertion and deletion of elements from both ends. A header file named as `<deque>` should be used inorder to use this function in C++.

### Inserting Elements to a Deque:

There are two ways to insert elements to a deque. <br>

### 1) push_back
The `push_back` method inserts an element at the end.Here's an example:
``` C++
#include <iostream>
#include <deque>
using namespace std;

int main() {

  deque<int> datas {2, 3};

  cout << "Initial Deque: ";
  for (const int& data : datas) {
    cout << data << ", ";
  }
  
  // add integer 4 at the back
  datas.push_back(4);
   
  // add integer 1 at the front
  datas.push_front(1);
  
  cout << "\nFinal Deque: ";
  for (const int& data : datas) {
    cout << data << ", ";
  }
  
  return 0;
}

```
### Changing Elements of a Deque:
We can use `at()` method for changing the elements in `deque`. Here's an example:
``` C++
#include <iostream>
#include <deque>
using namespace std;

int main() {

  deque<int> nums = {1, 2};
  
  cout << "Initial Deque: ";

  for (const int& num : nums) {
    cout << num << ", ";
  }
  
  // change elements at the index
  nums.at(0) = 3;
  nums.at(1) = 4;
  
  cout << "\nUpdated Deque: ";

  for (const int& num : nums) {
    cout << num << ", ";
  }
  
  return 0;
}

```
### Removing Elements from a Deque:
We can remove elements from deque by two methods `pop_front` & `pop_back`.
``` C++
#include <iostream>
#include <deque>
using namespace std;

// function prototype for display_deque()
void display_deque(deque<int>);

int main() {

  deque<int> nums {1, 2, 3};
  
  cout << "Initial Deque: ";
  display_deque(nums);

  // remove element from the back
  nums.pop_back();
  
  cout << "\nDeque after pop_back(): ";
  display_deque(nums);
  
  // remove element from the front
  nums.pop_front();
  
  cout << "\nDeque after pop_front(): ";
  display_deque(nums);
  
  return 0;
}

// utility function to print deque elements
void display_deque(deque<int> dq){
  for (const int& num : dq) {
    cout << num << ", ";
  }
}
```
# Map

In C++, a map is a standard template library (STL) container that represents an associative container, specifically an associative array. It is initialized bt a header file `map`.

### Inserting into Map:
We can insert into a map using `insert` function. Here's an example:
``` C++
#include <iostream>
#include <map>

using namespace std;

int main() {
    // Declare a map with int keys and string values
    map<int, string> myMap;

    // Method 1: Using insert function
    myMap.insert(make_pair(1, "One"));
    myMap.insert(make_pair(2, "Two"));
    myMap.insert(make_pair(3, "Three"));

    // Method 2: Using subscript operator []
    myMap[4] = "Four";
    myMap[5] = "Five";

    // Display the elements in the map
    for (const auto& pair : myMap) {
        cout << "Key: " << pair.first << ", Value: " << pair.second << endl;
    }

    return 0;
}
```

### Accessing Keys and Values:
We can access the keys and values of our map using the help of map iterators. We can relate it with an example:
```C++
#include <iostream>
#include <map>
using namespace std;

int main() {
    
    map<int, string> student;
  
    // use [] operator to add elements
    student[1] = "Jacqueline";
    student[2] = "Blake";

    // use insert() method to add elements
    student.insert(make_pair(3, "Denise"));
    student.insert(make_pair(4, "Blake"));

    // add elements with duplicate keys
    student[5] = "Timothy";
    student[5] = "Aaron";

    for (int i = 1; i <= student.size(); ++i) {
        cout << "Student[" << i << "]: " << student[i] << endl;
    }

    return 0;
}
```
# Stack:
In order to create a stack in C++, we need to include `stack` header file. The stack data structure follows the LIFO (Last In First Out) princip
### Adding element: 
We use `push()` method to add an element into a stack. 
Here's an example to do so:
```C++
#include <iostream>
#include <stack>
using namespace std;

int main() {

  // create a stack of strings
  stack<string> colors;

  // push elements into the stack
  colors.push("Red");
  colors.push("Orange");
  
  cout << "Stack: ";

  // print elements of stack
   while(!colors.empty()) {
    cout << colors.top() << ", ";
    colors.pop();
  }
 
  return 0;
}
```
### Removing an element:
We can remove an element from the stack using the `pop()` method. Here's an example:
```C++
#include <iostream>
#include <stack>
using namespace std;

// function prototype for display_stack utility
void display_stack(stack<string> st);

int main() {

  // create a stack of strings
  stack<string> colors;

  // push elements into the stack
  colors.push("Red");
  colors.push("Orange");
  colors.push("Blue");
  
  cout << "Initial Stack: ";
  // print elements of stack
  display_stack(colors);
  
  // removes "Blue" as it was inserted last
  colors.pop();
  
  cout << "Final Stack: ";

  // print elements of stack
  display_stack(colors);
  
  return 0;
}

// utility function to display stack elements
void display_stack(stack<string> st) {

  while(!st.empty()) {
    cout << st.top() << ", ";
    st.pop();
  }

  cout << endl;
}
```
### Accessing an element:
We can access the element of the stack using `top()` function. Here's an example:
```C++
#include <iostream>
#include <stack>
using namespace std;

int main() {

  // Create a stack of strings
  stack<string> colors;

  // Push elements into the stack
  colors.push("Red");
  colors.push("Orange");
  colors.push("Blue");
  
  // Get the top element
  string topColor = colors.top();

  cout << "Top Element: " << topColor << endl;
  
  return 0;
}
```
# Set:
Sets are STL containers that store unique elements of the same type in a sorted manner. We have to add `<set>` in header file in our program.

### Creating a Set:
Here's an example of creating a set in C++.
```C++
#include <iostream>
#include <set>
using namespace std;

int main() {

    set<int> my_set = {5, 3, 8, 1, 3};
    
    for(int val : my_set) {
        cout << val << " ";
    }

    return 0;
}
```
### Inserting item in Set:
We can insert an item in Set by using `insert()` function. We can illustrate this with an example given below:
```C++
#include <iostream>     
#include <set>          
using namespace std;
   
int main () {

    set<int> my_set;

    // add values to the set
    my_set.insert(10);
    my_set.insert(30);
    my_set.insert(20);
    my_set.insert(50);
    my_set.insert(40);
    my_set.insert(50);
    
    // print the set elements
    for (int i : my_set) {
        cout << i << "  ";
    }
    
    return 0;
}
```

### Deleting item in Set:
We can delete an item in Set by using `erase()` function. We can illustrate this with an example given below:
``` C++
#include <iostream>
#include <set>

using namespace std;

int main() {
    set<int> my_set = {10, 20, 30, 40};

    // Delete values from the set
    my_set.erase(10);
    my_set.erase(20);

    // Delete all elements from the set
    my_set.clear();

    return 0;
} 
```
  
### Sorting Items in Descending Order:
We can get the elements of set sorted in Descending order as illustrated in the example below.
```C++
#include <iostream>
#include <set>
using namespace std;

int main() {

    set<int, greater<int>> my_set = {5, 3, 8, 1, 3};
    
    for(int val : my_set) {
        cout << val << " ";
    }

    return 0;
}
```

