# Constructors-and-Destructors


Aim: To study and implement Constructors and Destructors.

Tools Used: VS Code or Programiz online compiler.

# Theory

## Constructors in Cpp
--A constructor is a special member function of a class that is automatically invoked when an object is created.
--Its main job is to initialize data members of the class.
--Name rule: A constructor has the same name as the class and does not have a return type (not even void).

**1. Default Constructor**
--Takes no arguments.
--Automatically initializes objects with default values.

```

class Student {
    int age;
public:
    Student() {  // default constructor
        age = 18;
    }
};

```


**2. Parameterized Constructor**
--Accepts parameters to initialize an object with specific values.

```

class Student {
    int age;
public:
    Student(int a) {  // parameterized constructor
        age = a;
    }
};

```

**2. Copy Constructor**
--Creates a new object as a copy of an existing object.

```

class Student {
    int age;
public:
    Student(int a) { age = a; }
    Student(const Student &s) {  // copy constructor
        age = s.age;
    }
};

```

## Destructors in Cpp 
--A destructor is a special member function that is automatically invoked when an object goes out of scope or is deleted.
--Its purpose is to free resources (like memory, file handles, database connections).
--Name rule:
  1.Same name as the class but preceded with a tilde (~).
  2.It does not take arguments and does not return anything.

```

class Student {
public:
    ~Student() {  // destructor
        cout << "Destructor called, object destroyed" << endl;
    }
};

```

# Program-1: Default Constructor
This program defines a class **`Marks`** with five subjects as data members. The **constructor** is used to take input for all subjects when an object is created. In `main()`, when Marks `m1`; is declared, the constructor runs automatically and prompts the user to enter marks. No destructor or other functions are defined, so the program ends after input.

--> Algorithm:

1. Start
2. Define a class Marks with five integer data members: MTT, DCLD, EDC, NT, SS.
3. Define a constructor inside the class that:
  --Prompts the user to enter marks for each subject.
  --Stores the input in the respective data members.
4. In the main() function:
  --Create an object m1 of class Marks.
  --Automatically, the constructor is called and inputs are taken.
5. End

# Program-2: Constructor Outside Class
This program defines a class **`Marks`** with five subject marks as data members. The **constructor** takes input for all marks when an object is created. A separate **`display()`** function is defined to print the entered marks. In `main()`, creating object `m1` calls the constructor for input, and then `m1.display()` shows the stored marks.

--> Algorithm:

1. Start
2. Define a class Marks with five integer data members: MTT, DCLD, EDC, NT, SS.
3. Declare a constructor Marks() to:
  --Prompt the user to enter marks for all five subjects.
  --Store the input values in corresponding data members.
4. Define a member function display() that outputs all the stored marks.
5. In the main() function:
  --Create an object m1 of class Marks.
  --The constructor automatically runs to take input.
  --Call m1.display() to show the entered marks.
6. End

# Program-3: Parameterized Constructor
This program defines a class **`Num`** with two integers as data members. It uses a **parameterized constructor** to initialize the values of `num1` and `num2` at the time of object creation. The **`display()`** function is used to print these values. In `main()`, when object `n1` is created with values `(23, 78)`, the constructor sets them, and `display()` outputs the result.

--> Algorithm:

1. Start
2. Define a class Num with two integer data members: num1 and num2.
3. Define a parameterized constructor Num(int a, int b) that:
  --Assigns a to num1.
  --Assigns b to num2.
4. Define a member function display() that prints the values of num1 and num2.
5. In the main() function:
  --Create an object n1 of class Num by passing values (23, 78) to the constructor.
  --Call n1.display() to output the stored values.
6. End

# Program-4: Copy Constructor (Printing 2 numbers)
This program demonstrates the use of a **copy constructor** in C++. The class **`Num`** has two integers that are initialized either through a **parameterized constructor** or by copying another object. When object `n2` is created from `n1`, the **copy constructor** is called, and it duplicates the values of `n1` into `n2`. The `display()` function prints the values of both objects.

--> Algorithm:

