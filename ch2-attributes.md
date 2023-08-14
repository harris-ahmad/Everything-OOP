# Data Members and Member Functions

- [Data Members and Member Functions](#data-members-and-member-functions)
  - [What are data types of member variables?](#what-are-data-types-of-member-variables)
  - [Objects of Other Classes as Data Members?](#objects-of-other-classes-as-data-members)
  - [Why Use Member Functions?](#why-use-member-functions)

## What are data types of member variables? 

The data types of member variables can be any valid data type in C++. This includes primitive data types like `int`, `float`, `double`, `char`, `bool`, etc. It also includes user-defined data types like `struct`, `class`, `enum`, etc. Since this course assumes that you have a basic understanding of C++, we won't be covering these data types in detail. If you want to learn more about these data types, you can refer to the [C++ documentation](https://en.cppreference.com/w/cpp/language/types).

C++, as an Object-Oriented Programming language gives you a lot of freedom in selecting data types of a data member. Arrays, vectors and pointers can also be used as data stores. The object of our own custom defined class can also be used as a data type. How cool is that? We'll be covering all of these in the upcoming sections.

Here's an example of a Student class and its data members:

```cpp
class Student {
    // all private members
    string name;
    int age;
    string* address;
    float height;
    int grades[9]; // a student can have a max of 9 grades
}
```

## Objects of Other Classes as Data Members? 

Yes, you can use objects of other classes as data members. This is one of the most powerful features of Object-Oriented Programming. You can create objects of one class inside another class. This is called **composition**. This is a slightly advanced concept that we won't be getting into detail. For now, let's see an example of a `Student` class that has an object of the `Address` class as a data member.

```cpp
class Address {
    // all private members
    string street;
    string city;
    string state;
    int zipCode;
}

class Student {
    // all private members
    string name;
    int age;
    Address address; // object of the Address class
    float height;
    int grades[9]; // a student can have a max of 9 grades
}
```

You're not really paying attention, are you? How did you not raise a very important question. These data members are meaningless. We still have not initialized them. Well, nothing to worry about.

## Why Use Member Functions?

Member functions are used to perform operations on the data members. They are used to manipulate the data members. For example, if we have a data member `age`, we can create a member function `setAge()` to set the value of the `age` data member. Similarly, we can create a member function `getAge()` to get the value of the `age` data member. 

Member functions act as an interface between a program and the data members of a class in the program. These functions can either modify the content of the data members or use the data members to perform some operations. The important ones are defined using the public access modifier and the ones that are supposed to be hidden from the user are defined using the private access modifier. Public and Private access modifiers were discussed in great depth in [chapter 1](./ch1-introduction.md). If you haven't read it yet, I highly recommend you to do so.