1. Start
2. Define a class Num with two integer data members: num1 and num2.
3. Define a parameterized constructor Num(int a, int b) that assigns a to num1 and b to num2.
4. Define a copy constructor Num(const Num &n) that copies the values of num1 and num2 from another object n and prints "Copy constructor is called!".
5. Define a member function display() that outputs the values of num1 and num2.
6. In the main() function:
  --Create object n1 with values (23, 78) using the parameterized constructor.
  --Call n1.display() to print its values.
  --Create another object n2 as a copy of n1. The copy constructor is invoked automatically.
  --Call n2.display() to print the copied values.
7. End

# Program-5: Copy Constructor (Book Details)
This program defines a class **`Book`** with data members for book name, author, and price. It uses a **parameterized constructor** to initialize these details when an object is created. A **copy constructor** is also defined, which duplicates the values of one object into another and prints a message. In `main()`, book details are entered, stored in object `b1`, displayed, and then copied into `b2` using the copy constructor.

--> Algorithm:

1. Start
2. Define a class Book with three data members: b_name (string), b_auth (string), and price (float).
3. Define a parameterized constructor Book(string b, string a, float p) that assigns the values of book name, author, and price.
4. Define a copy constructor Book(const Book &b) that copies the data members from another object and prints "Copy constructor is called!".
5. Define a member function display() that outputs the book details.
6. In the main() function:
  --Take input from the user for book name, author, and price.
  --Create object b1 using the parameterized constructor and display its details.
  --Create another object b2 as a copy of b1, which automatically calls the copy constructor.
  --Display the details of b2.
7. End

# Program-6: Destructor (counting no. of cars added and discarded)
This program demonstrates the use of **constructors and destructors** with a **static counter**. Each time a `Car` object is created, the constructor increments `count` and displays the number of objects. When an object goes out of scope, the destructor is called, decrementing `count` and showing how many objects remain. It illustrates **object creation and destruction order in C++**.

--> Algorithm:

1. Start
2. Declare a global integer variable count = 0 to keep track of the number of objects.
3. Define a class Car with:
  --A constructor that increments count by 1 and prints the number of objects created.
  --A destructor that decrements count by 1 and prints the number of objects destroyed.
4. In the main() function:
  --Create three objects c1, c2, and c3. Each constructor call increases and displays the count.
  --Create a new block { ... } inside which two more objects c4 and c5 are created. Their constructors update and display the count.
  --When the block ends, destructors of c4 and c5 are called automatically, reducing the count.
  --At the end of main(), destructors of c1, c2, and c3 are called, again decreasing the count step by step.
5. End

# Program-7: Destructor (without specifying constructor)
This program shows the working of a **destructor** in C++. The class **`Date`** has only a destructor, which prints `"Destructor Called"` whenever an object is destroyed. In `main()`, four objects (`d1, d2, d3, d4`) are created, and additional temporary objects are created inside the loop. As each object goes out of scope, its destructor is automatically invoked. Here, constructor isn't specifically written but, by default constructor is present in the code.

--> Algorithm:

1. Start
2. Define a class Date with a destructor that prints "Destructor Called" whenever an object is destroyed.
3. In the main() function:
  --Create four objects d1, d2, d3, d4.
  --Enter a for loop that runs 4 times (i = 0 to 3).
  --In each iteration, create a temporary object d1 inside the loop.
  --At the end of each iteration, the loop’s local object d1 goes out of scope, and its destructor is called.
4. After the loop ends, when main() completes, the destructors of d1, d2, d3, d4 (created outside the loop) are invoked automatically in reverse order of creation.
5. End

# Conclusion
Across these seven programs, we explored how constructors and destructors work in C++.

Program 1 & 2 showed how a default constructor can be used to take input at object creation, and how a separate display() function outputs the data. Program 3 introduced a parameterized constructor, allowing initialization of objects with values passed during creation. Program 4 & 5 demonstrated the copy constructor, which duplicates the values of one object into another, ensuring object data can be cloned correctly. Program 6 illustrated the interaction of constructors and destructors using a counter to track object creation and destruction, emphasizing scope and lifetime of objects. Program 7 highlighted how a destructor is automatically invoked when objects go out of scope, including temporary objects inside loops.

Together, these programs provide a complete understanding of object lifecycle in C++, showing how data is initialized, copied, and cleaned up through constructors and destructors.
